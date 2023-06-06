# c_sharp_review
常見資料型態&變數
//字串string "小白好帥"
//字元char 'a'
//整數 int 160
//浮點數 double 160.5
//布林值 bool true false

string name = "小黑";  //把"小黑"放到name這個容器
char sex = 'M';
int age = 30;
double height = 180.3;
bool is_male = true;

System.Console.WriteLine("有一個人叫"+name);
name = "小黃";
System.Console.WriteLine(name + "今年87歲");
name = "小灰";
System.Console.WriteLine(name + "身高187公分");
name = 30; //已經指定name是string就不能設定其餘型態
System.Console.WriteLine(name + "討厭自己87歲");

字串常見用法
換行： \n
反斜線後面為字串一部分：\任意符號
string phrase = "Hello Mr.White";
System.Console.WriteLine( phrase.Length );
System.Console.WriteLine( phrase.Contains("Hello") ); ## T or F
//"Hello Mr.White"
// 012345678...
System.Console.WriteLine( phrase[1] ); ## e
System.Console.WriteLine( phrase.IndexOf('H') );
System.Console.WriteLine( phrase.IndexOf("White") ); ## 9
System.Console.WriteLine( phrase.IndexOf("qq") ); ## -1　(找不到)
System.Console.WriteLine( phrase.Substring(2) ); ##從第2個往後數 llo Mr.White
System.Console.WriteLine( phrase.Substring(6,5) ); ## Mr.Wh


數字常見的用法(整數 浮點數)
System.Console.WriteLine(5/2); ## 2
System.Console.WriteLine(5/2.0); ##2.5
System.Console.WriteLine(System.Math.Abs(-10));
System.Console.WriteLine(System.Math.Pow(2,3)); ## 8 
System.Console.WriteLine(System.Math.Sqrt(64)); ## 8 
System.Console.WriteLine(System.Math.Round(3.4)); ## 3 (四捨五入)


取得用戶輸入
System.Console.WriteLine("請輸入你的名字:"); ## WriteLine會換行
System.Console.Write("請輸入你的名字:"); ## Write不會
string name = System.Console.ReadLine();
System.Console.Write("請輸入你的年紀:");
string age = System.Console.ReadLine();
System.Console.WriteLine("你好阿" + name + "你今年" + age + "歲") ;



基本計算機
System.Console.Write("請輸入第一個數字: ");
string num1 = System.Console.ReadLine();
System.Console.Write("請輸入第二個數字: ");
string num2 = System.Console.ReadLine();
System.Console.WriteLine(num1  + num2);
以上為字串的相加

System.Console.Write("請輸入第一個數字: ");
double num1 = System.Convert.ToDouble(System.Console.ReadLine());
System.Console.Write("請輸入第二個數字: ");
double num2 = System.Convert.ToDouble(System.Console.ReadLine());
System.Console.WriteLine(num1  + num2); 
以上為數字相加



Array 陣列
int[] scores = { 50, 60, 70, 80, 90,}; //直接建立幾個值
scores[0] = 60;
System.Console.WriteLine(scores[0]);
System.Console.WriteLine(scores[1]);
System.Console.WriteLine(scores[2]);
System.Console.WriteLine(scores[3]);
System.Console.WriteLine(scores[4]);

string[] phones = new string[10]; //先建立空位，沒賦值就為空
phones[0] = "0123456789";
phones[1] = "0088888";
System.Console.WriteLine(phones[0]);
System.Console.WriteLine(phones[1]);



if 判斷句
//1.如果我肚子餓
//我就去吃飯
bool hungry = true;
if(hungry)
{
    System.Console.WriteLine("我就去吃飯");
}

//2.如果今天有下雨
//我就開車去上班
//否則
//我就走路去上班
bool rainy = true;
if(rainy)
{
    System.Console.WriteLine("我就開車去上班");
}
else
{
    System.Console.WriteLine("我就走路去上班");
}

//3.
int score = 100;
if(score == 100)
{
    System.Console.WriteLine("我給你1000元");
}
else if(score>=80)
{
    System.Console.WriteLine("我給你500元");
}
else if(score>=60)
{
    System.Console.WriteLine("我給你100元");
}
else
{
    System.Console.WriteLine("你給我300元");
}

//4.
int score = 90;
bool rainy = true;
if(score == 100 && rainy)  // 且:&&，或:||
{
    System.Console.WriteLine("我給你1000元");
}
else if(score>=80)
{
    System.Console.WriteLine("我給你500元");
}
else if(score>=60)
{
    System.Console.WriteLine("我給你100元");
}
else
{
    System.Console.WriteLine("你給我300元");
}

