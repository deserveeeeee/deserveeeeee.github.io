---
layout:     post   				    # 使用的布局（不需要改）
title:      忽略安全证书的resttemplate配置				# 标题
subtitle:   IgnoreSSLRestTemplate #副标题
date:       2019-07-31 				# 时间
author:     Molly 						# 作者
header-img: img/programming.png 	#这篇文章标题背景图片
catalog: true 						# 是否归档
tags:								#标签
    - 12Code:tool
---



    /*
     * Create a RestTemplate bean, using the RestTemplateBuilder
     * with trust all SSL certificates and SSLConnectionSocketFactory.ALLOW_ALL_HOSTNAME_VERIFIER
     * replaced for new apache httpclient to NoopHostnameVerifier.INSTANCE
     */
     
     
     
    @Bean
    public RestTemplate restTemplate(RestTemplateBuilder builder) throws NoSuchAlgorithmException, KeyManagementException {

        /*
         * Ignore untrusted certificates
         */
        TrustManager[] trustAllCerts = new TrustManager[] {
                new X509TrustManager() {
                    public java.security.cert.X509Certificate[] getAcceptedIssuers() {
                        return new X509Certificate[0];
                    }
                    public void checkClientTrusted(
                            java.security.cert.X509Certificate[] certs, String authType) {
                    }
                    public void checkServerTrusted(
                            java.security.cert.X509Certificate[] certs, String authType) {
                    }
                }
        };

        // Install the all-trusting trust manager
        SSLContext sslContext = SSLContext.getInstance("SSL");

        sslContext.init(null, trustAllCerts, new java.security.SecureRandom());

        /*
         * Create an HttpClient that uses the custom SSLContext and do not verify cert hostname
         */
        CloseableHttpClient httpClient = HttpClients.custom()
                .setSSLContext(sslContext)
                .setSSLHostnameVerifier(NoopHostnameVerifier.INSTANCE)
                .build();


        HttpComponentsClientHttpRequestFactory customRequestFactory =
                new HttpComponentsClientHttpRequestFactory();

        customRequestFactory.setHttpClient(httpClient);

        /*
         * Create a RestTemplate that uses custom request factory
         */
        return builder.requestFactory(customRequestFactory).build();
    }
