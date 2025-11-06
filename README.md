
#include <iostream> 
#include <fstream>
#include <string>
using namespace std; 
 
class Person
{
protected:     string name, gender;     int age; public: 
    void getData() 
    {       
    cout << "Enter name: "; cin >> name;  
    cout << "Enter gender: "; cin >> gender; 
    cout << "Enter age: "; cin >> age; 
    } 
    void showData() 
    {        
    cout << "Name: " << name << "\nGender: " << gender << "\nAge: " << age << endl; 
    } 
    string getName()
    {
    return name;
    }    
    string getGender() 
    {
    return gender; 
    }   
    int getAge()
    { 
    return age;
    } 
}; 
 
class Patienthttps:
 public: Person 
{    
string disease;
public: 
    void getPatientData() 
    {   
    getData(); 
    cout << "Enter disease: "; 
    cin >> disease; 
    } 
    void displayPatient() 
    {         
    showData();     
    cout << "Disease: " << disease << endl; 
    } 
    string getDisease()
   
    { 
    return disease;
    } 
}; 
 
class Hospital 
{
public: 
    void savePatient(Patient &p)
    {        
    ofstream file("patients.txt", ios::app);
    file << p.getName() << "," << p.getGender() << ","      
    << p.getAge() << "," << p.getDisease() << "\n";       
    file.close(); 
        cout << "  Patient record saved successfully!\n"; 
    } 
}; 
int main() 
{    
Patient p; 
Hospital h;    
int choice; 
 
    cout << "\n=== Hospital Management System ===\n";     
    cout << "1. Add Patient\n2. Display Patient\n3. Save Patient to File\n4. Exit\n"; 
 
    do 
    {         cout << "\nEnter your choice: ";  
    cin >> choice;       
    switch (choice) 
    {          
    case 1: 
    
                p.getPatientData();       
                break;           
                case 2: 
                cout << "\n--- Patient Details ---\n";    
                p.displayPatient();                 
                break;          
                case 3: 
                h.savePatient(p);            
                break;       
                case 4:            
                cout << "Exiting...\n";       
                break;             default: 
                cout << "Invalid choice!\n"; 
        } 
    }
    while (choice != 4); 
 
    return 0; 
} 
 