/*5.
如果你考100分 且 今天下雨
    我給你1000元
否則
    我給你100元
*/

/*6.
如果你沒有考100分 或 今天沒有下雨
    我給你1000元
否則
    你給我100元
*/
int score = 90;
bool rainy = false;
if(score != 100 || !rainy)  ## 且:&&，或:||
{
    System.Console.WriteLine("我給你1000元");
}
else if(score>=80)
{
    System.Console.WriteLine("我給你500元");
}
else if(score>=60)
{
    System.Console.WriteLine("我給你100元");
}
else
{
    System.Console.WriteLine("你給我300元");
}

進階計算機
System.Console.Write("輸入第一個數");
double num1 = System.Convert.ToDouble(System.Console.ReadLine());
System.Console.Write("輸入要做的運算");
string oper = System.Console.ReadLine();
System.Console.Write("輸入第二個數");
double num2 = System.Convert.ToDouble(System.Console.ReadLine());

if (oper == "+")
{
    System.Console.WriteLine(num1 + num2);
}
else if (oper == "-")
{
    System.Console.WriteLine(num1 - num2);
}
else if (oper == "*")
{
    System.Console.WriteLine(num1 * num2);
}
else if (oper == "/")
{
    System.Console.WriteLine(num1 / num2);
}
else
{
    System.Console.WriteLine("此計算機不會");
}

while 迴圈
int num = 1;
while (num <= 5)
{
    System.Console.WriteLine(num);
    num = num + 1; //num++  num+=1
}

int num = 1;
do
{
    System.Console.WriteLine(num);
    num = num + 1; //num++  num+=1
}
while (num <= 5);

猜數字遊戲
int secret_num = 66;
int guess;
int guess_num = 0;
int guess_limit = 3;
bool win = false;

do
{
	System.Console.WriteLine("輸入猜測數字");
guess = System.Convert.ToInt32(System.Console.ReadLine());
guess_num++;

if(guess>secret_num)
{
	System.Console.WriteLine("小一點");
}
else if(guess<secret_num)
{
	System.Console.WriteLine("大一點");
}
else
{
	System.Console.WriteLine("答對了");
	win = true;
}

}while(guess!=secret_num && guess_num<guess_limit);

if (!win)
{
	System.Console.WriteLine("你輸了");
}

for迴圈
for(int i=0; i<=5; i++) //也可以i+=2，以2為等差
{
	System.Console.WriteLine(i);
}


int[] nums = {55,66,11,22,33,78};
for (int i = 0; i < nums.Length; i++)
{
    System.Console.WriteLine(nums[i]);
}

二維陣列
int[,] nums = {
    {1, 2, 3 },
    {4, 5, 6 },
    {7, 8, 9 }
};

int[,] num1 = new int[3, 4]; //3*4的張量
num1[0, 0] = 3;
num1[1, 0] = 4;

class、object 類別 物件
##先建立模板，再建立實體物件
##加入->專案->class專案
class Person
{
    public double height;
    public int age;
    public string name;
}

Person person1 = new Person();
person1.height = 170;
person1.name = "小黑";
person1.age = 42;

System.Console.WriteLine(person1.height);


namespace、using(namespace想成資料夾)
namespace Animal
{
    class Person
    {
        public double height;
        public int age;
        public string name;
    }

}

using Animal;   //(or Animal.Person)
using System;
Console.WriteLine("哈哈");
System.Console.WriteLine("哈哈");
System 是 namespace
Console 是 class


方法(印出來 != return)
class Person
{
    public double height;
    public int age;
    public string name;

    public void SayHi()
    {
        Console.WriteLine("hi我是" + name);
    }
    public void Is18_1()
    {
        if (age >= 18)
        {
            Console.WriteLine(true);
        }
        else
        {
            Console.WriteLine(false);
        }
    }
    public bool Is18_2()
    {
        if (age >= 18)
        {
            return true;
        }
        else
        {
            return false;
        }
    }
    public int add(int num1, int num2)
    {
        return num1 + num2;
    }



}
Console.WriteLine(person1.add(5,9));
Console.WriteLine(person1.Is18_2());
person1.SayHi();

main方法(程式從哪裡開始?)
class Program
{
    static void Main()
    {
        Console.WriteLine("777");
    }
}




