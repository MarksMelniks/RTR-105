   # ROOTS.C
    
    #include <stdio.h>
    #include <math.h>

    int main(){
    
    float a,b,c,eps,x,froot;
    int k=0;
    
    printf("Ievadiet a robežu ");
    scanf("%f",&a);
    printf("Ievadiet b robežu ");
    scanf("%f",&b);
    printf("Ievadiet c vērtību izteiksmei (1-x)*exp(-x)=c   ");
    scanf("%f",&c);
    printf("Ievadiet precizitāti ");
    scanf("%f",&eps);
    
    float mid=a;
    
    while((b-a)>=eps){
        k++;
        mid=(a+b)/2;
        
        if((1-mid)*exp(-mid)-c==0){
            break;
        }
        else if(((1-mid)*exp(-mid)-c)*((1-a)*exp(-a)-c)<0){
            b=mid;
        }
        else a=mid;
    }
    
    froot=(1-mid)*exp(-mid)-c;

    printf("\nSakne (1-x)*exp(-x)=%.2f izteiksmei ir   %f\n",c,mid);
    printf("f(%.2f)=%f\n",mid,froot);
    printf("Nepieciešmo literāciju skaits %d",k);
    
    return 0;
    }
    
 ![roots3](https://user-images.githubusercontent.com/71380657/103362668-33e9c000-4ac2-11eb-8f33-ead2a3a4a095.png)
    
    
   # GNUPLOT

    #Scale font and line width (dpi) by changing the size! It will always display stretched.
    set terminal svg size 400,300 enhanced fname 'arial'  fsize 10 butt solid
    set output 'out.svg'

    #Key means label...
    set key inside bottom right
    set title 'Roots'
    set xrange [-2:2]
    set yrange [-2:2]
    set grid
    set label "   (-1.26;0.021039)" at -1.26 , 0.021039 point pointtype 2
    #set object circle at -1.26 , 0.021039 size 0.1
    plot (1-x)*exp(-x)-8

![roots2 1](https://user-images.githubusercontent.com/71380657/103366640-d2c6ea00-4acb-11eb-98bf-4f9ce04f928d.png)
![roots1 1](https://user-images.githubusercontent.com/71380657/103366644-d35f8080-4acb-11eb-905c-b8209143215c.png)




