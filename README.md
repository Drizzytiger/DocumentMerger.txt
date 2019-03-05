# DocumentMerger.txt
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.IO;

namespace DocumentMerger
{
    class Program
    {
        static void Main(string[] args)
        {
            int quest = 0;
            Console.WriteLine("Document Merger\n");
            while (quest == 0)
            {
                Console.WriteLine("What is the Name of the First File?");
                var info = new List<string> {@"C:\new folder\dogs","C:\new folder\tigers"};
                string name1 = Console.ReadLine();
                string CaseA = "Dogs";
                string CaseB = "Tigers";
                string CaseC = "Socer";
                string CaseD = "Drake";
                string CaseE = "Ewing";
                string CaseF = "File";
                String CaseG = "Games";
                File.CreateText(CaseA);
                File.CreateText(CaseB);
                File.CreateText(CaseC);
                File.CreateText(CaseD);
                File.CreateText(CaseE);
                File.CreateText(CaseF);
                File.CreateText(CaseG);
                while(File.Exists(name1) == false)
                {
                    Console.WriteLine("The file you hav seleted does not exist\nPlease try again\nWhat is the name of your file?");
                    name1 = Console.ReadLine();
                }
                Console.WriteLine("What is the Name of the Second File?");
                string name2 = Console.ReadLine();
                while(File.Exists(name2) == false)
                {
                    Console.WriteLine("The file you hav seleted does not exist\nPlease try again\nWhat is the name of your file?");
                    name2 = Console.ReadLine();
                }
                string merge = name1 + name2 + ".txt";
                Console.WriteLine("The mergeed files are {0},and {1}, together they create {2}",name1,name2,merge);
                StreamWriter sw = null;
                try
                {
                    sw = new StreamWriter(merge);
                    Console.WriteLine("The Two files that have been merged has been saved! " + merge + ". The Document contains " + merge.Length+ " amount of characters");
                }
                catch(Exception e)
                {
                    Console.WriteLine(e);
                }
                finally
                {
                    if(sw != null)
                    {
                        sw.Close();
                    }
                }

                Console.WriteLine("Would you like to merge two more files? If so Press any key, if not enter no");
                string test;
                test = Console.ReadLine();
                if(test == "no")
                {
                    quest = 1;
                }
            }

        }
    }
}
