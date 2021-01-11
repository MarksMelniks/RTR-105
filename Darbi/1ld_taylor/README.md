# TAYLOR.c
    
    int main(){

    long double x, y, a, s, e, a999, s999, a1000, s1000;
    int k=0;

    printf("(1-x)*exp(-x) apreiķināšana\n\n");
    printf("Ievadiet x argumentu ");
    scanf("%Lf",&x);
    y=(1-x)*exp(-x);                        // D.a.   xєR

    a=(1-x)*(pow(-1,k)*pow(x,k)/1);
    s=a;

    printf("\nf(%0.Lf)= %Lf\n\n", x, y);
    printf("a0= %Lf          s0= %LF\n", a , s);

    while (k<999){
    k++;
    a=a*(-x)/k;
    s=s+a;
    //printf( "%1.LF , %Le , %Lf\n" ,x , a , s);
    }

    a999=a;
    s999=s;
    a1000=a999*(1-x)/(k-1);
    s1000=s999+a1000;

    printf( "999= %Le  s999= %Lf\n" , a999 , s999);
    printf( "a1000= %Le   s1000= %Lf\n\n" , a1000 , s1000);
    printf("f(%1.Lf) caur summu: %Lf\n", x, s1000);

    printf("                1000\n               ______\n               |            k      k\n                |       (-1)  *  x\nf(%0.Lf) = (1->
    printf("\n\n");
    printf("                          -x\n rekurences reizinātājs: -----                             \n                           k\n");

    }
