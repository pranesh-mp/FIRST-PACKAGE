#include<stdio.h>
#include<conio.h>
#include<string.h>
#include<dos.h>
#include<stdlib.h>
#include<alloc.h>
struct stud
{
	int markscal,marksappl,marksdigi,marksc,markse;
	float attendcal,attendappl,attenddigi,attendc,attende;
};
struct stud s1[40];
int choice1,ans2;
int a6,b6;
char uname2[100];
void staff();
void student();
void admin();
void display();
void nwpasswrd(char []);
void subjectbranch();
void resultdetails();
void calculus();
void appliedphysics();
void digitalelectronics();
void cprogramming();
void english();
void calculusa(int []);
void appliedphysicsa(int []);
void digitalelectronicsa(int []);
void cprogramminga(int []);
void englisha(int []);
void assignsearchdetails(char [],int);
void enternwpasswrd(char []);
void search();
void studetails();
void revaluation();
void payment();
char uname1[][7]={
	"15PD01","15PD02","15PD03","15PD04","15PD05","15PD06","15PD07","15PD08","15PD09","15PD10"
};
void main()
{
	int v,x,y,z,i,dec;
	clrscr();
	while(1)
	{
		delay(500);
		printf("\n\t\t\t\tSTUDENT ZONE\n\n\n");
		printf("\n\n\n\t\t\t\tPLEASE SELECT AN OPTION\n\n\n");
		printf("\n\t\t\t\t\t1.STAFF");
		printf("\n\t\t\t\t\t2.STUDENT");
		printf("\n\t\t\t\t\t3.ADMIN");
		printf("\n\t\t\t\t\t4.QUIT");
		printf("\n\n\nEnter an option=");
		fflush(stdin);
		x=!scanf("%d",&dec);
		if(x==1)
		{
			printf("\n Enter correct option");
			continue;
		}
		switch(dec)
		{
			case 1:staff();
			
			case 2:student();
			
			case 3:admin();
			
			case 4:exit(0);
			default:printf("\n Enter correct option");
			delay(1000);
			continue;
		}
	}
}
void staff()
{
	char uname[100],password[100];
	int i=0,ch,j,k;
	char c,ifile[100];
	FILE *in;
	clrscr();
	fflush(stdin);
	while(1)
	{
		i=0;
		printf("\n\n\n\n\n\t\t\tUSERNAME=");
		fflush(stdin);
		scanf("%s",uname);
		k=!strcmp(uname,"staff");
		if(k==0)
		{
			printf("\n The username is wrong so please enter it again ");
			delay(500);
			continue;
		}
		else
			delay(200);
		printf("\n\t\t\tPASSWORD=");
		while(1)
		{
			if(i<0)
			{
				i=0;
			}
			ch=getch();
			if(ch==13)
			break;
			password[i++]=ch;
			ch='*';
			putch(ch);
		}
		password[i]='\0';
		printf("\n\n\n\n\n\t\t\t\t WAIT WHILE IT IS PROCESSING\n");
		delay(750);
		clrscr();
		if(!strcmp(password,"admin123"))
		{
			printf("\nWelcome to Staff Portal");
			delay(1000);
			break;
		}
		else
		{
			printf("\nPlease enter correct password");
			continue;
		}
	}
	subjectbranch();
}
void subjectbranch()
{
	char subject[100];
	int u=0,v=0,x=0,y=0,w=0,a10,marks[100],k;
	delay(1000);
	fflush(stdin);
	while(1)
	{
		printf("\n\n\n\n\t\t\t\t SELECT AN OPTION");
		printf("\n\n\t\t\t\t\t1.ENTER DETAILS");
		printf("\n\n\t\t\t\t\t2.EDIT ATTENDANCE");
		printf("\n\n\n\n\n\nEnter the choice =");
		k=!scanf("%d",&a10);
		if(k==1)
		{
			printf("Enter correct option");
			delay(1000);
			continue;
		}
		switch(a10)
		{
			case 1:
			{
				printf("\n Enter Your subject	=");
				fflush(stdin);
				scanf("%s",subject);
				u=!strcmp(subject,"15XD11");
				v=!strcmp(subject,"15XD12");
				w=!strcmp(subject,"15XD13");
				x=!strcmp(subject,"15XD14");
				y=!strcmp(subject,"15XD15");
				if(u==1)
				{
					calculus();
				}
				else
				if(v==1){
					appliedphysics();
				}
				else
				if(w==1){
					digitalelectronics();
				}
				else
				if(x==1){
					cprogramming();
				}
				else
					if(y==1)
				{
					english();
				}
				else
				{
					printf("enter correctly");
					continue;
				}
			}
			case 2:
			{
				printf("\n Enter Your subject	=");
				fflush(stdin);
				scanf("%s",subject);
				u=!strcmp(subject,"15XD11");
				v=!strcmp(subject,"15XD12");
				w=!strcmp(subject,"15XD13");
				x=!strcmp(subject,"15XD14");
				y=!strcmp(subject,"15XD15");
				if(u==1){
					a6=1;
					calculusa(marks);
				}
				else
				if(v==1){
					a6=1;
					appliedphysicsa(marks);
				}
				else
				if(w==1){
					a6=1;
					digitalelectronicsa(marks);
				}
				else
				if(x==1){
					a6=1;
					cprogramminga(marks);
				}
				else
				if(y==1){
					a6=1;
					englisha(marks);
				}
				else
				{
					printf("enter correctly");
					continue;
				}
			}
			default:
			{
				printf("\nEnter it correctly");
				subjectbranch();
			}
		}
	}
}
void calculus()
{
	int marks[40],no_ofperiods,no_attend[40],i,n,k;
	char ans[40];
	float attendpercent[40];
	FILE *fm;
	clrscr();
	fm=fopen("studca.txt","w");
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\n\n\n\n\t\t\tCALCULUS\n\n");
	for(i=0;i<79;i++)
	printf("-");
	for(i=0;   i<2;    i++)
	{   delay(200);
		printf("\n Enter the marks of %d students =",i+1);
		fflush(stdin);
		k=!scanf("%d",&marks[i]);
		if(k==1||marks<0||marks[i]>100)
		{
			printf("\n Enter correct option");
			delay(1000);
			i--;
			continue;
		}
		fprintf(fm,"%d\n",marks[i]);
	}
	fclose(fm);
	for(i=0;i<79;i++)
	printf("-");
	if(ans2==0)
	{
		calculusa(marks);
	}
	if(ans2==1)
	{
		admin();
	}
}
void calculusa(int marks[])
{
	FILE *fa;
	int no_ofperiods,no_attend[40],i,n,j,k;
	char ans[40];
	float attendpercent[40];
	fa=fopen("attendca.txt","w");
	clrscr();
	if(!feof(fa))
	{
		for(i=0;i<79;i++)
		printf("-");
		printf("\n\t\tEnter the total number of periods            =");
		fflush(stdin);
		j=!scanf("%d",&no_ofperiods);
		if(j==1||no_ofperiods<0)
		{
			printf("\n Enter correct option");
			delay(1000);
			calculusa(marks);
		}
		printf("\n\n\n");
		for(i=0;i<79;i++)
		printf("-");
		for(i=0;   i<2;    i++)
		{
			delay(200);
			printf("\n\t\t Enter the number of periods attended =");
			fflush(stdin);
			k=!scanf("%d",&no_attend[i]);
			if(k==1||no_attend<0)
			{
				printf("\n Enter correct option");
				delay(1000);
				i--;
				continue;
			}
			if(no_attend[i]>no_ofperiods)
			{
				printf("\n\n\nYou cant be so studious so enter number of periods attended correctly");
				i--;
				continue;
			}
			attendpercent[i]=(no_attend[i]*1.0/no_ofperiods);
			fprintf(fa,"%0.02f\n",attendpercent[i]);
		}
		fclose(fa);
		for(i=0;i<79;i++)
		printf("-");
	}
	else
	{
		printf("\n ERROR OPENING FILE");
	}
	clrscr();
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\n\tDo you want to see what you have entered (YES) or press anything to exit");
	printf("\n\n\t\t\tEnter the option=");
	scanf("%s",ans);
	for(i=0;i<79;i++)
	printf("-");
	if(!strcmpi(ans,"yes")||!strcmp(ans,"Yes"))
	{
		for(i=0;i<79;i++)
		printf("-");
		printf("\n Total Number ofperiods  =%d",no_ofperiods);
		for(i=0; i<2; i++)
		{
			printf("\n no. of attended     =%d\n",no_attend[i]);
		}
		if(a6==1)
		exit(0);
		for(i=0;i<79;i++)
		printf("-");
		for(i=0; i<2; i++)
		{
			printf("\n marks are           =%d",marks[i]);
		}
		delay(1500);
	}
	printf("\n");
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\t\t\t\t\tTHANKS FOR ENTERING\n");
	for(i=0;i<79;i++)
	printf("-");
	delay(2000);
	exit(0);
}
void appliedphysics()
{
	int marks[40],no_ofperiods,no_attend[40],i,k;
	float attendpercent[40];
	char ans[25];
	FILE *fm,*fa;
	fm=fopen("studap.txt","w");
	clrscr();
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\n\n\n\t\tAPPLIED PHYSICS\n\n\n");
	for(i=0;i<79;i++)
	printf("-");
	for(i=0;    i<2;    i++)
	{
		delay(200);
		printf("\n Enter the marks of %d students           =",i+1);
		fflush(stdin);
		k=!scanf("%d",&marks[i]);
		if(k==1||marks<0||marks[i]>100)
		{
			printf("\n Enter correct option");
			delay(1000);
			i--;
			continue;
		}
		fprintf(fm,"%d\n",marks[i]);
	}
	fclose(fm);
	for(i=0;i<79;i++)
	printf("-");
	if(ans2==0)
	{
		appliedphysicsa(marks);
	}
	if(ans2==1)
	{
		admin();
	}
}
void appliedphysicsa(int marks[])
{
	FILE *fa;
	int no_ofperiods,no_attend[40],i,n,j;
	char ans[40];
	float attendpercent[40];
	fa=fopen("attendap.txt","w");
	if(!feof(fa))
	{
		for(i=0;i<79;i++)
		printf("-");
		printf("\n Enter the total number of periods           =");
		fflush(stdin);
		j=!scanf("%d",&no_ofperiods);
		if(j==1||no_ofperiods<0)
		{
			printf("\n Enter correct option");
			delay(1000);
			appliedphysicsa(marks);
		}
		for(i=0;i<79;i++)
		printf("-");
		for(i=0;    i<2;     i++)
		{
			delay(200);
			printf("\n Enter the number of periods attended=");
			fflush(stdin);
			j=!scanf("%d",&no_attend[i]);
			if(j==1||no_attend<0)
			{
				printf("\n Enter correct option");
				delay(1000);
				i--;
				continue;
			}
			if(no_attend[i]>no_ofperiods)
			{
				printf("You cant be so studious so enter number of periods attended correctly");
				i--;
				continue;
			}
			attendpercent[i]=(no_attend[i]*1.0/no_ofperiods);
			fprintf(fa,"%0.02f\n",attendpercent[i]);
		}
		fclose(fa);
		for(i=0;i<79;i++)
		printf("-");
	}
	else
	{
		printf("\n ERROR OPENING FILE");
	}
	clrscr();
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\n\n\n\tDo u want to see what you have entered (YES) or press anything to exit");
	printf("\n\n\tEnter the option=");
	scanf("%s",ans);
	for(i=0;i<79;i++)
	printf("-");
	if(!strcmpi(ans,"yes")||!strcmp(ans,"Yes"))
	{
		for(i=0;i<79;i++)
		printf("-");
		printf("\n Total Number ofperiods  =%d",no_ofperiods);
		for(i=0;  i<2;  i++)
		{
			printf("\n no. of atended      =%d\n",no_attend[i]);
		}
		if(a6==1)
		{
			exit(0);
		}
		for(i=0;i<79;i++)
		printf("-");
		for(i=0; i<2; i++)
		{
			printf("\n marks are           =%d",marks[i]);
		}
		delay(1500);
		printf("\n");
		for(i=0;i<79;i++)
		printf("-");
	}
	printf("\n\t\t\t\t\tTHANKS FOR ENTERING ");
	for(i=0;i<79;i++)
	printf("-");
	delay(2000);
	exit(0);
}
void digitalelectronics()
{
	int marks[40],no_ofperiods,no_attend[40],i,k;
	float attendpercent[40];
	char ans[25];
	FILE *fm,*fa;
	fm=fopen("studdi.txt","w");
	clrscr();
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\n\n\t\t\tDIGITAL ELECTRONICS\n\n\n");
	for(i=0;i<79;i++)
	printf("-");
	for(i=0;     i<2;      i++)
	{
		delay(200);
		printf("\n Enter the marks of %d students     		=",i+1);
		fflush(stdin);
		k=!scanf("%d",&marks[i]);
		if(k==1||marks<0||marks[i]>100)
		{
			printf("\n Enter correct option");
			delay(1000);
			i--;
			continue;
		}
		fprintf(fm,"%d\n",marks[i]);
	}
	fclose(fm);
	for(i=0;i<79;i++)
	printf("-");
	if(ans2==0)
	{
		digitalelectronicsa(marks);
	}
	if(ans2==1)
	{
		admin();
	}
}
void digitalelectronicsa(int marks[])
{
	FILE *fa;
	int no_ofperiods,no_attend[40],i,n,j,l;
	char ans[40];
	float attendpercent[40];
	fa=fopen("attenddi.txt","w");
	if(!feof(fa))
	{
		for(i=0;i<79;i++)
		printf("-");
		printf("\n Enter the total number of periods  	  	=");
		fflush(stdin);
		j=!scanf("%d",&no_ofperiods);
		if(j==1||no_ofperiods<0)
		{
			printf("\n Enter correct option");
			delay(1000);
			digitalelectronicsa(marks);
		}
		for(i=0;i<79;i++)
		printf("-");
		for(i=0;     i<2;          i++)
		{
			delay(200);
			printf("\n Enter the number of periods attended= ");
			fflush(stdin);
			l=!scanf("%d",&no_attend[i]);
			if(l==1||no_attend<0)
			{
				printf("\n Enter correct option");
				delay(1000);
				i--;
				continue;
			}
			if(no_attend[i]>no_ofperiods)
			{
				printf("You cant be so studious so enter number of periods attended correctly");
				i--;
				continue;
			}
			attendpercent[i]=(no_attend[i]*1.0/no_ofperiods);
			fprintf(fa,"%0.02f\n", attendpercent[i]);
		}
		fclose(fa);
		for(i=0;i<79;i++)
		printf("-");
	}
	else
	{
		printf("\n ERROR OPENING FILE");
	}
	clrscr();
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\n\n\tDo u want to see what you have entered (YES) or press anything to exit");
	printf("\n\n\t\tEnter the option=");
	scanf("%s",ans);
	for(i=0;i<79;i++)
	printf("-");
	if(!strcmpi(ans,"yes")||!strcmp(ans,"Yes"))
	{
		for(i=0;i<79;i++)
		printf("-");
		printf("\n Total Number ofperiods  =%d",no_ofperiods);
		for(i=0; i<2; 	i++)
		{
			printf("\n no. of attended       =%d\n",no_attend[i]);
		}
		if(a6==1)
		exit(0);
		for(i=0;i<79;i++)
		printf("-");
		for(i=0; i<2; i++)
		{
			printf("\n marks are           =%d",marks[i]);
		}
		delay(1500);
		printf("\n");
		for(i=0;i<79;i++)
		printf("-");
	}
	printf("\n\t\t\t\t\tTHANKS FOR ENTERING ");
	for(i=0;i<79;i++)
	printf("-");
	delay(2000);
	exit(0);
}
void cprogramming()
{
	int marks[40],no_ofperiods,no_attend[40],i,j;
	float attendpercent[40];
	char ans[25];
	FILE *fm,*fa;
	fm=fopen("studc.txt","w");
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\n\n\t\tC Program\n\n\n");
	for(i=0;
	i<2;
	i++)
	{
		delay(200);
		printf("\n Enter the marks of %d students 		=",i+1);
		fflush(stdin);
		j=!scanf("%d",&marks[i]);
		if(j==1||marks<0||marks[i]>100)
		{
			printf("\n Enter correct option");
			delay(1000);
			i--;
			continue;
		}
		fprintf(fm,"%d\n",marks[i]);
	}
	fclose(fm);
	for(i=0;i<79;i++)
	printf("-");
	if(ans2==0)
	{
		cprogramminga(marks);
	}
	if(ans2==1)
	{
		admin();
	}
}
void cprogramminga(int marks[])
{
	FILE *fa;
	int no_ofperiods,no_attend[40],i,n,j,l;
	char ans[40];
	float attendpercent[40];
	fa=fopen("attendc.txt","w");
	if(!feof(fa))
	{
		for(i=0;i<79;i++)
		printf("-");
		printf("\n Enter the total number of periods			=");
		fflush(stdin);
		j=!scanf("%d",&no_ofperiods);
		if(j==1||no_ofperiods<0)
		{
			printf("\n Enter correct option");
			delay(1000);
			cprogramminga(marks);
		}
		for(i=0;i<79;i++)
		printf("-");
		for(i=0;   i<2;    i++)
		{
			delay(200);
			printf("\n Enter the number of periods attended		=");
			fflush(stdin);
			l=!scanf("%d",&no_attend[i]);
			if(l==1||no_attend<0)
			{
				printf("\n Enter correct option");
				delay(1000);
				i--;
				continue;
			}
			if(no_attend[i]>no_ofperiods)
			{
				printf("You cant be so studious so enter number of periods attended correctly");
				i--;
				continue;
			}
			attendpercent[i]=(no_attend[i]*1.0/no_ofperiods);
			fprintf(fa,"%0.02f\n",attendpercent[i]);
		}
		fclose(fa);
		for(i=0;i<79;i++)
		printf("-");
	}
	else
	{
		printf("\n ERROR OPENING FILE");
	}
	clrscr();
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\n\tDo u want to see what you have entered (YES) or anything  to exit");
	printf("\n\n\t\tEnter the option=");
	scanf("%s",ans);
	if(!strcmpi(ans,"yes")||!strcmp(ans,"Yes"))
	{
		for(i=0;i<79;i++)
		printf("-");
		printf("\n Total Number ofperiods  =%d",no_ofperiods);
		for(i=0;	i<2;  	i++)
		{
			printf("\n no. of attended      =%d\n",no_attend[i]);
		}
		if(a6==1)
		{
			exit(0);
		}
		for(i=0;i<79;i++)
		printf("-");
		for(i=0; i<2; i++)
		{
			printf("\n marks are           =%d",marks[i]);
		}
		delay(1500);
	}
	printf("\n");
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\t\t\t\t\tTHANKS FOR ENTERING ");
	for(i=0;i<79;i++)
	printf("-");
	delay(2000);
	exit(0);
}
void english()
{
	int marks[40],i,k;
	char ans[25];
	FILE *fm,*fa;
	fm=fopen("stude.txt","w");
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\n\n\t\t\tENGLISH\n\n\n");
	for(i=0;i<79;i++)
	printf("-");
	if(!feof(fm))
	{
		for(i=0;i<79;i++)
		printf("-");
		for(i=0;  i<2; 	i++)
		{
			delay(200);
			printf("\n Enter the marks of %d students 		=",i+1);
			fflush(stdin);
			k=!scanf("%d",&marks[i]);
			if(k==1||marks<0||marks[i]>100)
			{
				printf("\n Enter correct option");
				delay(1000);
				i--;
				continue;
			}
			fprintf(fm,"%d\n",marks[i]);
		}
	}
	else
	{
		printf("\nERROR OPENING FILE");
	}
	fclose(fm);
	for(i=0;i<79;i++)
	printf("-");
	if(ans2==0)
	{
		englisha(marks);
	}
	if(ans2==1)
	{
		admin();
	}
}
void englisha(int marks[])
{
	FILE *fa;
	int no_ofperiods,no_attend[40],i,n,j,l;
	char ans[40];
	float attendpercent[40];
	fa=fopen("attende.txt","w");
	if(!feof(fa))
	{
		for(i=0;i<79;i++)
		printf("-");
		printf("\n Enter the total number of periods		=");
		fflush(stdin);
		l=!scanf("%d",&no_ofperiods);
		if(l==1||no_ofperiods<0)
		{
			printf("\n Enter correct option");
			delay(1000);
			englisha(marks);
		}
		for(i=0;i<79;i++)
		printf("-");
		for(i=0;    i<2;        i++)
		{
			delay(200);
			printf("\n Enter the number of periods attended		=");
			fflush(stdin);
			j=!scanf("%d",&no_attend[i]);
			if(j==1||no_attend<0)
			{
				printf("\n Enter correct option");
				delay(1000);
				i--;
				continue;
			}
			if(no_attend[i]>no_ofperiods)
			{
				printf("\n\nThe students cant be so studious so enter number of periods attended correctly");
				i--;
				continue;
			}
			attendpercent[i]=(no_attend[i]*1.0/no_ofperiods);
			fprintf(fa,"%0.02f\n",attendpercent[i]);
		}
		fclose(fa);
		for(i=0;i<79;i++)
		printf("-");
	}
	else
	{
		printf("\n ERROR OPENING FILE");
	}
	clrscr();
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\n\n\tDo u want to see what you have entered (YES) or press anything to exit");
	printf("\n\n\t\tEnter the option=");
	scanf("%s",ans);
	if(!strcmpi(ans,"yes")||!strcmp(ans,"Yes"))
	{
		for(i=0;i<79;i++)
		printf("-");
		printf("\n Total Number ofperiods  =%d",no_ofperiods);
		for(i=0;  i<2;  i++)
		{
			printf("\n no. of attended     =%d\n",no_attend[i]);
		}
		if(a6==1)
		exit(0);
		for(i=0;i<79;i++)
		printf("-");
		for(i=0; i<2; i++)
		{
			printf("\n marks are           =%d",marks[i]);
		}
		delay(1500);
	}
	printf("\n");
	for(i=0;i<79;i++)
	printf("-");
	printf("\n\t\t\t\t\tTHANKS FOR ENTERING ");
	for(i=0;i<79;i++)
	printf("-");
	delay(2000);
	exit(0);
}
void student()
{
	char uname[100],ifile[100],ans[40],passwrd[25];
	int j,k,i,l;
	FILE *in;
	while(1)
	{
		clrscr();
		printf("\n\n\n\n\t\t\t USERNAME=");
		scanf("%s",uname);
		strcpy(uname2,uname);
		sprintf(ifile,"%s.txt",uname);
		in = fopen(ifile,"r");
		if(in!=NULL)
		{
			enternwpasswrd(ifile);
			exit(0);
		}
		else
		{
			for(j=0; j<2; j++)
			{
				k=!strcmp(uname,uname1[j]);
				if(k==1)
				break;
				else
					continue;
			}
			if(k==0)
			{
				printf("\n Enter correct username");
				continue;
			}
			else  if(k==1)
			{
				printf("\n\t\t\tPASSWORD=");
				scanf("%s",passwrd);
				l=!strcmp(passwrd,"15PD");
				printf("\n\n\n\n\n\t\t\t\t WAIT WHILE IT IS PROCESSING\n");
				delay(750);
				if(l==0)
				{
					printf("\nPlease enter correct password");
					student();
					clrscr();
				}
				else
				{
					printf("\nWelcome to Student Portal");
					nwpasswrd(uname);
					clrscr();
				}
			}
		}
	}
}
void nwpasswrd(char uname[100])
{
	char passwrd[15],deci[15],*name,schl[100],dis[100],st[100],ifile[100];
	char fathn[100],mothn[100],bloodgrp[10];
	FILE *in;
	int i,ch;
	sprintf(ifile,"%s.txt",uname);
	in = fopen(ifile,"w");
	if(!feof(in))
	{
		printf("\n\n\n\n\t\t\tNEW PASSWORD=");
		fflush(stdin);
		while(1)
		{
			if(i<0) {
				i=0;
			}
			ch=getch();
			if(ch==13)
			break;
			if(ch==8)
			{
				putch(8);
				putch(NULL);
				putch(8);
				i--;
				continue;
			}
			passwrd[i++]=ch;
			ch='*';
			putch(ch);
		}
		passwrd[i]='\0';
		fprintf(in,"%s\n",passwrd);
		clrscr();
		printf("\n\t\t\tDETAILS\n\n\n\n");
		printf("\n\t\t\tEnter the length of your name");
		scanf("%d",&i);
		printf("\n\t\t\t Enter your name                  =");
		name=(char *)malloc(i*sizeof(char));
		scanf("%s",name);
		free(name);
		fflush(stdin);
		fprintf(in,"%s\n",name);
		printf("\n\t\t\t Enter your Fathers name          =");
		fflush(stdin);
		gets(fathn);
		fprintf(in,"%s\n",fathn);
		printf("\n\t\t\t Enter your Mothers name          =");
		fflush(stdin);
		gets(mothn);
		fprintf(in,"%s\n",mothn);
		printf("\n\t\t\t Enter the type of blood group    =");
		fflush(stdin);
		gets(bloodgrp);
		fprintf(in,"%s\n",bloodgrp);
		printf("\n\t\t\t Enter your school name           =");
		fflush(stdin);
		gets(schl);
		fprintf(in,"%s\n",schl);
		fprintf(in,"%s\n",schl);
		printf("\n\t\t\t Enter your district name         =");
		fflush(stdin);
		gets(dis);
		fprintf(in,"%s\n",dis);
		printf("\n\t\t\t Enter your state name            =");
		fflush(stdin);
		gets(st);
		fprintf(in,"%s\n",st);
		fclose(in);
	}
	else
	{
		printf("\nERROR opening file");
	}
	studetails();
}
void display()
{
	int marks[100],i,marks1[100],i1;
	float attendpercent1[40],attendpercent[40];
	FILE *fm,*fa;
	fm=fopen("studca.txt","r");
	if(!feof(fm))
	{
		for(i=0;  i<40;   i++)
		{
			fscanf(fm,"%d",&marks[i]);
			s1[i].markscal=marks[i];
		}
	}
	else
	{
		printf("\nERROR opening file");
	}
	fclose(fm);
	fa=fopen("attendca.txt","r");
	if(!feof(fa))
	{
		for(i=0; i<40; 	i++)
		{
			fscanf(fa,"%f",&attendpercent[i]);
			s1[i].attendcal=attendpercent[i];
		}
	}
	else
	{
		printf("\nERROR opening file");
	}
	fclose(fm);
	fm=fopen("studap.txt","r");
	if(!feof(fm))
	{
		for(i=0;   i<40; i++)
		{
			fscanf(fm,"%d",&marks[i]);
			s1[i].marksappl=marks[i];
		}
	}
	else
	{
		printf("\nERROR opening file");
	}
	fclose(fm);
	fa=fopen("attendap.txt","r");
	if(!feof(fa))
	{
		for(i=0;
		i<40;
		i++)
		{
			fscanf(fa,"%f",&attendpercent[i]);
			s1[i].attendappl=attendpercent[i];
		}
	}
	else
	{
		printf("\nERROR opening file");
	}
	fclose(fm);
	fm=fopen("studdi.txt","r");
	if(!feof(fm))
	{
		for(i=0;
		i<40;
		i++)
		{
			fscanf(fm,"%d",&marks[i]);
			s1[i].marksdigi=marks[i];
		}
	}
	else
	{
		printf("\nERROR opening file");
	}
	fclose(fm);
	fa=fopen("attenddi.txt","r");
	if(!feof(fa))
	{
		for(i=0;   i<40;	i++)
		{
			fscanf(fa,"%f",&attendpercent[i]);
			s1[i].attenddigi=attendpercent[i];
		}
	}
	else
	{
		printf("\nERROR opening file");
	}
	fclose(fm);
	fm=fopen("studc.txt","r");
	if(!feof(fm))
	{
		for(i=0;
		i<2;
		i++)
		{
			fscanf(fm,"%d",&marks[i]);
			s1[i].marksc=marks[i];
		}
	}
	else
	{
		printf("\nERROR opening file");
	}
	fclose(fm);
	fa=fopen("attendc.txt","r");
	if(!feof(fa))
	{
		for(i=0;
		i<40;
		i++)
		{
			fscanf(fa,"%f",&attendpercent[i]);
			s1[i].attendc=attendpercent[i];
		}
	}
	else
	{
		printf("\nERROR opening file");
	}
	fclose(fm);
	fm=fopen("stude.txt","r");
	if(!feof(fm))
	{
		for(i=0; i<2;  	i++)
		{
			fscanf(fm,"%d",&marks[i]);
			s1[i].markse=marks[i];
		}
	}
	else
	{
		printf("\nERROR opening file");
	}
	fclose(fm);
	fa=fopen("attende.txt","r");
	if(!feof(fa))
	{
		for(i=0;
		i<40;
		i++)
		{
			fscanf(fa,"%f",&attendpercent[i]);
			s1[i].attende=attendpercent[i];
		}
	}
	fclose(fm);
	if(choice1!=1)
	{
		resultdetails();
	}
	
}
void resultdetails()
{
	int rollno,i,k;
	clrscr();
	while(1)
	{
		printf("\n Enter the last  digit of your rollno=");
		fflush(stdin);
		k=!scanf("%d",&rollno);
		if(k==1)
		{
			printf("\nEnter correct option");
			delay(1000);
			continue;
		}
		fflush(stdin);
		if(rollno>2||rollno<0)
		{
			printf("\n Enter the correct roll number");
			getch();
			clrscr();
			continue;
		}
		rollno-=1;
		clrscr();
		printf("\n\t\t\t\t\tDETAILS\n\n\n");
		printf("\n\t\t\t\t\tMARKS\n\n\n");
		for(i=0;i<79;i++)
		printf("-");
		printf("\nSUBJECTS\t\t15XD11\t15XD12\t15XD13\t15XD14\t15XD15\n");
		for(i=0;i<79;i++)
		printf("-");
		printf("\n15PD0%d\t\t\t   %d\t  %d\t  %d\t  %d\t  %d\n",rollno+1,s1[rollno].markscal,s1[rollno].marksappl,s1[rollno].marksdigi,s1[rollno].marksc,s1[rollno].markse);
		for(i=0;i<79;i++)
		printf("-");
		delay(1000);
		getch();
		clrscr();
		printf("\n\t\t\t\t\tATTENDANCE\n\n\n");
		for(i=0;i<80;i++)
		printf("-");
		printf("\nSUBJECTS\t\t15XD11\t15XD12\t15XD13\t15XD14\t15XD15\n");
		for(i=0;i<80;i++)
		printf("-");
		printf("\n15PD0%d\t\t\t%0.02f\t%0.02f  %0.02f  %0.02f   %0.02f\n",rollno+1,s1[rollno].attendcal*100,s1[rollno].attendappl*100,s1[rollno].attenddigi*100,s1[rollno].attendc*100,s1[rollno].attende*100);
		for(i=0;i<80;i++)
		printf("-");
		getch();
		break;
	}
	studetails();
}
void admin()
{
	int k,j,ch,l;
	char sub[25],ans[25],ans1[25];
	int i,marks1,no,marks[20],dec,max,c1=0,d,min;
	char uname[100],password[100];
	FILE *in,*fm;
	clrscr();
	choice1=1;
	display();
	fflush(stdin);
	while(1)
	{
		printf("\n\n\n\n\n\t\t\tUSERNAME=");
		scanf("%s",uname);
		k=!strcmp(uname,"admin");
		if(k==0)
		{
			printf("\n The username is wrong so please enter it again ");
			delay(500);
			continue;
		}
		else
			delay(200);
		printf("\n\t\t\tPASSWORD=");
		scanf("%s",password);
		delay(100);
		clrscr();
		printf("\n\n\n\n\n\t\t\t\t WAIT WHILE IT IS PROCESSING\n");
		delay(750);
		clrscr();
		k=!strcmp(password,"admin@123");
		if(k)
		{
			printf("\nWelcome to Admin Portal");
			delay(1000);
			break;
		}
		else
		{
			printf("\nPlease enter correct password");
			continue;
		}
	}
	while(1)
	{
		clrscr();
		printf("\n\t\t\t\tADMINISTRATOR\n\n\n");
		printf("\n\n\n\t\t\t\tPLEASE SELECT AN OPTION\n\n\n");
		printf("\n\t\t\t\t\t1.VIEW ALL");
		printf("\n\t\t\t\t\t2.EDIT");
		printf("\n\t\t\t\t\t3.SEARCH");
		printf("\n\t\t\t\t\t4.SORTING");
		printf("\n\t\t\t\t\t5.QUIT");
		printf("\n\n\nEnter an option=");
		fflush(stdin);
		k=!scanf("%d",&dec);
		if(k==1)
		{
			printf("\nEnter correct option");
			delay(1000);
			continue;
		}
		switch(dec)
		{
			case 1:
			clrscr();
			printf("\n\t\t\t\t\tDETAILS\n\n\n");
			printf("\n\t\t\t\t\tMARKS\n\n\n");
			for(i=0;i<79;i++)
			printf("-");
			printf("\nSUBJECTS\t\t15XD11\t15XD12\t15XD13\t15XD14\t15XD15\n");
			for(i=0;i<79;i++)
			printf("-");
			for(i=0;i<2;i++)
			printf("\n15PD0%d\t\t\t   %d\t  %d\t  %d\t  %d\t  %d\n",i+1,s1[i].markscal,s1[i].marksappl,s1[i].marksdigi,s1[i].marksc,s1[i].markse);
			for(i=0;i<79;i++)
			printf("-");
			delay(2000);
			clrscr();
			printf("\n\t\t\t\t\tATTENDANCE\n\n\n");
			for(i=0;i<80;i++)
			printf("-");
			printf("\nSUBJECTS\t\t15XD11\t15XD12\t15XD13\t15XD14\t15XD15\n");
			for(i=0;i<80;i++)
			printf("-");
			for(i=0;i<2;i++)
			printf("\n15PD0%d\t\t\t%0.02f\t%0.02f  %0.02f  %0.02f   %0.02f\n",i+1,s1[i].attendcal*100,s1[i].attendappl*100,s1[i].attenddigi*100,s1[i].attendc*100,s1[i].attende*100);
			for(i=0;i<79;i++)
			printf("-");
			delay(2000);
			continue;
			case 2:
			while(1)
			{
				clrscr();
				printf("DO YOU WANT TO EDIT (YES) or (NO)?");
				scanf("%s",ans);
				clrscr();
				if(!strcmpi(ans,"no")||!strcmp(ans,"NO"))
				break;
				if(!strcmpi(ans,"yes")||!strcmp(ans,"YES"))
				{
					printf("\n\n\n\t\tDo you want to edit all values (all) or just one value(one)");
					printf("\n\n\t\tEnter the option=");
					scanf("%s",ans1);
					if(!strcmpi(ans1,"all"))
					{
						ans2=1;
						getch();
						clrscr();
						subjectbranch();
						break;
					}
					else
					{
						if(!strcmpi(ans1,"one"))
						{
							char subject[100];
							int u=0,v=0,x=0,y=0,w=0;
							printf("\n Enter Your subject=");
							scanf("%s",subject);
							u=!strcmp(subject,"15XD11");
							v=!strcmp(subject,"15XD12");
							w=!strcmp(subject,"15XD13");
							x=!strcmp(subject,"15XD14");
							y=!strcmp(subject,"15XD15");
							if(u==1)
							{
								fm=fopen("studca.txt","r");
							}
							else
								if(v==1)
							{
								fm=fopen("studap.txt","r");
							}
							else
								if(w==1)
							{
								fm=fopen("studdi.txt","r");
							}
							else
								if(x==1)
							{
								fm=fopen("studc.txt","r");
							}
							else
								if(y==1)
							{
								fm=fopen("stude.txt","r");
							}
							else
							{
								printf("\nEnter it correctly");
								break;
							}
							printf("Enter their class roll number=");
							j=!scanf("%d",&no);
							if(j==1||no<0||no>2)
							{
								printf("\n Enter it correctly");
								delay(1000);
								continue;
							}
							printf("\n Enter the new marks=");
							l=!scanf("%d",&marks1);
							if(l==1||marks1<0)
							{
								printf("\n Enter it correctly");
								delay(1000);
								continue;
							}
							for(i=0; i<2; i++)
							{
								fscanf(fm,"%d",&marks[i]);
							}
							fclose(fm);
							no-=1;
							marks[no]=marks1;
							if(u==1)
							{
								fm=fopen("studca.txt","w");
							}
							else
								if(v==1)
							{
								fm=fopen("studap.txt","w");
							}
							else
								if(w==1)
							{
								fm=fopen("studdi.txt","w");
							}
							else
								if(x==1)
							{
								fm=fopen("studc.txt","w");
							}
							else
								if(y==1)
							{
								fm=fopen("stude.txt","w");
							}
							for(i=0; i<2; i++)
							{
								fprintf(fm,"%d\n",marks[i]);
							}
							getch();
							fclose(fm);
							break;
						}
						else
						{
							printf("\n Enter correct value");
							continue;
						}
					}
				}
			}
			continue;
			case 3:
			{
				search();
				continue;
				
			}
			case 4:
			{
				while(1)
				{
					clrscr();
					printf("\n\n\n\n\n\t\t\t\tSORTING");
					printf("\n\n\n\t\t1.CALCULUS");
					printf("\n\n\n\t\t2.APPLIED PHYSICS");
					printf("\n\n\n\t\t3.DIGITAL ELECTRONICS");
					printf("\n\n\n\t\t4.C PROGRAMMING");
					printf("\n\n\n\t\t5.ENGLISH");
					printf("\n\n\t Enter the option=");
					fflush(stdin);
					d=!scanf("%d",&c1);
					if(d==1)
					{
						printf("\n Enter correct option");
						delay(1000);
						continue;
					}
					switch(c1)
					{
						case 1:max=s1[0].markscal;
						if(max<s1[1].markscal)
						{
							max=s1[1].markscal;
						}
						else
							min=s1[1].markscal;
						clrscr();
						for(i=0;i<79;i++)
						printf("-");
						printf("\n\n\n\n\t\t\tSORTING\n\n");
						for(i=0;i<79;i++)
						printf("-");
						printf("\n\n\t\tNUMBER\t\tMARKS\n");
						for(i=0;i<79;i++)
						printf("-");
						i=0;
						printf("\n    \t\t%d    \t\t%d\n",i+1,max);
						printf("\n    \t\t%d    \t\t%d\n",i+2,min);
						for(i=0;i<79;i++)
						printf("-");
						printf("\nHighest marks=%d\n",max);
						delay(2000);
						break;
						case 2:max=s1[0].marksappl;
						if(max<s1[1].marksappl)
						{
							max=s1[1].marksappl;
						}
						else
							min=s1[1].marksappl;
						clrscr();
						for(i=0;i<79;i++)
						printf("-");
						printf("\n\n\n\n\t\t\tSORTING\n");
						for(i=0;i<79;i++)
						printf("-");
						printf("\n\n\t\tNUMBER\t\tMARKS\n");
						for(i=0;i<79;i++)
						printf("-");
						i=0;
						printf("    \t\t%d    \t\t%d\n",i+1,max);
						printf("    \t\t%d    \t\t%d\n",i+2,min);
						for(i=0;i<79;i++)
						printf("-");
						printf("\nHighest marks=%d",max);
						delay(2000);
						break;
						case 3:max=s1[0].marksdigi;
						if(max<s1[1].marksdigi)
						{
							max=s1[1].marksdigi;
						}
						else
							min=s1[1].marksdigi;
						clrscr();
						for(i=0;i<79;i++)
						printf("-");
						printf("\n\n\n\n\t\t\tSORTING\n");
						for(i=0;i<79;i++)
						printf("-");
						printf("\n\n\t\tNUMBER\t\tMARKS\n");
						for(i=0;i<79;i++)
						printf("-");
						i=0;
						printf("    \t\t%d    \t\t%d\n",i+1,max);
						printf("    \t\t%d    \t\t%d\n",i+2,min);
						for(i=0;i<79;i++)
						printf("-");
						printf("\nHighest marks=%d",max);
						delay(2000);
						break;
						case 4:max=s1[0].marksc;
						if(max<s1[1].marksc)
						{
							max=s1[1].marksc;
						}
						else
							min=s1[1].marksc;
						clrscr();
						for(i=0;i<79;i++)
						printf("-");
						printf("\n\n\n\n\t\t\tSORTING\n");
						for(i=0;i<79;i++)
						printf("-");
						printf("\n\n\t\tNUMBER\t\tMARKS\n");
						for(i=0;i<79;i++)
						printf("-");
						i=0;
						printf("    \t\t%d    \t\t%d\n",i+1,max);
						printf("    \t\t%d    \t\t%d\n",i+2,min);
						for(i=0;i<79;i++)
						printf("-");
						printf("\nHighest marks=%d",max);
						delay(2000);
						break;
						case 5:max=s1[0].markscal;
						if(max<s1[1].markse)
						{
							max=s1[1].markse;
						}
						else
							min=s1[1].markse;
						clrscr();
						for(i=0;i<79;i++)
						printf("-");
						printf("\n\n\n\n\t\t\tSORTING\n");
						for(i=0;i<79;i++)
						printf("-");
						printf("\n\n\t\tNUMBER\t\tMARKS\n");
						for(i=0;i<79;i++)
						printf("-");
						i=0;
						printf("    \t\t%d    \t\t%d\n",i+1,max);
						printf("    \t\t%d    \t\t%d\n",i+2,min);
						for(i=0;i<79;i++)
						printf("-");
						printf("\nHighest marks=%d",max);
						delay(2000);
						break;
						default:printf("\n\n\n\t\t Enter valid option");
						delay(2000);
						continue;
					}
					break;
				}
			}
			continue;
			case 5:
			{
				delay(1000);
				printf("\n\n\n\n\t\t\t\t Thanks for coming\n");
					exit(0);
			}
			default:
			{
				printf("\n\n\t\t\tEnter correct value");
				delay(1000);
				continue;
			}
		}
	}
}
void search()
{
	int rollno,i,k;
	char uname[25],ifile[25],name[100],schl[100],dis[100],st[100],fathn[100],mothn[100],bloodgrp[10],a[10];
	FILE *in;
	long int ph;
	clrscr();
	printf("\n Enter their roll number to search for them(Enter The full number)         =");
		fflush(stdin);
	scanf("%s",uname);
	printf("\n Enter their last number                                                   =");
	fflush(stdin);
	k=!scanf("%d",&rollno);
	if(k==1||rollno<0||rollno>2)
	{
		printf("\n Enter it correctly");
		delay(1000);
		search();
	}
	display();
	sprintf(ifile,"%s.txt",uname);
	in=fopen(ifile,"r");
	if(in!=NULL)
	{
		fscanf(in,"%s",a);
		printf("\n\n\t\t\tNAME         =");
		fscanf(in,"%s",name);
		printf("%s",name);
		fflush(stdin);
		printf("\n\n\t\t\tFathers name  =");
		fflush(stdin);
		fscanf(in,"%s",fathn);
		printf("%s",fathn);
		printf("\n\n\t\t\tMothers name  =");
		fflush(stdin);
		fscanf(in,"%s",mothn);
		printf("%s",mothn);
		printf("\n\n\t\t\tBlood group   =");
		fflush(stdin);
		fscanf(in,"%s",bloodgrp);
		printf("%s",bloodgrp);
		printf("\n\n\t\t\tSchool name   =");
		fflush(stdin);
		fscanf(in,"%s",schl);
		printf("%s",schl);
		printf("\n\n\t\t\tDistrict name =");
		fflush(stdin);
		fscanf(in,"%s",dis);
		printf("%s",dis);
		printf("\n\n\t\t\tState name    =");
		fflush(stdin);
		fscanf(in,"%s",&st);
		printf("%s",st);
		fclose(in);
		getch();
		clrscr();
		rollno-=1;
		clrscr();
		printf("\n\t\t\t\t\tDETAILS\n\n\n");
		printf("\n\t\t\t\t\tMARKS\n\n\n");
		for(i=0;i<79;i++)
		printf("-");
		printf("\nSUBJECTS\t\t15XD11\t15XD12\t15XD13\t15XD14\t15XD15\n");
		for(i=0;i<79;i++)
		printf("-");
		printf("\n15PD0%d\t\t\t   %d\t  %d\t  %d\t  %d\t  %d\n",rollno+1,s1[rollno].markscal,s1[rollno].marksappl,s1[rollno].marksdigi,s1[rollno].marksc,s1[rollno].markse);
		for(i=0;i<79;i++)
		printf("-");
		delay(1000);
		getch();
		clrscr();
		printf("\n\t\t\t\t\tATTENDANCE\n\n\n");
		for(i=0;i<80;i++)
		printf("-");
		printf("\nSUBJECTS\t\t15XD11\t15XD12\t15XD13\t15XD14\t15XD15\n");
		for(i=0;i<80;i++)
		printf("-");
		printf("\n15PD0%d\t\t\t%0.02f\t%0.02f  %0.02f  %0.02f   %0.02f\n",rollno+1,s1[rollno].attendcal*100,s1[rollno].attendappl*100,s1[rollno].attenddigi*100,s1[rollno].attendc*100,s1[rollno].attende*100);
		for(i=0;i<80;i++)
		printf("-");
		getch();
	}
	else
	{
		printf("The file is not valid or hasnt be entered");
		delay(1000);
	}
}
void enternwpasswrd(char ifile [10])
{
	char password[100],pass[100],uname[100];
	int i=0,ch,j;
	char c;
	FILE *in;
	int k;
	in = fopen(ifile,"r");
	fscanf(in,"%s",pass);
	fclose(in);
	while(1)
	{
		i=0;
		printf("\n\t\t\tNEW PASSWORD=");
		while(1)
		{
			if(i<0)
			{
				i=0;
			}
			ch=getch();
			if(ch==13)
			break;
			if(ch==8)
			{
				putch(8);
				putch(NULL);
				putch(8);
				i--;
				continue;
			}
			password[i++]=ch;
			ch='*';
			putch(ch);
		}
		password[i]='\0';
		k=!strcmp(password,pass);
		if(k==1)
		{
			studetails();
			exit(0);
		}
		else
			printf("\n Enter correct password ");
		continue;
	}
}
void studetails()
{
	int ch,k,i,j,ch1,ch2,ch3,ch4,accno,amt,a,n10,b,c,n11,m,x,y,z,m1,m2;
	char ifile[25],name[25],accname[25],colname[25],uname[100],uname3[100][100];
	FILE *in;
	fflush(stdin);
	clrscr();
	choice1=1;
	display();
	while(1)
	{
		printf("\n\n\n\n\t\t\t\tStudents zone");
		printf("\n\n\t\t1.MARKS");
		printf("\n\n\t\t2.FEES");
		printf("\n\n\t\t3.REVALUATION");
		printf("\n\n\t\t4.QUIT");
		printf("\n\n\t\tEnter the option=");
		delay(1000);
		fflush(stdin);
		k=!scanf("%d",&ch);
		if(k==1)
		{
			printf("Enter correct option");
			delay(1000);
			continue;
		}
		switch(ch)
		{
			case 1: choice1=0;
			display();
			break;
			case 2:
			{
				clrscr();
				while(1)
				{
					clrscr();
					printf("\n\n\n\n\n\t\t\tVERIFICATION\n");
					printf("\n\t\t\tUSERNAME:");
					fflush(stdin);
					scanf("%s",uname);
					i=0;
					while(i<2)
					{
						in=fopen("fees.txt","r");
						fscanf(in,"%s",uname3[i]);
						fclose(in);
						if(!strcmpi(uname,uname3[i]))
						{
							printf("\n You have paid already");
							delay(2000);
							studetails();
						}
						break;
					}
					in=fopen("fees.txt","a");
					fprintf(in,"%s",uname);
					fclose(in);
					delay(500);
					if(strcmpi(uname,uname2))
					{
						printf("\n Enter corrct username");
						delay(1000);
						continue;
					}
					break;
				}
				while(1)
				{
					clrscr();
					for(i=0;i<79;i++)
					printf("-");
					printf("\n\n\n\t\tFEES DETAILS\n");
					for(i=0;i<79;i++)
					printf("-");
					printf("\n\n\n\t\t STAFF FEES               =RS.10000");
					printf("\n\n\t\t TUITION FEES             =RS.5000");
					printf("\n\n\t\t TOUR FEES                =RS.1000");
					printf("\n\n\t\t TAX                      =RS.2500");
					printf("\n\n\t\t LIBRARY USAGE            =RS.2500\n");
					for(i=0;i<79;i++)
					printf("-");
					printf("\n\n\t\t TOTAL AMOUNT             =RS.17000\n");
					for(i=0;i<79;i++)
					printf("-");
					printf("\n\n\t\t Do you want to pay now press 1 or press 0\n");
					printf("\n\t\tEnter an option=");
					fflush(stdin);
					j=!scanf("%d",&ch1);
					if((ch1!=1||ch1!=0)&&j==1)
					{
						printf("\n\n\nEnter correct option");
						delay(1000);
						continue;
					}
					switch(ch1)
					{
						case 1:payment();
						break;
						case 0:studetails();
						default:continue;
					}
					
				}
			}
			case 3:revaluation();
			continue;
			case 4:exit(0);
			default:printf("\nEnter correct option");
			delay(1000);
			continue;
		}
	}
}

