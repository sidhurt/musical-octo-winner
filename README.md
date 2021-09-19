# musical-octo-winner
MCGM want to prepare the list of doctor area wise to assign the duty to take care of patients. In order to prepare the list, computer operator enter the name of doctor and area. Finally, this list is sorted area wise, system uses operator overloading concept (function) to compare the area.

#include<iostream>
#include<string.h>
using namespace std;
class Doctor
{
public:
    char name[30];
    char area[10];
    void read()
 {
 cout<<"Name: ";
 cin>>name;
 cout<<"Area: ";
 cin>>area;
 }
int operator <(Doctor d)

{
    if(strcmp(name,d.name)>0)
return 1;
else
return 0;
}
  void displaylist()
    {
        cout<<name<<" "<<area<<endl;
    }
};
int main()
{
  Doctor d1[2];
  Doctor temp;
    for(int i=0;i<2;i++)
        {
            d1[i].read();
        }
for(int i = 0; i <2; i++)
    {
        for(int j = 0; j <1-i; j++)
        {
            if(d1[j]<d1[j+1])
            {
                temp=d1[j];
                d1[j]=d1[j+1];
                d1[j+1]=temp;
            }
        }
    }
     for(int i=0;i<2;i++)
    {
        d1[i].displaylist();
    }
 }

