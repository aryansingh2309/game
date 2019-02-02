#include<iostream.h>
#include<conio.h>
#include<stdlib.h>
#include<graphics.h>
#include<dos.h>
#include<process.h>
#include<stdio.h>
#include<string.h>

void main()
 {
   clrscr();
   int gdriver=DETECT,gmode;
   char cont;
	initgraph(&gdriver,&gmode,"C:\\TURBOC3\\BGI"); //initiate graphics
	settextstyle(0,0,4);
	setcolor(7);
	outtextxy(130,200,"Kation Games");      //title screen

	delay(1500);
	settextstyle(0,0,2);
	setcolor(4);
	outtextxy(200,250,"Jump to the next level...");

	delay(1500);
	clrscr();
	clearviewport();
	settextstyle(0,0,2);
	setcolor(4);
	outtextxy(200,250,"Jump to the next level...");

	delay(1500);
	menu:                    //main menu
	clrscr();
	setbkcolor(0);
	clearviewport();
	settextstyle(0,0,4);
	setcolor(3);
	outtextxy(105,10,"CLASSROOM GAMES");

	settextstyle(0,0,3);
	setcolor(15);

	outtextxy(10,100,"[1] LAST STICK STANDIING"); //game options

	outtextxy(10,150,"[2] HANGMAN");

	outtextxy(10,200,"[3] HAND CRICKET");

	outtextxy(10,250,"[4] CREDITS");

	outtextxy(10,300,"[5] QUIT");

	settextstyle(2,0,5);
	setcolor(3);

	outtextxy(328,400,"(Press the corresponding number to start)");

	char a=getch();        //to sense user input
	clearviewport();

  if(a=='1')            // if user puts 1, i.e matchstick game
  {
   setbkcolor(6);
   setcolor(15);
   settextstyle(0,0,5);
   outtextxy(270,10,"RULES");  //rules for matchstick game
   line(270,30,370,60);
   settextstyle(1,0,3);
   outtextxy(20,100,"1.You have to eliminate bars,");
   outtextxy(20,130,"  how many ever bars of one row.");
   outtextxy(20,160,"2.At max 7 bars in the first row,");
   outtextxy(20,190,"  5 in the second and 3 in the third");
   outtextxy(20,220,"3.Order of eliminating bars in a");
   outtextxy(20,250,"  row doesn't matter");
   outtextxy(20,280,"4.Enter the co-ordinates of the bars");
   outtextxy(20,310,"you want to eliminate as prompted above the bars");
   outtextxy(20,340,"5.Who ever eliminates the ");
   outtextxy(20,370,"  LAST STICK STANDING... LOSES!");
   outtextxy(20,400,"6.Player 1 is green, Player 2 is red");
   settextstyle(1,0,4);
   outtextxy(270,430,"BEGIN...");
   getch();
   clearviewport();
  int x[15],y[15],X[15],Y[15];
  int INP_X,INP_Y,N_BARS,count;
  x[0]=330;
  y[0]=20;
   for(int t=1;t<7;t++)    //to set coordinates for bars
   {
    x[t]=x[t-1]+45;
   }
   for(int r=1;r<7;r++)
   {
    y[r]=y[r-1];
   }
   x[7]=355;
   y[7]=175;
   for(t=8;t<12;t++)
   {
    x[t]=x[t-1]+54;
   }
   for(r=8;r<12;r++)
   {
    y[r]=y[r-1];
   }
   x[12]=380;
   y[12]=330;
   for(t=13;t<15;t++)
   {
    x[t]=x[t-1]+83;
   }
   for(r=13;r<15;r++)
   {
    y[r]=y[r-1];
   }
    for(int z=0;z<15;z++)
    {
     X[z]=x[z]+15;
    }
    for(int q=0;q<15;q++)
    {
     Y[q]=y[q]+145;
    }
 for(int k=1;k<18;k++) //master loop
 {
  count=0;
      for(int g=0;g<15;g++)
       {
	if(x[g]!=0 && X[g]!=0 && y[g]!=0&&Y[g]!=0)
	{count++;}
       }
    if(count==0)
	 {
	  break;
	 }

  initgraph(&gdriver,&gmode,"C:\\TURBOC3\\BGI");  //display screen
  setcolor(15);
  settextstyle(2,0,6);
  outtextxy(10,4,"Number of bars");
  outtextxy(156,4,"Bar co-ordinates");
  settextstyle(2,0,2);
  outtextxy(330,10,"1,1");
  outtextxy(375,10,"2,2");
  outtextxy(420,10,"3,3");
  outtextxy(465,10,"4,4");
  outtextxy(510,10,"5,5");
  outtextxy(555,10,"6,6");
  outtextxy(600,10,"7,7");
  outtextxy(355,165,"8,8");
  outtextxy(409,165,"9,9");
  outtextxy(463,165,"10,10");
  outtextxy(517,165,"11,11");
  outtextxy(571,165,"12,12");
  outtextxy(380,320,"13,13");
  outtextxy(463,320,"14,14");
  outtextxy(546,320,"15,15");

  cout<<"\n\n";

  setbkcolor(6);

  setcolor(8);
  setlinestyle(0,1,3);

  line(310,2,310,480);
  line(0,2,640,2);
  line(154,2,155,480);
  line(0,25,310,25);
   if(k%2==0)                 //to show player 1 by red
    {
     setfillstyle(1,4);
    }
   if(k%2!=0)                 //to show player 1 by green
    {
     setfillstyle(1,2);
    }
   for(int e=0;e<15;e++)     //displaying bars
    {
     bar(x[e],y[e],X[e],Y[e]);
    }
  cin>>N_BARS; //user input to select number of bars

     for(int xy=0;xy<N_BARS;xy++)   //to delete number of bars input by user
      {
       cout<<"\t\t\t";
       cin>>INP_X;      // user input for x coordinate of bar
       line(154,2,155,480);
       cout<<"\t\t\t";
       cin>>INP_Y;      // user input for y coordinate of bar
       line(154,2,155,480);
       x[INP_X-1]=0;
       y[INP_Y-1]=0;
       X[INP_X-1]=0;
       Y[INP_Y-1]=0;
      }

  clrscr();
 }
  initgraph(&gdriver,&gmode,"C:\\TURBOC3\\BGI");
  if(k%2!=0)                          //losing screens
   {
    setbkcolor(4);
    setcolor(8);
    settextstyle(0,0,5);
    outtextxy(30,200,"Player 2 Loses!");
    cout<<"press m to go back to main menu\npress e to quit";//return and quit
    cont = getch();
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
   }
  if(k%2==0)
   {
    setbkcolor(2);
    setcolor(8);
    settextstyle(0,0,5);
    outtextxy(30,200,"Player 1 Loses!");
    cout<<"press m to go back to main menu\npress e to quit";//continue options
    cont = getch();
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
   }

  }
  if(a=='2')     //if user puts 2, i.e hangman
  {
  int gmode,gdriver=DETECT;
  initgraph(&gdriver,&gmode,"C:\\TC\\BIN");
  setbkcolor(6);
  char a[20];                               //rules for hangman
  cout<<"Enter the name of your movie ";
  cout<<"Max 20 characters\nIncluding spaces";
  cout<<endl;
  gets(a);      // user input for movie
  char b[20],c[20];
  char x;
  int leng=strlen(a);  //to check characters only till the length of the movie
  clrscr();
  initgraph(&gdriver,&gmode,"C:\\TC\\BIN");
  setbkcolor(6);
  for(int k=0;k<leng;k++) //to detect vowels
  {
    if(a[k]=='a'||a[k]=='e'||a[k]=='i'||a[k]=='o'||a[k]=='u')
    {
      b[k] = a[k];   //storing vowels in an array
    }

    else if(a[k]==' ')
    {
     b[k] = ' ';
    }
    else
    {
	b[k] = '_';
    }
  }

 int u;
 for(int chances =10;chances>0;)   //loop depending on mistakes(chances left)
  {
    clrscr();
    initgraph(&gdriver,&gmode,"C:\\TC\\BIN");
  setbkcolor(6);
    for(int z=0;z<leng;z++)  //changes ' ' to '/'
	{
	 if(b[z]==' ')
	   {
	    b[z]='/';
	   }
	}
    u=1;
      for(int i=0;i<leng;i++)
       {
	 cout << b[i];         //displaying movie with gaps
       }
	cout<< " \t\t\t\t Chances Remaining: "<<chances; //displaying chances remaining
     cout << "\n\nEnter your guess: ";
     cin >> x;  //input character

    for(i=0;i<leng;i++)      //checks for mistake in input char
    {
       if(x==a[i])
       {
	 b[i] = a[i];
	 u = 0;
       }

    }
    if(u==1)
    {
     chances=chances-1;
    }
       for(z=0;z<leng;z++)    //changing '/' to ' '
	{
	 if(b[z]=='/')
	   {
	     b[z]=' ';
	   }
	}
	if(chances<10)      //diplaying hangman as per number of mistakes
	  {
	    line(450,280,550,280); //podium
	     delay(250);
	     if(chances<9)
	      {
	       line(520,280,520,160); //mast
		delay(250);
		if(chances<8)
		 {
		   line(520,160,480,160); //bar
		    delay(250);
		    if(chances<7)
		     {
		      line(480,160,480,180);//rope
		      delay(250);
		      if(chances<6)
			{
			  circle(480,190,10); //head
			  delay(250);
			if(chances<5)
			 {
			   line(480,200,480,230);//body
			   delay(250);
			   if(chances<4)
			      {
				line(480,200,470,215);//R.Arm
				delay(250);
			      if(chances<3)
				{
				  line(480,200,490,215);//L.Arm
				  delay(250);
				if(chances<2)
				  {
				    line(480,230,470,250);//R.Leg
				    delay(250);
					if(chances<1)
					      {
						line(480,230,490,250);//L.Leg
						delay(250);
					      }
					  }
				      }
				  }
			      }
			  }
		      }
		  }
	      }
	  }

	 for(int y=0;y<leng;y++)
	   {
	    if(a[y]!=b[y])
	      {
		break;
	      }
	   }
	    if(y==leng)        /*if movie is guessed before
				 chances are exhausted*/
	      {
		goto win;
	      }


  }
  clrscr();
  initgraph(&gdriver,&gmode,"C:\\TC\\BIN");
  cout<<"youlose";
  cout<<"press m to go back to main menu\npress e to quit";
    cont = getch();
    if(cont == 'm')       //input for main menu or quitting
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
  goto lose;
  win:
   clrscr();
   initgraph(&gdriver,&gmode,"C:\\TC\\BIN");
   cout<<"you win!!";
  cout<<"press m to go back to main menu\npress e to quit";
    cont = getch();
    if(cont == 'm')      //input for main menu or quitting
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
  lose:
  getch();
  }
  if(a=='3')            //if user puts 3 i.e chooses hand cricket
  {
   setbkcolor(2);
   setcolor(15);
   settextstyle(0,0,5);
   outtextxy(270,10,"RULES");  //rules for hand cricket
   line(270,60,460,60);
   settextstyle(1,0,5);
   outtextxy(20,100,"1.This match will consist of");
   outtextxy(20,160," 3 Overs(6 balls per over)");
   outtextxy(20,220,"2.Press 1 to bat first");
   outtextxy(20,280,"3.Press 2 to ball first");
   settextstyle(1,0,6);
   outtextxy(270,350,"BEGIN...");
   getch();
   clearviewport();
   restart:      //in case incorrect value is entered to bat or ball first
   cout<<"Bat first[1] or ball[2]?\n";
   setbkcolor(2);
   setcolor(15);
   setfillstyle(1,6);   //graphics for cricket pitch
   bar(400,50,500,300);
   line(400,80,500,80);
   line(400,270,500,270);
    int d,x,y,dum=10000;
    cin>>d;
    int balls=18; /* switch statement to select
		    order of batting/balling */
    switch(d)
	{
	 case 1:                       //if user wants bat first
		int bat(int q,int SO); // function prototype
		int ball(int p,int so);// function prototype
		  setfillstyle(1,4);
		  bar(447,310,453,360); //graphics for bat
		  setcolor(14);
		  setfillstyle(1,14);
		  int poly[14]={447,360,438,375,438,450,462,450,462,375,453,360,447,360};
		  fillpoly(7,poly);
		x=bat(dum,balls);//function call
		cout<<"Your score was "<<x;
		    delay(2000);
		    clrscr();
		  initgraph(&gdriver,&gmode,"C:\\TURBOC3\\BGI");
		  setbkcolor(2);
		  setfillstyle(1,6);     //graphics for pitch and ball
		  bar(400,50,500,300);
		  setfillstyle(1,4);
		  pieslice(450,360,0,360,50);
		  line(450,360,400,360);
		  line(400,80,500,80);
		  line(400,270,500,270);
		y=ball(x,balls);        //function call
		cout<<endl<<"The score was "<<y;
		  delay(2000);
		  clrscr();
		  initgraph(&gdriver,&gmode,"C:\\TURBOC3\\BGI");
		if(x<y)    //if user loses
		{
		 clearviewport();
		 setbkcolor(0);
		 setcolor(4);    //graphics for loser screen
		 settextstyle(4,0,6);
		 outtextxy(30,230,"YOU");
		 outtextxy(480,230,"LOSE..");
		 setfillstyle(1,8);
		 bar(170,80,470,460);
		 bar(260,40,380,60);
		 bar(260,40,280,80);
		 bar(360,40,380,80);
		 setcolor(0);
		 setfillstyle(1,0);
		 fillellipse(210,270,20,130);
		 fillellipse(280,270,20,130);
		 fillellipse(350,270,20,130);
		 fillellipse(420,270,20,130);
		 setlinestyle(0,1,3);
		 line(170,120,470,120);
		 line(170,420,470,420);
		 cout<<"press m to go back to main menu\npress e to quit";//continuation options
    cont = getch();
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
		}

		else if(x>y) //if user wins
		{
		 clearviewport();
		 setbkcolor(2);
		 setcolor(14);   //graphics for winner screen
		 setfillstyle(1,14);
		 fillellipse(300,140,107,240);
		 pieslice(300,420,0,180,57);
		 pieslice(300,480,0,180,87);
		 pieslice(193,200,0,360,50);
		 pieslice(407,200,0,360,50);
		 setfillstyle(1,2);
		 bar(193,0,407,140);
		 bar(193,445,407,480);
		 settextstyle(4,0,9);
		 outtextxy(50,10,"YOU WIN!!!");
		 cout<<"press m to go back to main menu\npress e to quit";//continuation options
    cont = getch();
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
		}
		else if(x==y) //if it's a tie
		{
		 playagain: //if player ties in super over and plays again
		 int sX,sY;
		 cout<<"SUPER OVER:\n";
		 balls=6;
		 setfillstyle(1,4);
		  bar(447,310,453,360);
		  setcolor(14);
		  setfillstyle(1,14);
		  fillpoly(7,poly);
		 sX=bat(dum,balls);//function call
		 cout<<"Your score was "<<sX;
		   clrscr();
		   initgraph(&gdriver,&gmode,"C:\\TURBOC3\\BGI");
		   setbkcolor(2);
		   setfillstyle(1,6);
		   bar(400,50,500,300);
		   setfillstyle(1,4);
		   pieslice(450,360,0,360,50);
		   line(450,360,400,360);
		   line(400,80,500,80);
		   line(400,270,500,270);
		 sY=ball(sX,balls);  //function call
		 cout<<"The score was "<<sY;
		   if(sX<sY)    //if user loses
		{
		 clearviewport();
		 setbkcolor(0);
		 setcolor(4);      //loser screen graphics
		 settextstyle(4,0,6);
		 outtextxy(30,230,"YOU");
		 outtextxy(480,230,"LOSE..");
		 setfillstyle(1,8);
		 bar(170,80,470,460);
		 bar(260,40,380,60);
		 bar(260,40,280,80);
		 bar(360,40,380,80);
		 setcolor(0);
		 setfillstyle(1,0);
		 fillellipse(210,270,20,130);
		 fillellipse(280,270,20,130);
		 fillellipse(350,270,20,130);
		 fillellipse(420,270,20,130);
		 setlinestyle(0,1,3);
		 line(170,120,470,120);
		 line(170,420,470,420);
		 cout<<"press m to go back to main menu\npress e to quit";//continuation options
    cont = getch();
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
		}
		 else if(sX>sY)//if user wins
		{
		 setbkcolor(2);
		 setcolor(14);
		 setfillstyle(1,14);   //graphics for winner screen
		 fillellipse(300,140,107,240);
		 pieslice(300,420,0,180,57);
		 pieslice(300,480,0,180,87);
		 pieslice(193,200,0,360,50);
		 pieslice(407,200,0,360,50);
		 setfillstyle(1,2);
		 bar(193,0,407,140);
		 bar(193,445,407,480);
		 settextstyle(4,0,9);
		 outtextxy(50,10,"YOU WIN!!!");
		 cout<<"press m to go back to main menu\npress e to quit";//continuation options
    cont = getch();
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
		}
		 else if(sX==sY)
		 {cout<<endl<<"It's a Tie!";
		 cout<<"press p to play another super over"<<endl;//continuation options
		 cout<<"press m to go back to main menu\npress e to quit";
    cont = getch();
    if(cont=='p')
    {
     goto playagain;
    }
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
		 }
		}
		break;
	 case 2:                         //if user wants to ball first
		int ball(int p, int SO); //function prototype
		int  bat(int q, int so); //function prototype
		   setfillstyle(1,4);        //graphics for ball
		   pieslice(450,360,0,360,50);
		   line(450,360,400,360);
		y=ball(dum,balls);       //funtion call
		cout<<"The score was "<<y;
		  delay(2000);
		  clrscr();
		   initgraph(&gdriver,&gmode,"C:\\TURBOC3\\BGI");
		   setbkcolor(2);
		   setfillstyle(1,6);     //graphics for pitch
		   bar(400,50,500,300);
		   line(400,80,500,80);
		   line(400,270,500,270);
		   setfillstyle(1,4);
		   bar(447,310,453,360);
		   setcolor(14);
		   setfillstyle(1,14);
		   fillpoly(7,poly);
		x=bat(y,balls);     //funtion call
		cout<<endl<<"Your score was "<<x;
		  delay(2000);
		  clrscr();
		   initgraph(&gdriver,&gmode,"C:\\TURBOC3\\BGI");

		if(x<y)//if user loses
		{setbkcolor(0);
		 clearviewport();
		 setcolor(4);
		 settextstyle(4,0,6); //graphics for loser screen
		 outtextxy(30,230,"YOU");
		 outtextxy(480,230,"LOSE..");
		 setfillstyle(1,8);
		 bar(170,80,470,460);
		 bar(260,40,380,60);
		 bar(260,40,280,80);
		 bar(360,40,380,80);
		 setcolor(0);
		 setfillstyle(1,0);
		 fillellipse(210,270,20,130);
		 fillellipse(280,270,20,130);
		 fillellipse(350,270,20,130);
		 fillellipse(420,270,20,130);
		 setlinestyle(0,1,3);
		 line(170,120,470,120);
		 line(170,420,470,420);
		 cout<<"press m to go back to main menu\npress e to quit";//continuation options
    cont = getch();
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
		 }
		else if(x>y)   //if user wins
		{clearviewport();
		 setbkcolor(2);
		 setcolor(14);
		 setfillstyle(1,14);   //graphics for winner screen
		 fillellipse(300,140,107,240);
		 pieslice(300,420,0,180,57);
		 pieslice(300,480,0,180,87);
		 pieslice(193,200,0,360,50);
		 pieslice(407,200,0,360,50);
		 setfillstyle(1,2);
		 bar(193,0,407,140);
		 bar(193,445,407,480);
		 settextstyle(4,0,9);
		 outtextxy(50,10,"YOU WIN!!!");
		 cout<<"press m to go back to main menu\npress e to quit";//contionuation options
    cont = getch();
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
		 }
		else if(x==y)//if it's a tie
		{
		 Restart:   //if user ties and plays again
		 cout<<"SUPER OVER:\n";
		 int sY,sX;
		 balls=6;
		   setfillstyle(1,4);
		   pieslice(450,360,0,360,50);
		   line(450,360,400,360);
		 sY=ball(dum,balls);  //function call
		 cout<<"Your score was "<<sY;
		   clrscr();
		   initgraph(&gdriver,&gmode,"C:\\TURBOC3\\BGI");
		   setbkcolor(2);
		   setfillstyle(1,6);
		   bar(400,50,500,300);
		   line(400,80,500,80);
		   line(400,270,500,270);
		   setfillstyle(1,4);
		   bar(447,310,453,360);
		   setcolor(14);
		   setfillstyle(1,14);
		   fillpoly(7,poly);
		 sX=bat(sY,balls);   //function call
		 cout<<"The score was "<<sX;
		   if(sX<sY)  //if user loses
		{clearviewport();
		 setbkcolor(0);
		 setcolor(4);    //graphics for loser screen
		 settextstyle(4,0,6);
		 outtextxy(30,230,"YOU");
		 outtextxy(480,230,"LOSE..");
		 setfillstyle(1,8);
		 bar(170,80,470,460);
		 bar(260,40,380,60);
		 bar(260,40,280,80);
		 bar(360,40,380,80);
		 setcolor(0);
		 setfillstyle(1,0);
		 fillellipse(210,270,20,130);
		 fillellipse(280,270,20,130);
		 fillellipse(350,270,20,130);
		 fillellipse(420,270,20,130);
		 setlinestyle(0,1,3);
		 line(170,120,470,120);
		 line(170,420,470,420);
		 cout<<"press m to go back to main menu\npress e to quit";//continuation options
    cont = getch();
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
		 }
		 else if(sX>sY) //if user wins
		{clearviewport();
		 setbkcolor(2);
		 setcolor(14);      //graphics for winner screen
		 setfillstyle(1,14);
		 fillellipse(300,140,107,240);
		 pieslice(300,420,0,180,57);
		 pieslice(300,480,0,180,87);
		 pieslice(193,200,0,360,50);
		 pieslice(407,200,0,360,50);
		 setfillstyle(1,2);
		 bar(193,0,407,140);
		 bar(193,445,407,480);
		 settextstyle(4,0,9);
		 outtextxy(50,10,"YOU WIN!!!");
		 cout<<"press m to go back to main menu\npress e to quit";//continuation options
    cont = getch();
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
		 }
		 else if(sX==sY)//if it's a tie
		 {cout<<endl<<"It's a Tie!";
		 cout<<"press p to play another super over"<<endl;//continuation options
		 cout<<"press m to go back to main menu\npress e to quit";
    cont = getch();
    if(cont == 'p')
    {
      goto Restart;
    }
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
		 }
		}

		break;
	 default:cout<<"Please enter a valid no."<<endl;//error statement if incorrect value is entered
		 delay(5000);
		 goto restart;
	}


  }

  if(a=='4') //if user puts 4 i.e credits
   {

    setcolor(15);       //setting the text style
    settextstyle(0,0,3);

    for(int z=0;z<400;z+=5)
     {
       clearviewport();
       outtextxy(10,z,"Project director:Aryan");
   
     }
   cout<<"press m to go back to main menu\npress e to quit";//continouation options
    cont = getch();
    if(cont == 'm')
    {
      goto menu;
    }
    if(cont == 'e')
    {
      goto quit;
    }
   }

  if(a=='5') //if user puts 5 i.e quit
   {
    quit:
    exit(0);
   }

 getch();
 closegraph();
}

