/** 
 1. Создайте подобный класу Vetor из задания С3_1 класс Vetor2. Элементы данных нового класа
 пусть полностю совпадают с данными класса VEctor а методов достаточно
 релизовать только конструкторы.
 Напишите функцию, которая в качестве входных парамметров принимает две константные ссылки:
    на объект класса Vector
    на объект класса Vector 2
Эта функция должна выводить на экран больший из элементов Х двух объектов
и больший из элементов У
2. Напишите программу, в которой создайте векторр класса Vector и вектор класса Vector2.
с помощью нашей функции выведете на экран большие по значению элементы этих векторов
примечание class Vector;
 */ 
*.cpp linguist-обнаруживаемый=true
        #include <iostream>
        #include <cmath>
        #include <vector>
        using namespace std;

        class Vector
       {

          public:
           int x,y;
        // friend void fun (const Vector&v1, const Vector2&v2 );
          int p_x,p_y;
       Vector(int p_x,int p_y, int initx =0,int inity = 0 ) :  p_x(initx), p_y(inity) { cout << "222Object created2222\n"<< endl;}; // Конструктор
       ~Vector() // Деструктор всего классса vector
       {
        cout << "Object deleted\n";
       }
       double getp_x() { return x; }
       double getp_y() { return y; }
       void Set(double p_x, double p_y)
       {
        cout << "Enter coordinates.\nx = ";
        cin >> p_x;
        cout << "y = ";
        cin >> p_y;
        x = p_x; y = p_y;
         }
         void Show()
       {
         cout << "x = " << x << ", y = " << y << '\n';
             }

       };


       class Vector2
       {
       public:
       double x,y;
       int a;
       int b;
       friend void fun (const Vector&v1, const Vector2&v2 );
       Vector2(int inita = 0, int initb = 0) : a(inita), b(initb) { cout << "222Object created2222\n"<< endl;};

        ~Vector2() // Деструктор всего классса Vector2
       {
        cout << "222Object deleted222\n"<<endl;
        }

       };

       void fun (const Vector&v1, const Vector2&v2 ) {


       if (sqrt(v1.x*v1.x+v1.y*v1.y)>sqrt(v2.x*v2.x+v2.y*v2.y))
       {
         cout<<"Максимальное значение У = "<<v1.y<<endl; cout<<"Максимальное значение X = "<<v1.x<<endl;
       }
         else {cout<<"Максимальное значение У = "<<v2.y<<endl;cout<<"Максимальное значение X = "<<v2.x<<endl;}


        }

       int main()
       {

       setlocale(LC_ALL, "rus");
       int x1, y1, x2, y2,c;
        cout << "Координаты первого вектора: "; cin >> x1 >> y1;
       cout << "Координаты второго вектора: "; cin >> x2 >> y2;
       //cout << "число: "; cin >> d;

        Vector v1(x1, y1);
        Vector2 v2(x2, y2);
         void fan (const Vector&v1, const Vector2&v2);




        if (sqrt(x1*x1+y1*y1)>sqrt(x2*x2+y2*y2))
        {
        cout<<"Максимальное значение X = "<<x1<<endl;
        cout<<"Максимальное значение У = "<<y1<<endl;
       }
       else {cout<<"Максимальное значение X = "<<x2<<endl;cout<<"Максимальное значение У = "<<y2<<endl;}




         return 0;
       }