void payment()
{
	int ch1,ch2,ch3,ch4,accno,amt,a,b,c,m,x,y,z,m1,m2,i,k,j;
	char ifile[25],name[25],accname[25],colname[25],uname[100];
	while(1)
	{
		clrscr();
		printf("\n\n\n\t\t Enter mode of payment");
		printf("\n\t\t1.CASH");
		printf("\n\t\t2.CHEQUE");
		printf("\n\n\n\tEnter an option=");
		fflush(stdin);
		k=!scanf("%d",&ch2);
		switch(k)
		{
			case 1:printf("Enter option correctly");
			delay(1000);
			continue;
			case 0: if(ch2==1||ch2==2)
			break;
			else
				continue;
		}
		switch(ch2)
		{
			case 1:
			case 2:while(1)
			{
				clrscr();
				printf("\n\n\n\n\tDo you want to see fee details press 1 or press 0\n");
				printf("\n\n\nEnter the option=");
				fflush(stdin);
				m2=!scanf("%d",&ch3);
				if(m2==1)
				{
					printf("\n\tEnter correct option");
					delay(1000);
					continue;
				}
				if(ch3==1)
				{
					clrscr();
					for(i=0;i<79;i++)
					printf("-");
					printf("\n\n\n\t\tFEES DETAILS\n");
					for(i=0;i<79;i++)
					printf("-");
					printf("\n\n\n\t\t STAFF FEES               =RS.10000");
					printf("\n\n\t\t TUITION FEES             =RS.5000");
					printf("\n\n\t\t TOUR FEES                =RS.1000");
					printf("\n\n\t\t TAX                      =RS.2500");
					printf("\n\n\t\t LIBRARY USAGE            =RS.2500\n");
					for(i=0;i<79;i++)
					printf("-");
					printf("\n\n\t\t TOTAL AMOUNT             =RS.17000\n");
					for(i=0;i<79;i++)
					printf("-");
					delay(2000);
					continue;
				}
				if(ch3==0)
				{
					fflush(stdin);
					printf("-");
					for(i=0;i<79;i++)
					printf("-");
					printf("\n\n\t\t\tACCOUNT NUMBER             =");
					fflush(stdin);
					m=!scanf("%d",&accno);
					for(i=0;i<79;i++)
					printf("-");
					fflush(stdin);
					printf("\n\n\t\t\t NAME                      =");
					scanf("%s",name);
					for(i=0;i<79;i++)
					printf("-");
					fflush(stdin);
					printf("\n\n\t\t\tACCOUNT NAME               =");
					scanf("%s",accname);
					for(i=0;i<79;i++)
					printf("-");
					printf("\n\n\t\t\tTOTAL AMOUNT               =RS.17000\n");
					for(i=0;i<79;i++)
					printf("-");
					printf("\n Enter the amount=");
					fflush(stdin);
					m1=!scanf("%d",&amt);
					if(amt>17000||m==1||m1==1||amt<17000)
					{
						printf("\nEnter the correct details");
						delay(1000);
						continue;
					}
					clrscr();
					printf("\n\n\t\t\tDENOMINATIONS\n\n\n");
					printf("\n\t\tDenominations if the money is in that value enter 1 or else 0\n");
						printf("\n\n\t\t\tEnter it");
					printf("\n\t\t100x");
					fflush(stdin);
					x=!scanf("%d",&a);
					printf("\n\t\t500x");
					fflush(stdin);
					y=!scanf("%d",&b);
					printf("\n\t\t1000x");
					fflush(stdin);
					z=!scanf("%d",&c);
					if(x==1||y==1||z==1||(a*100+b*500+c*1000)!=17000)
					{
						printf("\n\t\tEnter correct denominations");
						delay(1000);
						continue;
					}
					else 	if((a*100+b*500+c*1000)==17000)
					{       if(ch2==1)
						{
							for(i=0;i<79;i++)
							printf("-");
							printf("\n\t\tTOTAL=Rs.17000\n");
							for(i=0;i<79;i++)
							printf("-");
							printf("\n\n\t\tThe fees has collected successfully");
							delay(2000);
							break;
						}
						
						else 	if(ch2==2)
						{
							for(i=0;i<79;i++)
							printf("-");
							printf("\n\t\tTOTAL=Rs.17000\n");
							for(i=0;i<79;i++)
							printf("-");
							printf("\n\t\tEnter name of recipient\t=");
							fflush(stdin);
							scanf("%s",colname);
							printf("\n\n\t\tPLEASE DEPOSIT THE CHECK IN OUR COLLEGE");
							delay(1000);
							break;
						}
					}
					default:break;
					
				}
				
			}
			break;
		}
		studetails();
	}
}
void revaluation()
{
	while(1)
	{
		int i,n1=0,n2=0,n3=0,n4=0,n5=0,ch4=1,k,rno,l,sub;
		clrscr();
		printf("\n\nEnter your roll number=");
		fflush(stdin);
		l=!scanf("%d",&rno);
		rno-=1;
		if(l==1)
		{
			printf("\n Enter the correct roll number ");
			delay(1000);
			continue;
		}
		if(rno<0||rno>1)
		{
			printf("\n Enter the correct roll number ");
			delay(1000);
			continue;
		}
		printf("Enter the subject \n\n\t\t\n\t\t1.\t\tcalculus\n\t\t2.\t\tapplied physics\n\t\t3.\t\tdigital electonics\n\t\t4.\t\tc programming\n\t\t5.\t\tenglish");
		fflush(stdin);
		printf("\n Enter The option=");
		k=!scanf("%d",&sub);
		if(k==1)
		{
			printf("\n Enter the correct roll number ");
			delay(1000);
			continue;
		}
		if(s1[rno].markscal<50)
		n1++;
		if(s1[rno].marksappl<50)
		n2++;
		if(s1[rno].marksdigi<50)
		n3++;
		if(s1[rno].marksc<50)
		n4++;
		if(s1[rno].markse<50)
		n5++ ;
		switch(sub)
		{
			case 1: clrscr();
			printf("\n\n\t\t Do you want to apply revaluation for caluculus");
				printf("\n\n\t\t1.To apply");
			printf("\n\n\t\t2.To exit");
			printf("\n\nEnter the option=");
			fflush(stdin);
			k=!scanf("%d",&ch4);
			if(ch4==2)
			break;
			if(k==1)
			{
				printf("\n\nEnter the option correctly");
				delay(1000);
				continue;
			}
			if(ch4==1)
			{
				if(n1>0)
				{
					n1*=1000;
					printf("\n\n\t\tThe cost for this is RS.%d",n1);
						printf("\n\n\t\tPlease pay it in our college");
					delay(2000);
					continue;
				}
				else
				{
					printf("\nYou have passed so no revaluation");
					delay(1000);
				}
			}
			else if(ch4==2)
			break;
			case 2:clrscr();
			printf("\n\n\t\t Do you want to apply revaluation for caluculus");
				printf("\n\n\t\t1.To apply");
			printf("\n\n\t\t2.To exit");
			printf("\n\nEnter the option=");
			fflush(stdin);
			k=!scanf("%d",&ch4);
			if(ch4==2)
			break;
			if(k==1)
			{
				printf("\n\nEnter the option correctly");
				delay(1000);
				continue;
			}
			if(ch4==1)
			{
				if(n2>0)
				{
					n2*=1000;
					printf("\n\n\t\tThe cost for this is RS.%d",n2);
						printf("\n\n\t\tPlease pay it in our college");
					delay(2000);
					continue;
				}
				else
				{
					printf("\nYou have passed so no revaluation");
					delay(1000);
				}
			}
			else if(ch4==2)
			break;
			case 3: clrscr();
			printf("\n\n\t\t Do you want to apply revaluation for caluculus");
				printf("\n\n\t\t1.To apply");
			printf("\n\n\t\t2.To exit");
			printf("\n\nEnter the option=");
			fflush(stdin);
			k=!scanf("%d",&ch4);
			if(ch4==2)
			break;
			if(k==1)
			{
				printf("\n\nEnter the option correctly");
				delay(1000);
				continue;
			}
			if(ch4==1)
			{
				if(n3>0)
				{
					n3*=1000;
					printf("\n\n\t\tThe cost for this is RS.%d",n3);
						printf("\n\n\t\tPlease pay it in our college");
					delay(2000);
					continue;
				}
				else
				{
					printf("\nYou have passed so no revaluation");
					delay(1000);
				}
			}
			else if(ch4==2)
			break;
			
			case 4: clrscr();
			printf("\n\n\t\t Do you want to apply revaluation for caluculus");
				printf("\n\n\t\t1.To apply");
			printf("\n\n\t\t2.To exit");
			printf("\n\nEnter the option=");
			fflush(stdin);
			k=!scanf("%d",&ch4);
			if(ch4==2)
			break;
			if(k==1)
			{
				
				printf("\n\nEnter the option correctly");
				delay(1000);
				continue;
			}
			if(ch4==1)
			{
				if(n4>0)
				{
					n4*=1000;
					printf("\n\n\t\tThe cost for this is RS.%d",n4);
						printf("\n\n\t\tPlease pay it in our college");
					delay(2000);
					continue;
				}
				else
				{
					printf("\nYou have passed so no revaluation");
					delay(1000);
				}
			}
			else if(ch4==2)
			break;
			
			case 5: clrscr();
			printf("\n\n\t\t Do you want to apply revaluation for caluculus");
				printf("\n\n\t\t1.To apply");
			printf("\n\n\t\t2.To exit");
			printf("\n\nEnter the option=");
			fflush(stdin);
			k=!scanf("%d",&ch4);
			if(ch4==2)
			break;
			if(k==1)
			{   	printf("\n\nEnter the option correctly");
				delay(1000);
				continue;
				
			}
			if(ch4==1)
			{
				if(n5>0)
				{
					n5*=1000;
					printf("\n\n\t\tThe cost for this is RS.%d",n5);
						printf("\n\n\t\tPlease pay it in our college");
					delay(2000);
					continue;
				}
				else
				{
					printf("\nYou have passed so no revaluation");
					delay(1000);
				}
			}
			else if(ch4==2)
			break;
			
			default:printf("\n Enter correct option");
			delay(1000);
			continue;
		}
		break;
	}
	studetails();
}
