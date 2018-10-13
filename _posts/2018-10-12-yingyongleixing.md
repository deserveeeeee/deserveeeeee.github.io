# 引用类型
public class Main {

    private static Integer i1;//引用类型，也可称为包装类型
    private static int i2;//基本类型
    private static Bool b1;
    private static boolean b2;
    private static Long L1;
    private static long L2;
    private static Float f1;
    private static float f2;
    private static Object object;//引用类型

    public static void main(String[] args) {

//        int默认值为0，boolean的默认值为false，null是任何引用类型的默认值
        System.out.println(i1);//null
        System.out.println(i2);//0
        System.out.println(b1);//null
        System.out.println(b2);//false
        System.out.println(L1);//null
        System.out.println(L2);//0
        System.out.println(f1);//null
        System.out.println(f2);//0.0
        System.out.println(object);//null
    }
}
