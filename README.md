# LABORATORNA-4
/*
Variant 13. Даний масив розміру N. Знайти кількість його локальних мінімумів
(максимумів).
*/

using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace ConsoleApp9
{
    class Program
    {
        static void Main(string[] args)
        {

            string b;
            var mass = new List<int>();
            Console.WriteLine("Введите элемент массива");

            while (!string.IsNullOrWhiteSpace((b = Console.ReadLine())))
            {
                int c;
                if (int.TryParse(b, out c))
                {
                    mass.Add(c);
                    int count = mass.Count();
                    if (count > 2 && mass[count - 1] < mass[count - 2] && mass[count - 2] > mass[count - 3])
                        Console.WriteLine("Локальный максимум {0}", mass[count - 2]);
                    Console.WriteLine("Добавьте элемент, или выведите массив");
                }
                else
                    Console.WriteLine("Некорректный ввод! Добавьте элемент, или выведите массив");
            }
            Console.WriteLine("----------------");
            Console.WriteLine("Получившийся массив");
            Console.WriteLine(string.Join("", mass));
            Console.WriteLine("----------------");
            Console.ReadKey();

        }
    }
}
