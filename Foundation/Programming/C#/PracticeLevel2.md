# Started 
**In this section, we will solved 100 problem using C#.**  

## Problem 1
**Write a program to fill a 3x3 matrix with random numbers.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
         static int Number;
         static Random rnd = new Random();

        static int RandomNumber(int From, int To)
        {
            Number = rnd.Next(From,To);
            return Number;
        }

      static void FillMatrixWithRandomNumber(int[,] arr,int Rows,int Cols)
        {
            for (int i = 0;i<Rows;i++)
            {
                for (int j = 0;j<Cols;j++)
                {
                    arr[i, j] = RandomNumber(1, 999);
                }
            }
        }
       
      static void PrintMatrix(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    Console.Write(arr[i,j] + "\t");
                }
                Console.WriteLine();
            }
        }
        static void Main(string[] args)
        {
            int[,] arr = new int[3, 3];
            FillMatrixWithRandomNumber(arr,arr.GetLength(0), arr.GetLength(1));

            Console.WriteLine("The following is a 3x3 random matrix:");
            PrintMatrix(arr, 3, 3);

            Console.ReadKey();
        }
    }
}
```

## Problem 2
**Write a program to fill a 3x3 matrix with random numbers,then print each row sum.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
         static int Number;
         static Random rnd = new Random();

        static int RandomNumber(int From, int To)
        {
            Number = rnd.Next(From,To);
            return Number;
        }

      static void FillMatrixWithRandomNumber(int[,] arr,int Rows,int Cols)
        {
            for (int i = 0;i<Rows;i++)
            {
                for (int j = 0;j<Cols;j++)
                {
                    arr[i, j] = RandomNumber(1, 999);
                }
            }
        }
       
      static void PrintMatrix(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    Console.Write(arr[i,j] + "\t");
                }
                Console.WriteLine();
            }
        }

        static int RowSum(int[,]arr, int Rows, int Cols)
        {
            int Sum = 0;
            for (int i = 0;i<Cols;i++)
            {
                Sum+= arr[Rows,i];
            }
            return Sum;
        }

        static void PrintEachRowSum(int[,]arr , int Rows, int Cols)
        {
            for (int i = 1;i<=Rows;i++)
            {
                Console.WriteLine("Row " + i + "Sum = " + RowSum(arr,i-1,Cols));   
            }
        }
        static void Main(string[] args)
        {
            int[,] arr = new int[3, 3];
            FillMatrixWithRandomNumber(arr,arr.GetLength(0), arr.GetLength(1));

            Console.WriteLine("The following is a 3x3 random matrix:");
            PrintMatrix(arr, 3, 3);

            Console.WriteLine("The following are the sum of each row in the matrix:");
            PrintEachRowSum(arr, 3, 3);
            Console.ReadKey();
        }
    }
}
```

