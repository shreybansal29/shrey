# shrey
#include<stdio.h>
#include<graphics.h>
#include<math.h>
#include<conio.h>
void drawline(float x0, float y0, float x1, float y1)
{
    float dx, dy, p, x, y;

    dx=x1-x0;
    dy=y1-y0;

    x=x0;
    y=y0;

    p=2*dy-dx;

    while(x<x1)
    {
	if(p>=0)
	{
	    putpixel(x,y,7);
	    y=y+1;
	    p=p+2*dy-2*dx;
	}
	else
	{
	    putpixel(x,y,7);
	    p=p+2*dy;
	}
	x=x+1;
    }
}

int main()
{
    float gdriver=DETECT, gmode, error, x0, y0, x1, y1,a,b,c,d,e;
    initgraph(&gdriver, &gmode, "c:\\turboc3\\bgi");

    printf("Enter coffecient of line: ");
    scanf("%f%f%f", &a, &b, &e);

    printf("Enter powers of line: ");
    scanf("%f%f", &c, &d);
    x1= pow(e/a,1/c);
    y0= pow(e/b,1/b);

    drawline(0, y0, x1, 0);
    getch();
    return 0;
    clrscr();
}
