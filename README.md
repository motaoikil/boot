using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.IO;

namespace ConsoleApp1
{
    class Program
    {
        static void Main(string[] args)
        {
            string path = @"C:\Users\motao\OneDrive\Desktop\ville.txt";
            string ru = "";
            StreamReader r = new StreamReader(path);
            ru=r.ReadToEnd();
            r.Close();
            int ind = -1;
            int ind1 = -1;

            string oo = "";
           while (ru.IndexOf('[') != -1) 
           {
                ind = -1;
                ind1 = -1;
                oo = "";

                ind =ru.IndexOf("[");
                ind1 = ru.IndexOf(")");

                if (ind1 < ind)
                {
                    break;
                    ru = ru.Replace("(", " ");
                    ru = ru.Replace(")", " ");
                }
                else
                {
                    oo = ru.Substring(ind, ind1 - ind + 1);
                    ru = ru.Replace(oo, "</option>\n");
                }
            }
            Console.WriteLine(ru);
            Console.ReadKey();
        }
    }
}