## Problem 3
**Write a program to fill a 3x3 matrix with random numbers, then sum each row in separate array and print the results.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
         static int Number;
         static Random rnd = new Random();

        static int RandomNumber(int From, int To)
        {
            Number = rnd.Next(From,To);
            return Number;
        }

      static void FillMatrixWithRandomNumber(int[,] arr,int Rows,int Cols)
        {
            for (int i = 0;i<Rows;i++)
            {
                for (int j = 0;j<Cols;j++)
                {
                    arr[i, j] = RandomNumber(1, 999);
                }
            }
        }
       
      static void PrintMatrix(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    Console.Write(arr[i,j] + "\t");
                }
                Console.WriteLine();
            }
        }

        static int RowSum(int[,]arr, int Rows, int Cols)
        {
            int Sum = 0;
            for (int i = 0;i<Cols;i++)
            {
                Sum+= arr[Rows,i];
            }
            return Sum;
        }

        static void PrintEachRowSum(int[,]arr , int Rows, int Cols)
        {
            for (int i = 1;i<=Rows;i++)
            {
                Console.WriteLine("Row " + i + "Sum = " + RowSum(arr,i-1,Cols));   
            }
        }

        static void SumMatixRowsInArry(int[]arr1D,int[,]arr2D,int Rows,int Cols)
        {
            for (int i = 0; i<arr1D.GetLength(0); i++)
            {
                arr1D[i] = RowSum(arr2D,i,Cols);
            }
        }

        static void Print1DArrayRowSum(int[]arr1D)
        {
            for (int i = 0; i< arr1D.GetLength(0); i++)
            {
                Console.WriteLine("Row " + (i + 1) + "Sum = " + arr1D[i]);

            }
        }
        static void Main(string[] args)
        {
            int[,] arr2D = new int[3, 3];
            int[] arr1D = new int[3];
            FillMatrixWithRandomNumber(arr2D,arr2D.GetLength(0), arr2D.GetLength(1));

            Console.WriteLine("The following is a 3x3 random matrix:");
            PrintMatrix(arr2D, 3, 3);

            SumMatixRowsInArry(arr1D, arr2D, 3, 3);
            Console.WriteLine("The following are the sum of each row in the matrix:");
            Print1DArrayRowSum(arr1D);
            Console.ReadKey();
        }
    }
}
```

## Problem 4
**Write a program to fill a 3x3 matrix with random numbers, then print each Col sum.**
```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
         static int Number;
         static Random rnd = new Random();

        static int RandomNumber(int From, int To)
        {
            Number = rnd.Next(From,To);
            return Number;
        }

      static void FillMatrixWithRandomNumber(int[,] arr,int Rows,int Cols)
        {
            for (int i = 0;i<Rows;i++)
            {
                for (int j = 0;j<Cols;j++)
                {
                    arr[i, j] = RandomNumber(1, 999);
                }
            }
        }
       
      static void PrintMatrix(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    Console.Write(arr[i,j] + "\t");
                }
                Console.WriteLine();
            }
        }

        static int ColsSum(int[,]arr, int Rows, int Cols)
        {
            int Sum = 0;
            for (int i = 0;i<Rows;i++)
            {
                Sum+= arr[i,Cols];
            }
            return Sum;
        }

        static void PrintEachColsSum(int[,]arr , int Rows, int Cols)
        {
            for (int i = 1;i<=Cols;i++)
            {
                Console.WriteLine("Cols " + i + "Sum = " + ColsSum(arr,Rows,i-1));   
            }
        }

        static void Main(string[] args)
        {
            int[,] arr2D = new int[3, 3];
            FillMatrixWithRandomNumber(arr2D,arr2D.GetLength(0), arr2D.GetLength(1));

            Console.WriteLine("The following is a 3x3 random matrix:");
            PrintMatrix(arr2D, 3, 3);

            Console.WriteLine("The following are the sum of each row in the matrix:");
            PrintEachColsSum(arr2D, 3, 3);

            Console.ReadKey();
        }
    }
}
```

## Problem 5
**Write a program to fill a 3x3 matrix with random numbers, then sum each Col in another array and print them.**
```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
         static int Number;
         static Random rnd = new Random();

        static int RandomNumber(int From, int To)
        {
            Number = rnd.Next(From,To);
            return Number;
        }

      static void FillMatrixWithRandomNumber(int[,] arr,int Rows,int Cols)
        {
            for (int i = 0;i<Rows;i++)
            {
                for (int j = 0;j<Cols;j++)
                {
                    arr[i, j] = RandomNumber(1, 999);
                }
            }
        }
       
      static void PrintMatrix(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    Console.Write(arr[i,j] + "\t");
                }
                Console.WriteLine();
            }
        }

        static int ColsSum(int[,]arr, int Rows, int Cols)
        {
            int Sum = 0;
            for (int i = 0;i<Rows;i++)
            {
                Sum+= arr[i,Cols];
            }
            return Sum;
        }

        static void PrintEachColsSum(int[,]arr , int Rows, int Cols)
        {
            for (int i = 1;i<=Cols;i++)
            {
                Console.WriteLine("Cols " + i + "Sum = " + ColsSum(arr,Rows,i-1));   
            }
        }

        static void SumMatixColsInArry(int[]arr1D,int[,]arr2D,int Rows,int Cols)
        {
            for (int i = 0; i<arr1D.GetLength(0); i++)
            {
                arr1D[i] = ColsSum(arr2D,Rows,i);
            }
        }

        static void Print1DArrayColsSum(int[]arr1D)
        {
            for (int i = 0; i< arr1D.GetLength(0); i++)
            {
                Console.WriteLine("Cols " + (i + 1) + " Sum = " + arr1D[i]);

            }
        }
        static void Main(string[] args)
        {
            int[,] arr2D = new int[3, 3];
            int[] arr1D = new int[3];
            FillMatrixWithRandomNumber(arr2D,arr2D.GetLength(0), arr2D.GetLength(1));

            Console.WriteLine("The following is a 3x3 random matrix:");
            PrintMatrix(arr2D, 3, 3);

            SumMatixColsInArry(arr1D, arr2D, 3, 3);
            Console.WriteLine("The following are the sum of each row in the matrix:");
           
            Print1DArrayColsSum(arr1D);
            Console.ReadKey();
        }
    }
}
```

## Problem 6
**Write a program to fill a 3x3 matrix with ordered numbers.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
        static void FillMatrixWithOrderNumber(int[,] arr, int Rows,int Cols)
        {
            int Counter = 0;
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    arr[i, j] = ++Counter;
                }
            }
        }

        static void PrintMatrix(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0;i < Rows; i++)
            {
                for (int j = 0;j < Cols; j++)
                {
                    Console.Write(arr[i, j] + "\t");
                }    
                Console.WriteLine();
            }
        }
        static void Main(string[] args)
        {
            int[ , ] arr = new int [3,3];

            FillMatrixWithOrderNumber(arr, 3, 3);

            Console.WriteLine("Write a program to fill a 3x3 matrix with ordered number:");
            PrintMatrix(arr, 3, 3);

            Console.ReadKey();
        }
    }
}
```

