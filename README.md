# tugas-5-adp

phyton
print("Nama: Daffa Dhiya Ulhaq")
print("Nim : 2310431005")
print("TABEL FUNGSI")
print("f(x) = 3x² + 7x - 2, jika x >= 0")
print("     = 2x² - 5x - 4, jika x < 0")
print("g(x) = (f(x))² - √f(x)")
print("h(x) = f(x) * g(x)")

while True:
    n = int(input("\nInput banyak data n = "))
    nilai_x = [float(input(f"Input nilai x ke-{i+1} = ")) for i in range(n)]

    print("\nHasil:")
    
    column_width = 12
    column_titles = ["x", "f(x)", "g(x)", "h(x)"]
    total_width = 4 * column_width + 5  # 4 kolom, 1 space untuk setiap kolom dan 1 untuk pemisah "|" di akhir

    print("+" + "-" * (total_width - 2) + "+")

    print("|", end="")
    for title in column_titles:
        print(f" {title:<{column_width}} |", end="")
    print()  
    print("+" + "-" * (total_width - 2) + "+")

    for x in nilai_x:
        if x >= 0:
            fx = 3*x**2 + 7*x - 2
        else:
            fx = 2*x**2 - 5*x - 4

        gx = fx**2 - (fx ** 0.5)
        hx = fx * gx

        
        print("|", end="")
        print(f" {x:<{column_width}.2f} |", end="")
        print(f" {fx:<{column_width}.2f} |", end="")
        print(f" {gx:<{column_width}.2f} |", end="")
        print(f" {hx:<{column_width + 8}.2f} |")  
    print("+" + "-" * (total_width - 2) + "+")

    lagi = input("\nIngin memasukkan nilai x lagi? (Y/N) ")
    if lagi != 'Y' and lagi != 'y':
        print("Terima kasih telah menggunakan program ini.")
        break


C++
#include <iostream>
#include <cmath>
#include <iomanip> // Untuk setprecision dan setw

using namespace std;

double fungsi_f(double x) {
    if (x >= 0) {
        return 3 * pow(x, 2) + 7 * x - 2;
    } else {
        return 2 * pow(x, 2) - 5 * x - 4;
    }
}

double fungsi_g(double x) {
    double fx = fungsi_f(x);
    return pow(fx, 2) - sqrt(fx);
}

double fungsi_h(double x) {
    double fx = fungsi_f(x);
    double gx = fungsi_g(x);
    return fx * gx;
}

int main() {
    cout << "TABEL FUNGSI" << endl;
    cout << "f(x) = 3x^2 + 7x - 2, jika x >= 0" << endl;
    cout << "     = 2x^2 - 5x - 4, jika x < 0" << endl;
    cout << "g(x) = (f(x))^2 - √f(x)" << endl;
    cout << "h(x) = f(x) * g(x)" << endl;

    while (true) {
        int n;
        cout << "\nInput banyak data n = ";
        cin >> n;

        double nilai_x[n];
        for (int i = 0; i < n; ++i) {
            cout << "Input nilai x ke-" << i + 1 << " = ";
            cin >> nilai_x[i];
        }

        cout << "\nHasil:\n";

        int column_width = 12;
        string column_titles[] = {"x", "f(x)", "g(x)", "h(x)"};
        int total_width = 4 * column_width + 5;  // 4 kolom, 1 space untuk setiap kolom dan 1 untuk pemisah "|" di akhir

        cout << "+" << string(total_width - 2, '-') << "+" << endl;

        cout << "|";
        for (const string& title : column_titles) {
            cout << " " << title << string(column_width - title.size(), ' ') << " |";
        }
        cout << endl;

        cout << "+" << string(total_width - 2, '-') << "+" << endl;

        for (int i = 0; i < n; ++i) {
            double x = nilai_x[i];
            double fx = fungsi_f(x);
            double gx = fungsi_g(x);
            double hx = fungsi_h(x);

            cout << "| " << fixed << setprecision(2) << setw(column_width) << x << " | ";
            cout << fixed << setprecision(2) << setw(column_width) << fx << " | ";
            cout << fixed << setprecision(2) << setw(column_width) << gx << " | ";
            cout << fixed << setprecision(2) << setw(column_width + 8) << hx << " |" << endl;
        }
        cout << "+" << string(total_width - 2, '-') << "+" << endl;

        char lagi;
        cout << "\nIngin memasukkan nilai x lagi? (Y/N) ";
        cin >> lagi;
        if (lagi != 'Y' && lagi != 'y') {
            cout << "Terima kasih telah menggunakan program ini." << endl;
            break;
        }
    }

    return 0;
}
