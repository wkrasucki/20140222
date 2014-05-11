## Pierwsze programy w C

Zaczynamy od *Hello world*(to to wymyślił?).

```c
#include stdio.h

 int main() {
 printf("Hello world");
 return 0;
 }
```
 


Pratycznie kazdy jezyk programowania ma taki program zob "Miejsce zerowe" (below).
[1]:http://www.wp.pl

```c
# include<stdio.h>
# include <math.h>
 
 double miejsceZerowe(double (*funkcja)(double), double a, double b, double epsilon){
if (a>=b) return NAN;
double ya, yb, x, y;

 ya=funkcja(a);
 yb=funkcja(b);
 if (ya*yb>=0) return NAN;
 do {x=(a+b)/2; y=funkcja(x);
 if (y==0) return x;
 if (ya*y<0){ b=x; yb=y;}
 else {a=x; ya=y;}
 }
while (b-a>epsilon);
return x;
}
 
 
 int main(){
 	
 	double x; 
 	x=miejsceZerowe(sin, 1, 5, 1e-7);
 	if (x!=x) printf("Nieprawidłowe dane.");
 	printf("%lf", x);
```