## Problem 7
**Write a program to fill a 3x3 matrix with ordered numbers and print it, then transpose matrix and print it.**

```c#
using System;
using System.Data.SqlClient;

namespace ConsoleApp2
{
    internal class Program
    {
        static void FillMatrixWithOrderNumber(int[,] arr, int Rows,int Cols)
        {
            int Counter = 0;
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    arr[i, j] = ++Counter;
                }
            }
        }

        static void PrintMatrix(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0;i < Rows; i++)
            {
                for (int j = 0;j < Cols; j++)
                {
                    Console.Write(arr[i, j] + "\t");
                }    
                Console.WriteLine();
            }
        }
        static void TransposedMatrix(int[,] arr, int[,] TransposedMatrix, int Rows, int Cols)
        {
            for (int i = 0;i<Rows;i++)
            {
                for (int j = 0;j<Cols;j++)
                {
                    TransposedMatrix[i,j] = arr[j,i];
                }
                Console.WriteLine();
            }
        }
        static void Main(string[] args)
        {
            int[ , ] arr = new int [3,3];
            int[ , ] arrTransposed = new int[3,3];
            FillMatrixWithOrderNumber(arr, 3, 3);

            Console.WriteLine("Write a program to fill a 3x3 matrix with ordered number:");
            PrintMatrix(arr, 3, 3);

            TransposedMatrix(arr, arrTransposed, 3, 3);
            Console.WriteLine("The following is the transposed matrix:");
            PrintMatrix(arrTransposed, 3, 3);


            Console.ReadKey();
        }
    }
}
```

## Problem 8
**Write a program to fill two 3x3 matrix with random numbers and them, then multiply them into a 3 matrix and print it.**

