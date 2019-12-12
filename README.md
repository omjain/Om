#include<stdio.h>
#include<graphics.h>
#include<conio.h>
#include<dos.h>

void rules();
void play();
void about();
void count();

void main()
{
 int x,s=1;
 do
 {
  clrscr();
  printf("\n\n\t\t-----DOTS AND DASHES-----");
  printf("\n\nMENU\n");
  printf("1.RULES\n2.PLAY GAME\n3.ABOUT\n4.QUIT\n");
  scanf("%d",&x);
  switch(x)
  {
   case 1:
	   rules();
	  break;
   case 2:
	  count();
	 break;
   case 3:
	  about();
	  break;
   case 4:
	  s=0;
	  break;
   default :
       printf("WRONG CHOICE\n");
  }
 }
   while(s==1);
}

void play()
{
 char x,y,p1[10],p2[10];
 int q=0,j,player1=0,player2=0,b1=0,b2=0,b3=0,b4=0,l[12];
 int gd=DETECT, gm;
 initgraph(&gd,&gm,"C:\\TURBOC3\\BGI");
 for(j=0;j<12;j++)
   l[j]=0;
  printf("Enter player1's name\n");
  scanf("%s",p1);
  printf("Enter player2's name\n");
  scanf("%s",p2);

 setbkcolor(RED);
 circle(400,100,2);
 circle(425,100,2);
 circle(450,100,2);
 circle(475,100,2);

 circle(400,125,2);
 circle(425,125,2);
 circle(450,125,2);
 circle(475,125,2);

 circle(400,150,2);
 circle(425,150,2);
 circle(450,150,2);
 circle(475,150,2);

 circle(400,175,2);
 circle(425,175,2);
 circle(450,175,2);
 circle(475,175,2);

 outtextxy(390,90,"A");
 outtextxy(415,90,"B");
 outtextxy(440,90,"C");
 outtextxy(465,90,"D");

 outtextxy(390,115,"E");
 outtextxy(415,115,"F");
 outtextxy(440,115,"G");
 outtextxy(465,115,"H");

 outtextxy(390,140,"I");
 outtextxy(415,140,"J");
 outtextxy(440,140,"K");
 outtextxy(465,140,"L");

 outtextxy(390,175,"M");
 outtextxy(415,175,"N");
 outtextxy(440,175,"O");
 outtextxy(465,175,"P");
 printf("Enter points to be joined(A to I)");
 while(q!=12)
 { if(q%2==0)
    { printf("%s ",p1);
    setbkcolor(BLUE);
    }
   else
    { printf("%s ",p2);
     setbkcolor(RED);
    }
 scanf(" %c %c",&x,&y);
 if(x=='a'&& y=='b'||x=='b'&&y=='a'&&l[0]==0)
  {
  line(400,100,425,100);
  q++;
  l[0]++;
  }
 else if(x=='b' && y=='c'&&l[1]==0)
  {
  line(425,100,450,100);
  q++;
  l[1]++;
  }
  else if(x=='a' && y=='d'&&l[2]==0)
  {
  line(400,100,400,125);
  q++;
  l[2]++;
  }
  else if(x=='b' && y=='e'&&l[3]==0)
  {
  line(425,100,425,125);
  q++;
  l[3]++;
  }
  else if(x=='c' && y=='f'&&l[4]==0)
  {
  line(450,100,450,125);
  q++;
  l[4]++;
  }
  else if(x=='d' && y=='e'&&l[5]==0)
  {
  line(400,125,425,125);
  q++;
  l[5]++;
  }
  else if(x=='e' && y=='f'&&l[6]==0)
  {
  line(425,125,450,125);
  q++;
  l[6]++;
  }
  else if(x=='d' && y=='g'&&l[7]==0)
  {
  line(400,125,400,150);
  q++;
  l[7]++;
  }
  else if(x=='e' && y=='h'&&l[8]==0)
  {
  line(425,125,425,150);
  q++;
  l[8]++;
  }
  else if(x=='g' && y=='h'&&l[9]==0)
  {
  line(400,150,425,150);
  q++;
  l[9]++;
  }
  else if(x=='f' && y=='i'&&l[10]==0)
  {
  line(450,125,450,150);
  q++;
  l[10]++;
  }
  else if(x=='h' && y=='i'&&l[11]==0)
  {
  line(425,150,450,150);
  q++;
  l[11]++;
  }
  else
  printf("\nChoose adcacent points,within range\n");

 if(l[0]==1&&l[2]==1&&l[3]==1&&l[5]==1&&b1==0)
   {
   if(q%2==0)
    {
    player1++;
    outtextxy(405,105,"p1");
    }
   else
    {
    player2++;
    outtextxy(405,105,"p2");
    }
    b1=1;
    }
 if(l[1]==1&&l[4]==1&&l[3]==1&&l[6]==1&&b2==0)
   {
    if(q%2==0)
    {
    player1++;
    outtextxy(430,105,"p1");
    }
    else
    {
    player2++;
    outtextxy(430,105,"p2");
    }
    b2=1;
    }
 if(l[7]==1&&l[8]==1&&l[9]==1&&l[5]==1&&b3==0)
  {
    if(q%2==0)
    {
    player1++;
    outtextxy(405,130,"p1");
    }
    else
    {
    player2++;
    outtextxy(405,130,"p2");
    }
    b3=1;
    }
 if(l[6]==1&&l[8]==1&&l[10]==1&&l[11]==1&&b4==0)
  {
    if(q%2==0)
    {
    player1++;
    outtextxy(430,130,"p1");
    }
    else
    {
    player2++; outtextxy
    (430,130,"p2");
    }
    b4=1;
    }
    getch();
 }
 setbkcolor(GREEN);
 if(player1>player2)
  printf("\n\n\t\tplayer 1 is winner");
 if(player1<player2)
  printf("\n\n\t\tplayer 2is winner");
 if(player1==player2)
  printf("\n\n\t\tmatch tied");

  printf("\n\n\t\t\tSCORES: \n\t%s - %d\n\t%s - %d",p1,player1,p2,player2);

 getch();
 closegraph();

}
void rules()
{
  printf("\t\tRULES\n");
  printf("! one player can draw only one line in a single turn\n");
  printf("! line can be only drawn vertically and horizontally\n");
  printf("! player with maximum number of boxes will be winner\n");
  printf("! Enter letters assigned to dots to draw a line\n");
  printf("! There is no time limit for this game\n");
  getch();
}

void about()
{
printf("Game name-DOTS AND DASHES");
printf("Made by-         ");
getch();
}

void count()
{
int gd=DETECT,gm,i;
char a[5];
initgraph(&gd,&gm,"C:\\turboc3\\bgi");
settextjustify(CENTER_TEXT,CENTER_TEXT);
settextstyle(DEFAULT_FONT,HORIZ_DIR,3);
setcolor(RED);
for(i=5;i>=0;i--)
{
sprintf(a,"GAME STARTS IN - %d",i);
outtextxy(getmaxx()/2,getmaxy()/2,a);
delay(1000);
if(i==0)
break;
cleardevice();
}
closegraph();
play();
}
