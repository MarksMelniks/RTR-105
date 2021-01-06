    #include <stdio.h>
     #include <math.h>

    int main(){
    
    double a, b, h, n, sum, sum1, sum2, sum3, analytintegr, eps;                 
    int k;   
    
    printf("Ievadiet a robežu ");                                      
    scanf("%lf", &a);                                               
    printf("Ievadiet b robežu ");                       
    scanf("%lf", &b);                                               
    printf("ievadiet precizitāti ");            
    scanf("%lf", &eps);                                                                                                
    
    n=pow(eps, -1);
  
    h=(b-a)/n;
    sum=0;
    for (int i=1 ; i<=n ; i++){
        sum+=h*(1-(a+i*h))*exp(-(a+i*h)); //h*f(a+i*h)
    }
    
    
    h=(b-a)/n;
    sum1=0;
    for (int i=0 ; i<=n-1 ; i++){
        sum1+=h*(1-(a+i*h))*exp(-(a+i*h)); //h*f(a+i*h)
    }
    
    
    h=(b-a)/n;
    sum2=(1-a)*exp(-a)+(1-b)*exp(-b);      //f(a)+f(b)
    for (int i=1 ; i<=n-1 ; i++){
        sum2+=2*(1-(a+i*h))*exp(-(a+i*h)); //h*f(a+i*h)
    }
    sum2*=h/2;
        
        
    h=(b-a)/n;
    sum3=(1-a)*exp(-a)+(1-b)*exp(-b);      //f(a)+f(b)
    for (int i=1 ; i<=n-1 ; i++){
        k=2+2*(i % 2);                     //if i is even - k=2 ; if i is odd - k=4
        sum3+=k*(1-(a+i*h))*exp(-(a+i*h)); //k*f(a+i*h)
    }
    sum3*=h/3;
    
    analytintegr=exp(-a)*a+exp(-b)*b;
    
    printf("integrālā vērtība, izmantojot kreisā taisnstūra metodi %f\n", sum);
    printf("integrālā vērtība, izmantojot labā taisnstūra metodi %f\n", sum1);
    printf("integrālā vērtība, izmantojot trapecu metodi %f\n", sum2);
    printf("integrālā vērtība, izmantojot Simpsona metodi %f\n", sum3);
    printf("integrālā vērtība, izmantojot analītisko formulu  %f\n", analytintegr);
    
    
    
    
}

![Снимок экрана (59)](https://user-images.githubusercontent.com/71380657/103816463-ad0e8780-506d-11eb-9fa3-3db7b2d3652e.png)
![Снимок экрана (56)](https://user-images.githubusercontent.com/71380657/103815962-d67ae380-506c-11eb-8a84-1f0c01a58f51.png)
![Снимок экрана (57)](https://user-images.githubusercontent.com/71380657/103815965-d7137a00-506c-11eb-81c0-9223bb5b7c3e.png)