```c#
using System;
using System.Data.SqlClient;

namespace ConsoleApp2
{
    internal class Program
    {
        static Random rnd = new Random();
        static int Number = rnd.Next();

        static int RandomNumber(int From, int To)
        {
            Number = rnd.Next(From, To);
            return Number;
        }

        static void FillMatrixWithRandomNumber(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    arr[i, j] = RandomNumber(1, 99);
                }
            }
        }

        static void FillMatrixWithMultiply1And2(int[,] arr1,int[,] arr2, int[,] arrResults,int Rows, int Cols)
        {
           for (int i = 0;i < Rows; i++)
            {
                for (int j = 0;j < Cols; j++)
                {
                    arrResults[i,j] = arr1[i, j] * arr2[i,j];
                }
            }
        }

        static void PrintMatrix(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0;i < Rows; i++)
            {
                for (int j = 0;j < Cols; j++)
                {
                    Console.Write(String.Format("{0:D2}", arr[i, j]) + "\t");
                }    
                Console.WriteLine();
            }
        }
      
        static void Main(string[] args)
        {
            int[,] arr1 = new int[3, 3];
            int[,] arr2 = new int[3,3];
            int[,] arrResult = new int[3, 3];

            FillMatrixWithRandomNumber(arr1, 3, 3);

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1,3,3);

            FillMatrixWithRandomNumber(arr2, 3, 3);

            Console.WriteLine("Matrix2:");
            PrintMatrix(arr2, 3, 3);

            FillMatrixWithMultiply1And2(arr1, arr2, arrResult, 3, 3);

            Console.WriteLine("Matrix3:");
            PrintMatrix(arrResult, 3, 3);


            Console.ReadKey();
        }
    }
}
```

## Problem 9
**Write a program to fill a 3x3 matrix with random numbers, print it, then print the middle row and middle col.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
        static Random rnd = new Random();
        static int Number = rnd.Next();

        static int RandomNumber(int From, int To)
        {
            Number = rnd.Next(From, To);
            return Number;
        }

        static void FillMatrixWithRandomNumber(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    arr[i, j] = RandomNumber(1, 10);
                }
            }
        }

        static void PrintMiddleRowofMatrix(int[,] arr,int Rows, int Cols)
        {
            int MiddleRow = Rows / 2;
            for (int i = 0;i < Cols; i++)
            {
                Console.Write(String.Format("{0:D2}",arr[MiddleRow, i]) + "\t");
            }
            Console.WriteLine();
        }

        static void PrintMiddleColsofMatrix(int[,] arr,int Rows, int Cols)
        {
            int MiddleCol = Cols / 2;
            for (int i = 0; i < Rows; i++)
            {
                Console.Write(String.Format("{0:D2}", arr[i, MiddleCol]) + "\t");
            }
            Console.WriteLine();
        }
        static void PrintMatrix(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0;i < Rows; i++)
            {
                for (int j = 0;j < Cols; j++)
                {
                    Console.Write(String.Format("{0:D2}", arr[i, j]) + "\t");
                }    
                Console.WriteLine();
            }
        }
      
        static void Main(string[] args)
        {
            int[,] arr1 = new int[3, 3];
            
            FillMatrixWithRandomNumber(arr1, 3, 3);

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1,3,3);

            Console.WriteLine("Middle Row of Matrix1 is:");
            PrintMiddleRowofMatrix(arr1,3,3);

            Console.WriteLine("Middle Col of Matrix1 is:");
            PrintMiddleColsofMatrix(arr1, 3, 3);


            Console.ReadKey();
        }
    }
}
```

## Problem 10
**Write a program to fill two 3x3 matrix with random numbers and them, then write a function to sum all numbers in this matrix and print it.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
        static Random rnd = new Random();
        static int Number = rnd.Next();

        static int RandomNumber(int From, int To)
        {
            Number = rnd.Next(From, To);
            return Number;
        }

        static void FillMatrixWithRandomNumber(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    arr[i, j] = RandomNumber(1, 10);
                }
            }
        }

        static int SumOfMatrix(int[,] arr, int Rows, int Cols)
        {
            int Sum = 0;

            for (int i = 0;i < Rows; i++)
            {
                for (int j=0;j < Cols; j++)
                {
                    Sum+= arr[i, j];
                }
            }

            return Sum;
        }
        static void PrintMatrix(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0;i < Rows; i++)
            {
                for (int j = 0;j < Cols; j++)
                {
                    Console.Write(String.Format("{0:D2}", arr[i, j]) + "\t");
                }    
                Console.WriteLine();
            }
        }
      
        static void Main(string[] args)
        {
            int[,] arr1 = new int[3, 3];
            
            FillMatrixWithRandomNumber(arr1, 3, 3);

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1,3,3);

            Console.WriteLine("\nSum of Matrix1 is:" + SumOfMatrix(arr1,3,3));

            Console.ReadKey();
        }
    }
}
```