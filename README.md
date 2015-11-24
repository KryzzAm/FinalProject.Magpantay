#include <cstdlib>
#include <iostream>
#include <string>
#include <fstream>
#include<conio.h>

using namespace std;

//Global
int AMT,SRP;
string ClientName;
string Address;
string Age;
string CivStat;
string carname;

//Structures
struct Clientinfo;

//Function Prototypes
void officialreceipt();
void createprofile();
void LoadClientProfile();
void DisplayClientProfile();
void editprofile();
void CarProfile();
void Purchase();
void Menu();
void deleteprofile();
void searchprofile();
void transaction();

//-----------------------------------------------------------------------------------------------------

int main () 
{
    system("color f1");
	int CHOICE;
do{

        printf("\n\t Welcome to Car Dealership Management System v1.0  \n");
		printf("\n\t-----------------------MAIN MENU----------------------");
		printf("\n\t|                                                     |");
		printf("\n\t|                 [1] Client Profile                  |");
		printf("\n\t|                 [2] Car Profile                     |");
		printf("\n\t|                 [3] Create Purchase                 |");
		printf("\n\t|                 [4] Quit                            |");
		printf("\n\t|                                                     |");
		printf("\n\t-------------------------------------------------------\n\n\t");
		scanf("%d",&CHOICE);

		switch (CHOICE) {

			case 1 :
			{
				int choice;

			system ("cls");
			do{
			
			printf("-----------------------------\n");
			printf("\n|  [1] CREATE PROFILE       |\n");
			printf("\n|  [2] SEARCH PROFILE       |\n");
			printf("\n|  [3] BACK TO HOMESCREEN   |\n");
			printf("-----------------------------");
			printf("\n Enter your Choice here: ");
			scanf("%d",&choice);

			switch (choice){

				case 1:createprofile();break;
				case 2:searchprofile();break;
			}
		}while(choice!=3);


			
			}
			break;
			case 2 : CarProfile();
			break;
			case 3:transaction();
			break;
			
		}
	}while(CHOICE!=4);
	system ("PAUSE");
	return 0;
}
//-------------------
struct Clientinfo
	{
		int patient_num;
		string fname;
		string lname;
        int age;
		char gender;
		string CivStat;
		string loc;
        int IDno;
    } Clientinfo[50];
//----------------------------

//----------------------------------------------------------------------------------------------------------------
void createprofile()
{
    ifstream inFile;
	ofstream newclient;
	newclient.open("newclient.txt",ios::app);
	int a=0, IDno,ans,o;
	char m,n,p,q,r,s;

		
        printf("Identification No.: ");
		scanf("%d",&s);
		Clientinfo[a].IDno=s;
        printf("First Name         : ");
		scanf("%s",&m);
		Clientinfo[a].fname=m;
        printf("Last Name          : ");
		scanf("%s",&n);
		Clientinfo[a].lname=n;
        printf("Age                : ");
		scanf("%d",&o);
		Clientinfo[a].age=o;
		printf("Location           : ");
		scanf("%s",&p);
		Clientinfo[a].loc=p;
		printf("Gender             : ");
		scanf("%s",&q);
		Clientinfo[a].gender=q;
        printf("Civil Status       : ");
		scanf("%s",&r);
		Clientinfo[a].CivStat=r;
	



}

//------------------------------------------------------------------------------------------------------------------
void searchprofile(){
	 ifstream inFile;
	ofstream newclient;
	newclient.open("newclient.txt",ios::app);
	int a=0,IDno,locate,Name,ans;
	IDno=11415134;
	printf("\nEnter ID No to search: ");
                  scanf("%s", &Name);
                  if (IDno==Name)
                    printf("\nId no %s located.", Name);
                    
                  else
                    printf("\nId no %s not located.", Name);
}



//----------------------------------------------------------------------------------------------------------------
void CarProfile()
{
    char findx;
	string details;
	ifstream CarProfile;
	CarProfile.open("carprofile.txt");
	system("CLS");
	cout<<endl;
	while(!CarProfile.eof())
	{
		getline(CarProfile,details);
		cout<<details<<endl;
	}
}
//-----------------------------------------------------------------------------------------------------------------
void transaction()
{
	string zz,n,xx,h;
	int x;
	double y,g,f,a[20]={2800000,6351822,1800000,1259196,1300000,1107497,1300000,1600000,1800000,1400000,1500000,1500000,1200000,1950369,1565700,788510,1430000,1900000,1150500,177530};
	ofstream newclient("newclient.txt", ios::app);
	ifstream e;
	e.open("carprofile.txt");
	system("CLS");
	cout<<endl;
	while(!e.eof())
	{
		getline(e,zz);
		cout<<zz<<endl;
	}
	e.close();
	printf("Enter Chassis No. of Car: [1 to 20]: ");
	scanf("%d",&x);

	printf("\n\nThe price of car is %0.2lf",a[x-1]);
	printf("\n\n Enter Amount of Payment:  ");
	scanf("%lf",&f);
	g=f-a[x-1];
	if(f<a[x-1])
	printf("\n\n\tInsufficient amount!!");
	else
	printf("\nChange is %0.2lf",g);



	printf("============================================================================\n");
	printf("                              CAR DETAILS                                   \n");
    printf("Car Details     Chassis No.       Brand         Model           SRP         \n");
     char findx;
	string details;
	ifstream CarProfile;
	CarProfile.open("carprofile.txt");
	cout<<endl;
	while(!CarProfile.eof())
	{
		getline(CarProfile,details);
		cout<<details<<endl;
	}
    printf("                    %d                                        %0.2lf\n",x,a[x-1]);
    printf("                                         Amount Tendered:    %0.2lf\n",f);
    printf("                                         Change         :    %0.2lf\n",g);
    printf("____________________________________________________________________________\n");

}

//-----------------------------

