# implementation-of-bresenhams-algorithm
#animplementation of bresenham's algorithm in c for my comp graphics assesment

#include<stdio.h>
#include<graphics.h>
#include<math.h>
void main()
{
    int gd=DETECT,gm,x,y,x1,y1,x2,y2,dx,dy,i,e;
    float xinc,yinc;
    initgraph(&gd,&gm,"");
    cleardevice();
    printf("Enter x1,y1,x2,y2:\n");
    scanf("%d%d%d%d",&x1,&y1,&x2,&y2);
    dx=x2-x1;
    dy=y2-y1;
    if(x1<x2)
        xinc=1;
    else
        xinc=-1;
    if(y1<y2)
        yinc=1;
    else
        yinc=-1;
    x=x1;
    y=y1;
    if(dx>=dy)
    {
        e=(2*dy)-dx;
        while(x!=x2)
        {
            if(e<0)
                e=e+(2*dy);
            else
            {
                e=e+(2*(dy-dx));
                y=y+yinc;
                y=y+yinc;
            }
            x=x+xinc;
            x=x+xinc;
            putpixel(x,y,WHITE);
        }
    }
    else
    {
        e=(2*dx)-dy;
        while(y!=y2)
        {
            if(e<0)
                e=e+(2*dx);
            else
            {
                e=e+(2*(dx-dy));
                x=x+xinc;
                x=x+xinc;
            }
            y=y+yinc;
            y=y+yinc;
            putpixel(x,y,WHITE);
        }
    }
    getch();
    closegraph();
    restorecrtmode();
}

