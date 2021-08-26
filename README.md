#include<string.h>
#include<stdio.h>
#include<conio.h>
int total(int a,int b,int c){
return a+b+c;
}
float avg(int a,int b,int c){
return (a+b+c)/3.0;
}
char *res(int a,int b,int c){
float avg=(a+b+c)/3.0;
if(avg<50) return "failed";
else
return "passed";
}
char grade(int a,int b,int c){
float avg=(a+b+c)/3.0;
if(avg<50) return 'F';
else if(avg<60) return 'E';
else if(avg<70) return 'D';
else if(avg<80) return 'C';
else if(avg<90) return 'B';
else return 'A';
}
main(){
int c=0,count=0,i,n,j,id[20],cpro[20],eng[20],math[20],index[20];
char name[20][30],sex[20],tmp1,tmp2[30];
float tmp;

printf("input n:\n"); scanf("%d",&n);
for(i=0;i<n;i++)
{
	index[i]=index[i]+1;
printf("======students %d=======\n",i+1);
printf("id: "); scanf("%d",&id[i]);
printf("name: "); fflush(stdin); gets(name[i]);
printf("sex: ");  scanf("%c",&sex[i]);
printf("cpro: "); scanf("%d",&cpro[i]);
printf("english: "); scanf("%d",&eng[i]);
printf("math: "); scanf("%d",&math[i]);
}
A:
clrscr();
puts("1. view all students data");
puts("2. sort average students by descending");
puts("3. unsort student data");
puts("4. sort by students by A to Z");
puts("5. showing only passed students");
puts("6. showing only failed students");
puts("7. counting failed students");
puts("8. counting passed students");
puts("9. deleting students");
puts("a. inserting name by location");
puts("b. adding students");
puts("c. updating student");
puts("0. exited");
switch(getch()){
	case '1':
   			puts("id\tname\tsex\tcpro\tenglish\tmath\ttotal\taverage\tresult\tgrade");
   			for(i=0;i<n;i++)
            {
            	printf("%d\t",id[i]);
               printf("%s\t",name[i]);
               printf("%c\t",sex[i]);
               printf("%d\t",cpro[i]);
               printf("%d\t",eng[i]);
               printf("%d\t",math[i]);
               printf("%d\t",total(cpro[i],eng[i],math[i]));
               printf("%.2f\t",avg(cpro[i],eng[i],math[i]));
               printf("%s\t",res(cpro[i],eng[i],math[i]));
               printf("%c\n",grade(cpro[i],eng[i],math[i]));
            }

            getch();  break;
   case '2':
   			for(i=0;i<n-1;i++)
            for(j=i+1;j<n;j++)
            if(avg(cpro[i],eng[i],math[i])<avg(cpro[j],eng[j],math[j])){
   			//tmp=index[i];
            //index[i]=index[j];
            //tmp=index[j];
            //for ID
            tmp=id[i];
            id[i]=id[j];
            id[j]=tmp;
            //cpro
            tmp=cpro[i];
            cpro[i]=cpro[j];
            cpro[j]=tmp;
            //math
            tmp=math[i];
            math[i]=math[j];
            math[j]=tmp;
            //english
            tmp=eng[i];
            eng[i]=eng[j];
            eng[j]=tmp;
            //sex
            tmp1=sex[i];
            sex[i]=sex[j];
            sex[j]=tmp1;
            //name
            strcpy(tmp2,name[i]);
            strcpy(name[i],name[j]);
            strcpy(name[j],tmp2);
				   }

            puts("id\tname\tsex\tcpro\tenglish\tmath\ttotal\taverage\tresult\tgrade");
   			for(i=0;i<n;i++)
             {
            	printf("%d\t",id[i]);
               printf("%s\t",name[i]);
               printf("%c\t",sex[i]);
               printf("%d\t",cpro[i]);
               printf("%d\t",eng[i]);
               printf("%d\t",math[i]);
               printf("%d\t",total(cpro[i],eng[i],math[i]));
               printf("%.2f\t",avg(cpro[i],eng[i],math[i]));
               printf("%s\t",res(cpro[i],eng[i],math[i]));
               printf("%c\n",grade(cpro[i],eng[i],math[i]));
             }
            	getch();
            	break;

           case '3':
                     for(i=0;i<n-1;i++)
                     for(j=i+1;j<n;j++)
                     if(id[i]>id[j]){
                              //for ID
            tmp=id[i];
            id[i]=id[j];
            id[j]=tmp;
            //cpro
            tmp=cpro[i];
            cpro[i]=cpro[j];
            cpro[j]=tmp;
            //math
            tmp=math[i];
            math[i]=math[j];
            math[j]=tmp;
            //english
            tmp=eng[i];
            eng[i]=eng[j];
            eng[j]=tmp;
            //sex
            tmp1=sex[i];
            sex[i]=sex[j];
            sex[j]=tmp1;
            //name
            strcpy(tmp2,name[i]);
            strcpy(name[i],name[j]);
            strcpy(name[j],tmp2);
				   }

            puts("id\tname\tsex\tcpro\tenglish\tmath\ttotal\taverage\tresult\tgrade");
   			for(i=0;i<n;i++)
             {
            	printf("%d\t",id[i]);
               printf("%s\t",name[i]);
               printf("%c\t",sex[i]);
               printf("%d\t",cpro[i]);
               printf("%d\t",eng[i]);
               printf("%d\t",math[i]);
               printf("%d\t",total(cpro[i],eng[i],math[i]));
               printf("%.2f\t",avg(cpro[i],eng[i],math[i]));
               printf("%s\t",res(cpro[i],eng[i],math[i]));
               printf("%c\n",grade(cpro[i],eng[i],math[i]));
              }
            getch();
            break;
            case '4': 	for(i=0;i<n-1;i++)
            				for(j=i+1;j<n;j++)
                        if(stricmp(name[i],name[j])>0){
                                     //for ID
                        tmp=id[i];
                        id[i]=id[j];
            				id[j]=tmp;
            				//cpro
            				tmp=cpro[i];
            				cpro[i]=cpro[j];
            				cpro[j]=tmp;
            				//math
            				tmp=math[i];
            				math[i]=math[j];
           					math[j]=tmp;
            				//english
            				tmp=eng[i];
            				eng[i]=eng[j];
            				eng[j]=tmp;
            				//sex
            				tmp1=sex[i];
            				sex[i]=sex[j];
            				sex[j]=tmp1;
            				//name
            				strcpy(tmp2,name[i]);
            				strcpy(name[i],name[j]);
            				strcpy(name[j],tmp2);
				   			}

            				puts("id\tname\tsex\tcpro\tenglish\tmath\ttotal\taverage\tresult\tgrade");
           		for(i=0;i<n;i++)
             {
            	printf("%d\t",id[i]);
               printf("%s\t",name[i]);
               printf("%c\t",sex[i]);
               printf("%d\t",cpro[i]);
               printf("%d\t",eng[i]);
               printf("%d\t",math[i]);
               printf("%d\t",total(cpro[i],eng[i],math[i]));
               printf("%.2f\t",avg(cpro[i],eng[i],math[i]));
               printf("%s\t",res(cpro[i],eng[i],math[i]));
               printf("%c\n",grade(cpro[i],eng[i],math[i]));
              }
            getch();
            break;
   	case '5':	puts("id\tname\tsex\tcpro\tenglish\tmath\ttotal\taverage\tresult\tgrade");
      			for(i=0;i<n;i++)
             	{
             	if(avg(cpro[i],eng[i],math[i])>50){
            	printf("%d\t",id[i]);
               printf("%s\t",name[i]);
               printf("%c\t",sex[i]);
               printf("%d\t",cpro[i]);
               printf("%d\t",eng[i]);
               printf("%d\t",math[i]);
               printf("%d\t",total(cpro[i],eng[i],math[i]));
               printf("%.2f\t",avg(cpro[i],eng[i],math[i]));
               printf("%s\t",res(cpro[i],eng[i],math[i]));
               printf("%c\n",grade(cpro[i],eng[i],math[i]));
               }
					}

				getch();
            break;
            case '6':	puts("id\tname\tsex\tcpro\tenglish\tmath\ttotal\taverage\tresult\tgrade");
   			for(i=0;i<n;i++)
             {
             	if(avg(cpro[i],eng[i],math[i])<50){
            	printf("%d\t",id[i]);
               printf("%s\t",name[i]);
               printf("%c\t",sex[i]);
               printf("%d\t",cpro[i]);
               printf("%d\t",eng[i]);
               printf("%d\t",math[i]);
               printf("%d\t",total(cpro[i],eng[i],math[i]));
               printf("%.2f\t",avg(cpro[i],eng[i],math[i]));
               printf("%s\t",res(cpro[i],eng[i],math[i]));
               printf("%c\n",grade(cpro[i],eng[i],math[i]));
               }
              }
				getch();
            break;
        	case '7':
         				for(i=0;i<n;i++){
                     if(avg(cpro[i],eng[i],math[i])<50)
                     count=count+1;
                     }
                     printf("=========there are/is %d failed",count);
                     getch();

         case '8':   clrscr();
         				for(i=0;i<n;i++){
                     if(avg(cpro[i],eng[i],math[i])>50)
                     c=c+1;
                     }
                     printf("=========there are/is %d passed",c);
                     getch();
                     break;
         case '9': int s;
         printf("input  id for deleted:\n"); scanf("%d",&s);
                for(i=0;i<n;i++)
                if(id[i]==s){
                n=n-1;
                for(j=i;j<n;j++)
                {
                id[j]=id[j+1];
                math[j]=math[j+1];
                cpro[j]=cpro[j+1];
                eng[j]=eng[j+1];
                strcpy(name[j],name[j+1]);
                }
                i--;
                puts("students has been deleted");
                }
                getch(); break;
         case 'a': int a,d,e,f,j,loc;
         				char k[20][30],b;
         			printf("id: "); scanf("%d",&a);
						printf("name: "); fflush(stdin); gets(k[30]);
						printf("sex: ");  scanf("%c",&b);
						printf("cpro: "); scanf("%d",&c);
						printf("english: "); scanf("%d",&d);
						printf("math: "); scanf("%d",&e);
						printf("input location\n");  scanf("%d",&loc);
						for(i=n;i>=loc-1;i--){
						id[i]=id[i-1];
   					strcpy(name[i],name[i-1]);
   					sex[i]=sex[i-1];
   					cpro[i]=cpro[i-1];
   					eng[i]=eng[i-1];
   					math[i]=math[i-1];
						avg(cpro[i],math[i],eng[i])==avg(cpro[i-1],math[i-1],eng[i-1]);

						}
						id[loc-1]=a;
						strcpy(name[loc-1],k[30]);
						sex[loc-1]=b;
						cpro[loc-1]=c;
						eng[loc-1]=d;
						math[loc-1]=e;
                  avg(cpro[loc-1],eng[loc-1],math[loc-1])==avg(c,d,e);
						n++;
						 puts("id\tname\tsex\tcpro\tenglish\tmath\ttotal\taverage\tresult\tgrade");
					for(i=0;i<n;i++)
					{
            	printf("%d\t",id[i]);
               printf("%s\t",name[i]);
               printf("%c\t",sex[i]);
               printf("%d\t",cpro[i]);
               printf("%d\t",eng[i]);
               printf("%d\t",math[i]);
               printf("%d\t",total(cpro[i],eng[i],math[i]));
               printf("%.2f\t",avg(cpro[i],eng[i],math[i]));
               printf("%s\t",res(cpro[i],eng[i],math[i]));
               printf("%c\n",grade(cpro[i],eng[i],math[i]));
            	}
				getch();
				break;
 case 'b':  clrscr(); int m;
 				printf("input m: "); scanf("%d",&m);
            for(i=n;i<m+n;i++)
            {
            printf("======student[%d]=======\n",i+1);
            printf("id: "); scanf("%d",&id[i]);
				printf("name: "); fflush(stdin); gets(name[i]);
				printf("sex: ");  scanf("%c",&sex[i]);
				printf("cpro: "); scanf("%d",&cpro[i]);
				printf("english: "); scanf("%d",&eng[i]);
            printf("math: "); scanf("%d",&math[i]);
         	}
         	clrscr();
         	puts("id\tname\tsex\tcpro\tenglish\tmath\ttotal\taverage\tresult\tgrade");
            for(i=0;i<m+n;i++)
         	{

            	printf("%d\t",id[i]);
               printf("%s\t",name[i]);
               printf("%c\t",sex[i]);
               printf("%d\t",cpro[i]);
               printf("%d\t",eng[i]);
               printf("%d\t",math[i]);
               printf("%d\t",total(cpro[i],eng[i],math[i]));
               printf("%.2f\t",avg(cpro[i],eng[i],math[i]));
               printf("%s\t",res(cpro[i],eng[i],math[i]));
               printf("%c\n",grade(cpro[i],eng[i],math[i]));
            }
            getch(); break;
 	case 'c':

               printf("========input for updating======= ");
               	printf("id: "); scanf("%d",&a);
						printf("name: "); fflush(stdin); gets(k[30]);
						printf("sex: ");  scanf("%c",&b);
						printf("cpro: "); scanf("%d",&c);
						printf("english: "); scanf("%d",&d);
						printf("math: "); scanf("%d",&e);
						printf("input location");  scanf("%d",&loc);
               for(i=0;i<n;i++)
               if(id[i]==loc)
               {
               id[i]=a;
               strcpy(name[i],k[30]);
               sex[i]=b;
               cpro[i]=c;
               eng[i]=d;
               math[i]=e;
               avg(cpro[i],math[i],eng[i])==avg(c,d,e);
               }
                        	puts("id\tname\tsex\tcpro\tenglish\tmath\ttotal\taverage\tresult\tgrade");
            for(i=0;i<m+n;i++)
         	{

            	printf("%d\t",id[i]);
               printf("%s\t",name[i]);
               printf("%c\t",sex[i]);
               printf("%d\t",cpro[i]);
               printf("%d\t",eng[i]);
               printf("%d\t",math[i]);
               printf("%d\t",total(cpro[i],eng[i],math[i]));
               printf("%.2f\t",avg(cpro[i],eng[i],math[i]));
               printf("%s\t",res(cpro[i],eng[i],math[i]));
               printf("%c\n",grade(cpro[i],eng[i],math[i]));
            }
            getch(); break;
        } goto A;
        }
