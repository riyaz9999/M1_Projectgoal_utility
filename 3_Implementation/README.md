IMPLEMENTATION AND CODE:

#include<stdio.h>

#include<conio.h>

#include<string.h>

struct customer

{

 char name[20],address[100],proof[10];
 
 long int phno,idno;
 
};

int roombook(int *p,int *q,int *r);

void custdetails();

void billing(int choice);

int main()

{

 int t,t1,t2,choice;
 
 int *p,*q,*r;
 
 printf("\n get the no of rooms left");
 
 scanf("%d%d%d",&t,&t1,&t2);
 
 choice=roombook(&t,&t1,&t2);
 
 custdetails();
 
 billing(choice);
 
 return 0;
 
}

int roombook(int *p,int *q,int *r)

{

 int choice,search;
 
 printf("\n enter your choice");
 
 scanf("%d",&choice);
 
 while(*p!=0)
 
 {
 
 if(choice==1)
 
 {
 
 if(*q!=0)
 
 {
 
 printf("\n this type room available \n");
 
 *q--;
 
 search=1;
 
 break;
 
 }
 
 if(*q==0)
 
 {
 
 printf("\n sorry no room available");
 
 }
 
 else if(choice==2)
 
 {
 
 if(*r!=0)
 
 {
 
 printf("\n this type room available");
 
 *r--;
 
 search=2;
 
 }
 
 }
 
 if(*r==0)
 
 {
 
 printf("\n sorry no room available");
 
 }
 
 else
 
 {
 
 printf("\n no room of such type");
 
 }
 
 if((search==1)||(search==2))
 
 {
 
 *p=*p-1;
 
 }
 
 if(*p==0)
 
 {
 
 printf("\n no rooms available");
 
 }
 
 }
 
 return(choice);
 
}

void custdetails()

{

 struct customer c;
 
 printf("\n name of the customer \n");
 
 //gets(c.name);
 
 scanf("%id",&c.phno);
 
 printf("enter nation and idproof \n");
 
 scanf("%s%id",c.proof,&c.idno);
 
}

void billing(int choice)

{

 clrscr();
 
 int j,i[100],D,n,taxp;
 
 float c[100],resbill,roombill,sum=0,tbill;
 
 printf("enter no of days to be stayed \n");
 
 scanf("%d,&D");
 
 if(choice==1)
 
 {
 
 roombill=1000*D;
 
 }
 
 if(choice==2)
 
 {
 
 roombill=2500*D;
 
 }
 
 printf("enter no of items taken \n");
 
 scanf("%d",&n);
 
 for(j=1;j<=n;j++)
 
 {
 
 printf("%d\n\t\t",j);
 
 scanf("%f",&c[j]);
 
 }
 
 for(j=1;j<=n;j++)
 
 {
 
 sum=sum+c[j];
 
 }
 
 printf("enter tax percentage \n");
 
 scanf("%d",&taxp);
 
 resbill=sum+((sum*taxp)/100);
 
 tbill=roombill+resbill;
 
 printf("total bill is %f",tbill);
 
}
