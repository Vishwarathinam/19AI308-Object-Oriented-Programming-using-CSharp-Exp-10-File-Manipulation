# Exp-10-File-Manipulation
Develop a C# program to get the values from the user using structure and store it in a file in a specific path using file stream concept
## AIM:
To develop a C# program using file streams.

## ALGORITHM:
### Step 1:
Create a file using FileStream.

### Step 2:
Create a structure for student details.

### Step 3:
Get the number of students and their details from user.

### Step 4:
Define a function to write the details of student into the created file.

### Step 5:
Pass the details of student to the function.

### Step 6:
File has been created and written with student details.

## PROGRAM:
```cs
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.IO;
struct student
{
    public string name;
    public int age;
    public string dept;
    public float sem_percent;
};
public class program
{
    static void write(string name, int age, string dept, float percent, int i)
    {
        FileStream fs = new FileStream("file.txt", FileMode.Append, FileAccess.Write);
        StreamWriter sw = new StreamWriter(fs);
        sw.WriteLine("name of the student-{0}:{1}", i + 1, name);
        sw.WriteLine("age of the student-{0}:{1}", i + 1, age);
        sw.WriteLine("dept of the student-{0}:{1}", i + 1, dept);
        sw.WriteLine("semester percentage of the student-{0}:{1}", i + 1, percent);
        sw.WriteLine();
        sw.Close();
        fs.Close();
    }
    public static void Main(string[] args)
    {
        FileStream fs = new FileStream("file.txt", FileMode.Create, FileAccess.Write);
        fs.Close();
        Console.Write("Enter num of students:");
        int n = Convert.ToInt32(Console.ReadLine());
        student[] s = new student[n];
        for (int i = 0; i < n; i++)
        {
            Console.Write("Enter the name of the student-{0}:", i + 1);
            s[i].name = Console.ReadLine();
            Console.Write("Enter the age of the student-{0}:", i + 1);
            s[i].age = Convert.ToInt32(Console.ReadLine());
            Console.Write("Enter the dept of the student-{0}:", i + 1);
            s[i].dept = Console.ReadLine();
            Console.Write("Enter the semester percentage of the student-{0}:", i + 1);
            s[i].sem_percent = float.Parse(Console.ReadLine());
            write(s[i].name, s[i].age, s[i].dept, s[i].sem_percent, i);
            Console.WriteLine();
        }
        Console.ReadKey();
    }
}
```

## OUTPUT:
![image](https://github.com/Ronick2005/19AI308-Object-Oriented-Programming-using-CSharp-Exp-10-File-Manipulation/assets/83219341/95c2255d-83c5-4de9-8e79-0f485d0cc8ae)

## RESULT:
Thus a C# program to store the student details in file using structure concept is implemented successfully.
