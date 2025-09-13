# bai2
bai2
using System;
using System.Collections.Generic;
using System.Linq;

namespace StudentManagement
{
    class Student
    {
        public int Id { get; set; }
        public string Name { get; set; }
        public int Age { get; set; }

        public override string ToString()
        {
            return $"ID: {Id}, Name: {Name}, Age: {Age}";
        }
    }

    class Program
    {
        static void Main(string[] args)
        {
            // Tạo danh sách học sinh
            List<Student> students = new List<Student>()
            {
                new Student{ Id = 1, Name = "An", Age = 16 },
                new Student{ Id = 2, Name = "Binh", Age = 18 },
                new Student{ Id = 3, Name = "Anh", Age = 15 },
                new Student{ Id = 4, Name = "Cuong", Age = 20 },
                new Student{ Id = 5, Name = "Dung", Age = 14 }
            };

            //a
            Console.WriteLine("a. Danh sach hoc sinh:");
            students.ForEach(s => Console.WriteLine(s));

            //b
            Console.WriteLine("\nb. Hoc sinh co tuoi tu 15 đen 18:");
            var ageRange = students.Where(s => s.Age >= 15 && s.Age <= 18);
            foreach (var s in ageRange) Console.WriteLine(s);

            //c
            Console.WriteLine("\nc. Hoc sinh co ten bat đau bang 'A':");
            var startWithA = students.Where(s => s.Name.StartsWith("A"));
            foreach (var s in startWithA) Console.WriteLine(s);

            //d
            Console.WriteLine("\nd. Hoc sinh nho tuoi nhat:");
            var minAge = students.Min(s => s.Age);
            var youngest = students.Where(s => s.Age == minAge);
            foreach (var s in youngest) Console.WriteLine(s);

            //e
            Console.WriteLine("\ne. Hoc sinh lon tuoi nhat:");
            var maxAge = students.Max(s => s.Age);
            var oldest = students.Where(s => s.Age == maxAge);
            foreach (var s in oldest) Console.WriteLine(s);

            //f
            Console.WriteLine("\nf. Danh sach sap xep theo tuoi tang dan:");
            var sorted = students.OrderBy(s => s.Age);
            foreach (var s in sorted) Console.WriteLine(s);
        }
    }
}
