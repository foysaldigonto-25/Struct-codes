# Struct-codes:

1.
#include <i.ostream>
<br>
using namespace std;

struct teacher {

    string name;
    int id;
    double salary;

    void setAll(string n, int i, double s) {
        name = n;
        id = i;
        salary = s;
    }

    void setName(string n) {
        name = n;
    }

    void setId(int i) {
        id = i;
    }

    void setSalary(double s) {
        if (s > 0) {
            salary = s;
        } else {
            cout << "Invalid" << endl;
        }
    }

    string getName() {
        return name;
    }

    int getId() {
        return id;
    }

    double getsSalary() {
        return salary;
    }

    void display() {
        cout << "Name :" << name << endl;
        cout << "ID :" << id << endl;
        cout << "Salary :" << salary << endl;
    }

    double yearlySalary() {
        return salary * 12;
    }

    double yearlySalaryWithBonus() {
        double bonus = (salary * 0.60) * 2;
        return yearlySalary() + bonus;
    }

    double taxOnYearlySalary() {
        double total = yearlySalaryWithBonus();
        if (total > 400000) {
            double tax = total * 0.15;
            total -= tax;
        }
        return total;
    }
};

int main() {
<br>
    teacher t;

    string name;
    int id;
    double salary;

    cout << "Enter name :";
    cin >> name;
    t.setName(name);

    cout << "Enter Id :";
    cin >> id;
    t.setId(id);

    cout << "Enter Salary :";
    cin >> salary;
    t.setSalary(salary);

    cout << "\nTeacher's Info:\n" << endl;
    t.display();

    cout << "\nYearly salary (without bonus): " << t.yearlySalary() << endl;
    cout << "Yearly salary (with bonus): " << t.yearlySalaryWithBonus() << endl;
    cout << "Yearly salary after tax (if applicable): " << t.taxOnYearlySalary() << endl;

    return 0;
}