int bat(int q,int SO)//funtion for batting
 {
   cout<<"\nBegin Batting"<<endl;
   int a,b=0;
   cout<<"You:\t\tComputer:\n  ";
   for(int k=0;k<SO;k++)/*loop to calculate score, display
			    computers' turn and take user input*/
      {
       int x=random(10)+1;//generates random number as the bowler
       if(k>0)
       {
	cout<<endl;
       }
       cin>>a;          //takes user input
       cout<<"\t\t"<<x;
       b=a+b;

	if(x==a)     /*checks if the batsman is out
		   i.e if the random number=input value*/
	 {
	  if(k==0)
	  {
	   b=0;
	  }
	  cout<<"\nYou're Out!"<<endl;
	  break;
	 }

       if(b>q)  /*checks if user makes more runs than
		  the comp,if so loop breaks */
	{
	 cout<<"\nYou Win!"<<endl;
	 break;
	}

       }
     return b;
 }

int ball(int p,int so)//function for balling
 {
   cout<<"\nBegin Balling"<<endl;
   int a,c=0;
   cout<<"You:\t\tComputer:\n  ";
   for(int j=0;j<so;j++)    /*loop to calculate score, display
			    computers' turn and take user input*/
     {
       int x=random(10)+1;//generates random number as the batsman
       if(j>0)
       {
	cout<<endl;
       }
       cin>>a;       //takes user input

       cout<<"\t\t"<<x;
       c=x+c;

       if(x==a)    /*checks if the batsman is out
		   i.e if the random number=input value*/
	 {
	   if(j==0)
	   {
	     c=0;
	   }
	  cout<<"\nYou Got Him!"<<endl;
	  break;
	 }

       if(c>p)    /*checks if comp makes more
		    runs than user,breaks loop if so*/
	 {
	  cout<<"\nYou Lose!"<<endl;
	  break;
	 }
      }

      return c;
 }
