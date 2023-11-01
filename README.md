// Considering that in 100% weightage ( " 5% for attendance(total delivered 70 ), 25% for CA's (out of 30 marks), 20% for MTE (out of 30 marks), 50% for ETE (out of 60 marks) " )

#include<iostream>
#include<string>
#include<stdlib.h>
using namespace std;
int total_delivered  = 70;
class student_details
{
    protected:
    string name;
    int roll_no;
    public:
    void fun()
    {
        cout<<"Enter the details of a Student \n";
        cout<<"Enter Name of Student : ";
        getline(cin,name);
        cout<<"Enter Roll no. : ";
        cin>>roll_no;
    }
};
class attendance
{
    protected:
    float attendance_marks;
    float total_attented;
    float avg_attendance;
    public:
    void fun()
    {
        cout<<"Enter Total Lecture Attented : ";
        cin>>total_attented;
        avg_attendance = (total_attented/total_delivered)*100;
        // cout<<avg_attendance<<endl;
        if(avg_attendance>=75)
        {
            if(avg_attendance<=80)
                {
                    attendance_marks = 1;
                }
                else if(avg_attendance>80 && avg_attendance<=85)
                {
                    attendance_marks = 2;
                }
                else if(avg_attendance>85 && avg_attendance<=90)
                {
                    attendance_marks = 3;
                }
                else if(avg_attendance>90 && avg_attendance<=95)
                {
                    attendance_marks = 4;
                }
                else if(avg_attendance>95 && avg_attendance<=100)
                {
                    attendance_marks = 5;
                }
        }
        else
        {
            cout<<endl<<"\t Not Eligible To Sit In Exam !!! ";
            cout<<endl<<"\tRegister for Backlog !!!!"<<endl<<endl;
            exit(0);
        }
    }
};
class ca
{
    protected:
    float ca1,ca2,ca3;
    int ca_marks;
    float max_marks1,max_marks2;
    public:
    void fun()
    {
        cout<<"Enter CA_1 Marks : ";
        cin>>ca1;
        cout<<endl<<"Enter CA_2 Marks : ";
        cin>>ca2;
        cout<<endl<<"Enter CA_3 Marks : ";
        cin>>ca3;
        cout<<endl;
        top_2();
        calcu();
    }
    void top_2()
    {
        if(ca1>=ca2 && ca1>=ca3)
        {
            max_marks1 = ca1;
            if(ca2>=ca3)
            {
                max_marks2 = ca2;
            }
            else
            {
                max_marks2 = ca3;
            }
        }
        else if(ca2>=ca1 && ca2>=ca3)
        {
            max_marks1 = ca2;
            if(ca1>=ca3)
            {
                max_marks2 = ca1;
            }
            else
            {
                max_marks2 = ca3;
            }
        }
        else
        {
            max_marks1 = ca3;
            if(ca2>=ca1)
            {
                max_marks2 = ca2;
            }
            else
            {
                max_marks2 = ca1;
            }
        }
    }
    void calcu()
    {
        ca_marks = ((max_marks1+max_marks2)/60)*25;
    }
};
class mte
{
    protected:
    float mte;
    int mte_marks;
    public:
    void fun()
    {
        cout<<"Enter MTE Marks : ";
        cin>>mte;
        mte_marks = ((mte/30)*20);
    }
};

class ete
{
    protected:
    float ete;
    int ete_marks;
    public:
    void fun()
    {
        cout<<endl<<"Enter ETE Marks : ";
        cin>>ete;
        ete_marks = ((ete/60)*50);
    }
};
class final_result:public student_details , public attendance , public ca , public ete , public mte 
{
    protected:
    int total_weightage;
    string o = " O ";
    string a1 = " A+ ";
    string a2 =" A ";
    string b1 = " B+ ";
    string b2 =" B ";
    string c1 = " C+ ";
    string c2 =" C ";
    string d1 = " D+ ";
    string d2 =" D ";
    string e =" E ";
    public:
    void get()
    {
        student_details::fun();
        attendance::fun();
        
            ca::fun();
            mte::fun();
            ete::fun();
            total_weightage = (attendance_marks+ca_marks+mte_marks+ete_marks);
            show();
            grade();
    }
    void show()
    {
        cout<<endl<<endl<<"\t Name : "<<name<<endl;
        cout<<"\t Roll : "<<roll_no<<endl;
        cout<<"\t Marks In Weightage "<<endl;
        cout<<"\t Attendance : "<<attendance_marks<<endl;
        cout<<"\t CA : "<<ca_marks<<endl;
        cout<<"\t MTE : "<<mte_marks<<endl;
        cout<<"\t ETE : "<<ete_marks<<endl;
        cout<<"\t Total Weightage : "<<total_weightage<<endl;
    }
    void grade()
    {
        if(total_weightage<=100 && total_weightage>=95)
        {
            cout<<"\t Grade "<<o;
        }
        else if(total_weightage<95 && total_weightage>=90)
        {
            cout<<"\t Grade "<<a1;
        }
        else if(total_weightage<90 && total_weightage>=85)
        {
            cout<<"\t Grade "<<a2;
        }
        else if(total_weightage<85 && total_weightage>=80)
        {
            cout<<"\t Grade "<<b1;
        }
        else if(total_weightage<80 && total_weightage>=75)
        {
            cout<<"\t Grade "<<b2;
        }
        else if(total_weightage<75 && total_weightage>=70)
        {
            cout<<"\t Grade "<<c1;
        }
        else if(total_weightage<70 && total_weightage>=65)
        {
            cout<<"\t Grade "<<c2;
        }
        else if(total_weightage<65 && total_weightage>=60)
        {
            cout<<"\t Grade "<<d1;
        }
        else if(total_weightage<60 && total_weightage>=40)
        {
            cout<<"\t Grade "<<d2;
        }
        else if(total_weightage<55 && total_weightage>=40)
        {
            cout<<"\t Grade "<<e<<endl;
            cout<<"Reapeared log !! "<<endl;
        }
    }
};
int main()
{
    final_result obj;
    obj.get();
    return 0;
}
