  #include <stdio.h>
  #include <math.h>

  int main(){
  float a, b, x, delta_x, fx,  fsx, fssx, fasx, fassx;
  printf("Ievadiet a robežu ");
  scanf("%f",&a);
  printf("Ievadiet b robežu ");
  scanf("%f",&b);
  printf("Ievadiet precizitāti ");
  scanf("%f",&delta_x);
 
  x=a;
  FILE *file = fopen("derivative.dat","w");
  fprintf(file, "#    \tx\t    f(x)\t   f'(x)\t     f'(x)\t   f''(x)\t    f''(x)\n");
  fprintf(file, "#    \t \t         \t analytical    finite    analytical    finite\n");
  while (x<=b+delta_x){
  fx=(1-x)*exp(-x);
  fsx=((1-x-delta_x)*exp(-x-delta_x)-(1-x)*exp(-x))/delta_x;
  fssx=((1-x-delta_x)*exp(-x-delta_x)-2*(1-x)*exp(-x)+(1-x+delta_x)*exp(-x+delta_x))/(delta_x*delta_x);
  fasx=x*exp(-x)-2*exp(-x);
  fassx=-x*exp(-x)+3*exp(-x);
  //fprintf (file, "%10.2f\t%10.3f\t%10.2f\n" ,x , fx , fsx);
  //fprintf (file, "%10.3f\t%10.5f\t%10.5f\n" ,x , fx , fssx);
  fprintf (file, "%10.3f\t%10.3f\t%10.3f\t%10.3f\t%10.3f\t%10.3f\n" ,x ,fx ,fasx ,fsx , fassx , fssx);

  x+=delta_x;
  }

  fclose(file);

  return 0;

  }
