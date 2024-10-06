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

## Problem 11
**Write a program to compre two matrices and check if they are equal or not.**

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

        static bool AreEqualMatrix(int[,] arr1, int[,] arr2, int Rows, int Cols)
        {
            return SumOfMatrix(arr1,Rows,Cols) == SumOfMatrix(arr2,Rows,Cols);
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
            int[,] arr2 = new int[3, 3];

            FillMatrixWithRandomNumber(arr1, 3, 3);

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1,3,3);

            FillMatrixWithRandomNumber(arr2, 3, 3);

            Console.WriteLine("Matrix2:");
            PrintMatrix(arr2, 3, 3);

            if (AreEqualMatrix(arr1, arr2, 3, 3))
                Console.WriteLine("Yes: both Matrices are equal.");
            else
                Console.WriteLine("No: Matrix are not equal.");

            Console.ReadKey();
        }
    }
}
```

## Problem 12
**Write a program to compare two matrices and check if they are typical or not.**

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

        static bool AreTypicalMatrix(int[,] arr1, int[,] arr2, int Rows, int Cols)
        {
            for (int i = 0;i<Rows;i++)
            {
                for (int j=0; j<Cols; j++)
                {
                    if (arr1[i, j] != arr2[i, j])
                        return false;
                }
            }
            return true;
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
            int[,] arr2 = new int[3, 3];

            FillMatrixWithRandomNumber(arr1, 3, 3);

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1,3,3);

            FillMatrixWithRandomNumber(arr2, 3, 3);

            Console.WriteLine("Matrix2:");
            PrintMatrix(arr2, 3, 3);

            if (AreTypicalMatrix(arr1,arr2,3,3))
                Console.WriteLine("Yes: both Matrices are Typical.");
            else
                Console.WriteLine("No: Matrix are not Typical.");

            Console.ReadKey();
        }
    }
}
```

## Problem 13
**Write a program to check if the matrix is identity or not.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
      
        static bool IsIdentityMarix(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    if (i == j && arr[i, j] != 1)
                        return false;
                    else if (i != j && arr[i, j] != 0)
                        return false;
                }
            }
            return true;
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
            int[,] arr1 = {{1,0,0},{ 0, 1, 0 },{ 0, 0, 1 } };

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1, 3, 3);

            if (IsIdentityMarix(arr1,3,3))
                Console.WriteLine("Yes: Matrix is identity.");
            else
                Console.WriteLine("No: Matrix is not identity.");

            Console.ReadKey();
        }
    }
}
```

## Problem 14
**Write a program to check if the matrix is Scalar or not.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
      
        static bool IsScalar(int[,] arr, int Rows, int Cols)
        {
            int FirstDigitElements = arr[0, 0];
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    if (i == j && arr[i, j] != FirstDigitElements)
                        return false;
                    else if (i != j && arr[i, j] != 0)
                        return false;
                }
            }
            return true;
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
            int[,] arr1 = {{9,0,0},{ 0, 9, 0 },{ 0, 0, 9 } };

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1, 3, 3);

            if (IsScalar(arr1,3,3))
                Console.WriteLine("Yes: Matrix is Scalar.");
            else
                Console.WriteLine("No: Matrix is not Scalar.");

            Console.ReadKey();
        }
    }
}
```

## Problem 15
**Write a program to count given number in matrix.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    { 
        static int CountNumberInMatrix(int[,] arr, int Rows, int Cols, int Number)
        {
            int numberCount = 0;
            for (int i = 0;i<Rows;i++)
            {
                for (int j = 0;j<Cols;j++)
                {
                    if (arr[i,j] == Number)
                        numberCount++;
                }
            }
            return numberCount;
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
            int[,] arr1 = { {9, 1, 12},{ 0, 9, 1 },{ 0, 9, 9 } };

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1, 3, 3);

            Console.Write("Enter the number to count in matrix? ");
            int Number = Int32.Parse(Console.ReadLine());
            Console.WriteLine("Number " + Number + " count in matrix is : " + CountNumberInMatrix(arr1, 3, 3, Number));
           

            Console.ReadKey();
        }
    }
}
```

## Problem 16
**Write a program to check if the matrix is Sparce or not.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    { 
        static int CountNumberInMatrix(int[,] arr, int Rows, int Cols, int Number)
        {
            int numberCount = 0;
            for (int i = 0;i<Rows;i++)
            {
                for (int j = 0;j<Cols;j++)
                {
                    if (arr[i,j] == Number)
                        numberCount++;
                }
            }
            return numberCount;
        }

        static bool isSparce(int[,] arr , int Rows, int Cols)
        {
            if (CountNumberInMatrix(arr, Rows, Cols, 0) <= Math.Ceiling((float)(Rows*Cols) / 2))
                return false;
            return true;
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
            int[,] arr1 = { {0, 0, 12},{ 0, 0, 1 },{ 0, 0, 9 } };

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1, 3, 3);

            if (isSparce(arr1, 3, 3))
                Console.WriteLine("Yes: It is Sparse");
            else
                Console.WriteLine("No: It's NOT Sparse");

            Console.ReadKey();
        }
    }
}
```

## Problem 17
**Write a program to check if a given number exists in matrix or not.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    { 
        static bool IsNumberInMatrix(int[,] arr, int Rows, int Cols, int Number)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    if (arr[i, j] == Number)
                        return true;
                }
            }
            return false;
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
            int[,] arr1 = { {77, 5, 12},{ 22, 20, 1 },{ 1, 0, 9 } };

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1, 3, 3);

            Console.Write("Please Enter the number to look for in matrix? ");
            int Number = Int32.Parse(Console.ReadLine());

            if (IsNumberInMatrix(arr1, 3, 3,Number))
                Console.WriteLine("Yes: It is there.");
            else
                Console.WriteLine("No: It's not there.");

            Console.ReadKey();
        }
    }
}
```

## Problem 18
**Write a program to print the intersected numbers in two given matrices.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
        static bool IsNumberInMatrix(int[,] arr, int Rows, int Cols, int Number)
        {
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    if (arr[i, j] == Number)
                        return true;
                }
            }
            return false;
        }
        static void PrintIntersectedNumbers(int[,] arr1, int[,] arr2, int Rows, int Cols)
        {
            int Number;
            for (int i = 0; i < Rows; i++)
                for (int j = 0; j < Cols; j++)
                {
                    Number = arr1[i, j];
                    if (IsNumberInMatrix(arr2,Rows,Cols,Number))
                        Console.Write(Number + "\t");
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
            int[,] arr1 = { {77, 5, 12},{ 22, 20, 1 },{ 1, 0, 9 } };
            int[,] arr2 = { { 5, 80, 90 }, { 22, 77, 1 }, {10,8,33} };

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1, 3, 3);

            Console.WriteLine("Matrix2:");
            PrintMatrix(arr2,3,3);

            Console.WriteLine("Intersected Numbers are:");
            PrintIntersectedNumbers(arr1, arr2, 3, 3);
            Console.ReadKey();
        }
    }
}
```

## Problem 19
**Write a program to print the Minimum and Maximum Numbers in Matrix.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
        
        static int MinNumberInMatrix(int[,] arr, int Rows, int Cols)
        {
            int MinNumber = arr[0, 0];
            for (int i = 0;i<Rows;i++)
            {
                for (int j = 0;j<Cols;j++)
                {
                    if (MinNumber > arr[i,j])
                        MinNumber = arr[i,j];
                }
            }
            return MinNumber;
        }
        static int MaxNumberInMatrix(int[,] arr, int Rows, int Cols)
        {
            int MaxNumber = arr[0, 0];
            for (int i = 0; i < Rows; i++)
            {
                for (int j = 0; j < Cols; j++)
                {
                    if (MaxNumber < arr[i, j])
                        MaxNumber = arr[i, j];
                }
            }
            return MaxNumber;
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
            int[,] arr1 = { {77, 5, 12},{ 22, 20, 6 },{ 14, 3, 9 } };

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1, 3, 3);

            Console.Write("Minimum Number is: ");
            Console.WriteLine(MinNumberInMatrix(arr1, 3, 3));

            Console.Write("Max Number is: ");
            Console.WriteLine(MaxNumberInMatrix(arr1, 3, 3));

            Console.ReadKey();
        }
    }
}
```

## Problem 20
**Write a program to check it the matrix is Palindrome or not.**

```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {
        
        static bool isPalindrome(int[,] arr, int Rows, int Cols)
        {
            for (int i = 0; i < Rows; i++)
                for (int j = 0; j < Cols/2; j++)
                {
                    if (arr[i, j] != arr[i, Cols - j - 1])
                        return false;
                }
            return true;

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
            int[,] arr1 = { {1, 2, 1},{ 5, 5, 5 },{ 7, 3, 7 } };

            Console.WriteLine("Matrix1:");
            PrintMatrix(arr1, 3, 3);

            if (isPalindrome(arr1, 3, 3))
                Console.WriteLine("Yes: Matrix is Palindrome");
            else
                Console.WriteLine("No: Matrix is NOT Palindrome");

            Console.ReadKey();
        }
    }
}
```

## Problem 21 
**Write a program to print Fibonacci Series of 10 using loop.**

```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {
        static void PrintFibonacciUsingLoop(int Number)
        {
            int FirstPrev = 1;
            int SecPrev = 0;
            int FebNumber = 0;
            Console.Write("1\t");
            for(int i = 0; i < Number - 1; i++)
            {
                FebNumber = FirstPrev + SecPrev;

                Console.Write(FebNumber + "\t");
         
                SecPrev = FirstPrev;
                FirstPrev = FebNumber;
            }
        }
        static void Main(string[] args)
        {
            PrintFibonacciUsingLoop(10);
            Console.ReadKey();
        }
    }
}
```

## Problem 22
**Write a program to print Fibonacci Series of 10 using Recursion.**

```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {
        static void PrintFibonacciUsingRecursion(int Number, int Prev1, int Prev2)
        {
            int FebNumber = 0;

            if (Number > 0)
               {
                FebNumber = Prev1 + Prev2;
                Console.Write(FebNumber + "\t");
                Prev2 = Prev1;
                Prev1 = FebNumber;

                PrintFibonacciUsingRecursion(Number - 1, Prev1, Prev2);
               }
            else
                return;
        }
        static void Main(string[] args)
        {
            PrintFibonacciUsingRecursion(10, 0, 1);
            Console.ReadKey();
        }
    }
}
```

## Problem 23
**Write a program to read a string then print the first letter of each word in that string.**

```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {

        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }
       static void PrintFirstLetterEachWord(string Input)
        {
            bool isFirstLetter = true;
            Console.WriteLine("First letter of this string:");

            for (int i = 0; i < Input.Length - 1; i++)
            {
                if (Input[i] != ' ' && isFirstLetter)
                {
                    Console.WriteLine(Input[i]);
                }
                isFirstLetter = (Input[i] == ' ' ? true : false);
            }

        }
        static void Main(string[] args)
        {
            PrintFirstLetterEachWord(ReadString());

            Console.ReadKey();
        }
    }
}
```

## Problem 24
**Write a program to read a string then uppercase the first letter of each word in that string.**
```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {

        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }
       static string UpperFirstLetterOfEachWord(string Input)
        {
            bool isFirstLetter = true;
            char[] chars = Input.ToCharArray();
            for (int i = 0; i < chars.Length - 1; i++)
            {
                if (chars[i] != ' ' && isFirstLetter)
                {
                    chars[i] = char.ToUpper(chars[i]);
                }
                isFirstLetter = (chars[i] == ' ' ? true : false);
            }

            Console.WriteLine("String After Conversion:");
            return new string(chars);

        }
        static void Main(string[] args)
        {
            Console.WriteLine(UpperFirstLetterOfEachWord(ReadString()));

            Console.ReadKey();
        }
    }
}
```

## Problem 25
**Write a program to read a string then lowercase the first letter of each word in that string.**

```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {

        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }
       static string LowerFirstLetterOfEachWord(string Input)
        {
            bool isFirstLetter = true;
            char[] chars = Input.ToCharArray();
            for (int i = 0; i < chars.Length - 1; i++)
            {
                if (chars[i] != ' ' && isFirstLetter)
                {
                    chars[i] = char.ToLower(chars[i]);
                }
                isFirstLetter = (chars[i] == ' ' ? true : false);
            }

            Console.WriteLine("String After Conversion:");
            return new string(chars);

        }
        static void Main(string[] args)
        {
            Console.WriteLine(LowerFirstLetterOfEachWord(ReadString()));

            Console.ReadKey();
        }
    }
}
```

## Problem 26
**Write a program to read a string then upper all letters , then lower all letters , and print them**

```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {

        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }
       static string LowerAllString(string Input)
        {
            
            char[] chars = Input.ToCharArray();
            for (int i = 0; i < chars.Length; i++)
            {
                if (chars[i] != ' ')
                {
                    chars[i] = char.ToLower(chars[i]);
                }
            }
            Console.WriteLine("String After Lower:");
            return new string(chars);

        }

        static string UpperAllString(string Input)
        {

            char[] chars = Input.ToCharArray();
            for (int i = 0; i < chars.Length; i++)
            {
                if (chars[i] != ' ')
                {
                    chars[i] = char.ToUpper(chars[i]);
                }
            }
            Console.WriteLine("String After Upper:");
            return new string(chars);

        }
        static void Main(string[] args)
        {
            string _Input = ReadString();  
            Console.WriteLine(UpperAllString(_Input));
            Console.WriteLine(LowerAllString(_Input));
            Console.ReadKey();
        }
    }
}
```

## Problem 27
**Write a program to read a character then invert it's case and print it.**

```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {

        static char ReadChar()
        {
            char _Input;
            Console.WriteLine("Please Enter Your Character?");
            _Input = (char)Console.Read();

            return _Input;

        }
       static char InvertChar(char Input)
        {
            Console.WriteLine("Char after inverting case:");
            return (Char.IsUpper(Input)) ? Input = Char.ToLower(Input) : Input = Char.ToUpper(Input);
        }

      
        static void Main(string[] args)
        {
            Console.WriteLine(InvertChar(ReadChar()));
            Console.ReadKey();
        }
    }
}
```

## Problem 28
**Write a program to read a string then invert all its letter's case and print it.**

```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {

        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }
        static char InvertChar(char Input)
        {
            return (Char.IsUpper(Input)) ? Input = Char.ToLower(Input) : Input = Char.ToUpper(Input);
        }

        static string InvertAllCharacter(string Input)
        {
            char[] chars = Input.ToCharArray();

            for (int i = 0;i<chars.Length;i++)
            {
                chars[i] = InvertChar(chars[i]);
            }


            Console.WriteLine("String after Inverting All Letter Case:");
            return new string(chars);
        }

      
        static void Main(string[] args)
        {
            Console.WriteLine(InvertAllCharacter(ReadString()));
            Console.ReadKey();
        }
    }
}
```

## Problem 29
**Write a program to read a string then count small/capital letters in that string.**
```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {
        enum enWhatToCount { SmallLetter = 0 , CapitalLetter = 1, All = 3}

        static int CountLetter(string Input, enWhatToCount WhatToCount = enWhatToCount.All)
        {
            int Counter = 0;
            if (WhatToCount == enWhatToCount.All)
                return Input.Length;
           
            for (int i = 0; i<Input.Length;i++)
            {
                if (char.IsUpper(Input[i]) && WhatToCount == enWhatToCount.CapitalLetter)
                    Counter++;
                if (char.IsLower(Input[i]) && WhatToCount == enWhatToCount.SmallLetter)
                    Counter++;
            }
            return Counter;
        }
        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }
        
        // First Way
        static int CapitalLetterCount(string Input)
        {
            int Count = 0;
            foreach (char c in Input)
            {
                if (char.IsUpper(c))
                {
                    Count++;
                }
            }

            return Count;
        }
        // First way
        static int SmallLetterCount(string Input)
        {
            int Count = 0;
            foreach (char c in Input)
            {
                if (char.IsLower(c))
                {
                    Count++;
                }
            }

            return Count;
        }

        static void Main(string[] args)
        {
            string _Input = ReadString();
            Console.WriteLine("String Length:" + CountLetter(_Input, enWhatToCount.All));
            Console.WriteLine("Capital Letter Count:" + CountLetter(_Input, enWhatToCount.CapitalLetter));
            Console.WriteLine("Small Letter Count:" + CountLetter(_Input, enWhatToCount.SmallLetter));
            Console.ReadKey();
        }
    }
}
```

## Problem 30

**Write a program to read a string and read a character then count the character in that string.**

```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {
        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }

        static char ReadChar()
        {
            char _Input;
            Console.WriteLine("\nPlease Enter Your Character?");
            _Input = (char)Console.Read();

            return _Input;

        }

        static int CountLetter(string Input, char Letter)
        {
            int Counter = 0;
            for (int i = 0;i<Input.Length;i++)
            {
                if (Input[i] == Letter)
                    Counter++;
            }
            return Counter;
        }
        static void Main(string[] args)
        {
            string _Input = ReadString();
            char _Letter = ReadChar();

            Console.WriteLine("Letter '" + _Letter + "' Count = " + CountLetter(_Input,_Letter));
            Console.ReadKey();
        }
    }
}
```

## Problem 31
**Write a program to read a string and read a character then count the character in that string (Match Case or Not).**

```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {
        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }

        static char ReadChar()
        {
            char _Input;
            Console.WriteLine("\nPlease Enter Your Character?");
            _Input = (char)Console.Read();

            return _Input;

        }

        static int CountLetter(string Input, char Letter)
        {
            int Counter = 0;
            for (int i = 0;i<Input.Length;i++)
            {
                if (Input[i] == Letter)
                    Counter++;
            }
            return Counter;
        }
        static int CountLetterMatchOrNot(string Input, char Letter)
        {
            int Counter = 0;
            for (int i = 0;i < Input.Length; i++)
            {
                if (char.ToUpper(Input[i]) == Letter || char.ToLower(Input[i]) == Letter)
                    Counter++;
            }
            return Counter;
        }

        static void Main(string[] args)
        {
            string _Input = ReadString();
            char _Letter = ReadChar();

            Console.WriteLine("Letter '" + _Letter + "' Count = " + CountLetter(_Input,_Letter));
            Console.WriteLine("Letter '" + char.ToUpper(_Letter) + "' or '" + char.ToLower(_Letter) + "' Count = " + CountLetterMatchOrNot(_Input,_Letter));
            Console.ReadKey();
        }
    }
}
```

## Problem 32
**Write a program to read a character the check if it is a vowel or not (Vowels are:a, e ,i ,o ,u).**

```c#
using System;
using System.Net.Http.Headers;

namespace ConsoleApp2
{
    internal class Program
    {
        static char ReadChar()
        {
            char _Input;
            Console.WriteLine("\nPlease Enter Your Character?");
            _Input = (char)Console.Read();

            return _Input;

        }
        
        static bool IsVowel(char _Letter)
        {
            return (_Letter == 'a') || (_Letter == 'o') || (_Letter == 'e') || (_Letter == 'i') || (_Letter == 'u');
        }
   
        static void Main(string[] args)
        {
            char _Letter = ReadChar();

            if (IsVowel(_Letter))
             Console.WriteLine("YES: Letter '" + _Letter + "' is vowel");
            else
             Console.WriteLine("NO: Letter '" + _Letter + "' is NOT vowel");

            Console.ReadKey();
        }
    }
}
```

## Problem 33
**Write a program to read a string then count all vowels in that string (Vowels are: a,e,i,o,u).**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }

        static bool IsVowel(char _Letter)
        {
            return (_Letter == 'a') || (_Letter == 'o') || (_Letter == 'e') || (_Letter == 'i') || (_Letter == 'u');
        }
       
        static int CountVowels(string Input)
        {
            int Counter = 0;
            for (int i = 0; i < Input.Length; i++)
            {
                if (IsVowel(Input[i]))
                    Counter++;  
                
            }

            return Counter;
        }
        static void Main(string[] args)
        {

            Console.WriteLine("\nNumber of vowels is: " + CountVowels(ReadString()));
            
            Console.ReadKey();
        }
    }
}
```

## Problem 34
**Write a program to read a string then print all vowels in that string (Vowels are: a,e,i,o,u).**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }

        static bool IsVowel(char _Letter)
        {
           _Letter = char.ToLower(_Letter);
            return (_Letter == 'a') || (_Letter == 'o') || (_Letter == 'e') || (_Letter == 'i') || (_Letter == 'u');
        }
       
        static void PrintVowels(string Input)
        {
            Console.Write("Vowels in string are: ");
            for (int i = 0; i < Input.Length; i++)
            {
                if (IsVowel(Input[i]))
                    Console.Write(Input[i] + "     ");  
            }
        }
        static void Main(string[] args)
        {
            PrintVowels(ReadString());
            Console.ReadKey();
        }
    }
}
```

## Problem 35
**Write a program to read a string then print each word in that string.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }

        static void PrintEachWordInString(string Input)
        {
            Console.WriteLine("Your string words are:");
            for (int i = 0; i < Input.Length; i++)
            {
                if (Input[i] == ' ')
                    Console.WriteLine();
                else
                    Console.Write(Input[i]);
            }
        }
        static void Main(string[] args)
        {
            PrintEachWordInString(ReadString());
            Console.ReadKey();
        }
    }
}
```

## Problem 36
**Write a program to read a string then count each word in that string.**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }

        static int CountWordInString(string Input)
        {
            int countWord = 0;
            bool isWord = false;
            for (int i = 0; i < Input.Length; i++)
            {
                if (Input[i] != ' ')
                {
                    if (!isWord)
                    {
                        countWord++;
                        isWord = true;
                    }
                }
                else
                    isWord = false;
            }
            return countWord;
        }
        static void Main(string[] args)
        {
            Console.WriteLine("The number of words in your string is: "+CountWordInString(ReadString()));
            Console.ReadKey();
        }
    }
}
```

## Problem 37
**Write a program to read a string then Trim Left, Right, All**

```c#
using System;

namespace ConsoleApp2
{
    internal class Program
    {
        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }

        static string TrimLeft(string Input)
        {
            for (int i = 0;i<Input.Length;i++)
            {
                if (Input[i] != ' ')
                    return Input.Substring(i);
            }
            return "";
        }

        static string TrimRight(string Input)
        {
            for (int i = Input.Length - 1; i >= 0 ; i--)
            {
                if (Input[i] != ' ')
                    return Input.Substring(0,i + 1);
            }
            return "";
        }

        static string Trim(string Input)
        {
            return TrimLeft(TrimRight(Input));
        }

        static void Main(string[] args)
        {
            string _Input = ReadString();
            Console.WriteLine("Trim: " + Trim(_Input));
            Console.WriteLine("Trim Left: " + TrimLeft(_Input));
            Console.WriteLine("Trim Right: " + TrimRight(_Input));
            Console.ReadKey();
        }
    }
}
```

## Problem 38
**Write a program to read string and reverse its words.**

```c#
using System;
using System.Collections.Generic;
using System.ComponentModel.Design;

namespace ConsoleApp2
{
    internal class Program
    {
        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }

        static void ReverseWords(string input)
        {
            int startIndex = 0;
            List<string> words = new List<string>();
            for (int i = 0; i < input.Length; i++)
            {
                if (input[i] == ' ')
                {
                    words.Add(input.Substring(startIndex, i - startIndex));
                    startIndex = i + 1;
                }
                
            }
            words.Add(input.Substring(startIndex, input.Length - startIndex));
            Console.WriteLine("String after reversing words:");
            for (int i = words.Count - 1; i >= 0; i--)
            {
                Console.Write(words[i] + " ");
            }
        }
        static void Main(string[] args)
        {
            ReverseWords(ReadString());
            Console.ReadKey();
        }
    }
}
```

## Problem 39
**Write a program to remove all punctuations from a string.**

```c#
using System;
using System.Collections.Generic;
using System.ComponentModel.Design;

namespace ConsoleApp2
{
    internal class Program
    {
        static string ReadString()
        {
            string _Input;
            Console.WriteLine("Please Enter Your String?");
            _Input = Console.ReadLine();

            return _Input;

        }

        static string RemoveAllPunchecation(string Input)
        {
            for (int i = 0; i < Input.Length; i++)
            {
                if (char.IsPunctuation(Input[i]))
                {
                    Input = Input.Remove(i,1);
                }
            }

            return Input;
        }
        static void Main(string[] args)
        {
            Console.WriteLine("Pauncations Removed: \n" + RemoveAllPunchecation(ReadString()));
            Console.ReadKey();
        }
    }
}
```

## Problem 40
**Write a program to read bank client data record and convert it to one line.**

```c#
using System;
using System.Collections.Generic;
using System.ComponentModel.Design;

namespace ConsoleApp2
{
    internal class Program
    {
        struct sClient
        {
           public string AccountNumber;
           public string PinCode;
           public string Name;
           public string Phone;
           public double AccountBalance;
        }
 
        static sClient ReadNewClient()
        {
            sClient nClient = new sClient();

            Console.WriteLine("Please Enter Client Data:");

            Console.Write("Enter Account number?");
            nClient.AccountNumber  = Console.ReadLine();

            Console.Write("Enter PinCode?");
            nClient.PinCode = Console.ReadLine();

            Console.Write("Enter Name?");
            nClient.Name = Console.ReadLine();

            Console.Write("Enter Phone?");
            nClient.Phone = Console.ReadLine();

            Console.Write("Enter Account Balance?");
            nClient.AccountBalance = Convert.ToInt32(Console.ReadLine());

            return nClient;

        }

        static string ConvertRecoredToLine(sClient Client, string Seperator = "#//#")
        {
            string stClientRecord = "";

            stClientRecord += Client.AccountNumber + Seperator;
            stClientRecord += Client.PinCode + Seperator;
            stClientRecord += Client.Name + Seperator;
            stClientRecord += Client.Phone + Seperator;
            stClientRecord += Client.AccountBalance;

            return stClientRecord;
        }
        static void Main(string[] args)
        {
            sClient Client1 = new sClient();
            Client1 = ReadNewClient();
            Console.WriteLine("\n\nClient Record For Saving is:");
            Console.WriteLine(ConvertRecoredToLine(Client1));
            Console.ReadKey();
        }
    }
}
```

## Problem 41
**Write a program to convert line data to record and print it.**

```c#
using System;
using System.Collections.Generic;
using System.ComponentModel.Design;
using System.Runtime.InteropServices;

namespace ConsoleApp2
{
    internal class Program
    {
        struct sClient
        {
           public string AccountNumber;
           public string PinCode;
           public string Name;
           public string Phone;
           public double AccountBalance;
        }
 
        static sClient ReadNewClient()
        {
            sClient nClient = new sClient();

            Console.WriteLine("Please Enter Client Data:");

            Console.Write("Enter Account number?");
            nClient.AccountNumber  = Console.ReadLine();

            Console.Write("Enter PinCode?");
            nClient.PinCode = Console.ReadLine();

            Console.Write("Enter Name?");
            nClient.Name = Console.ReadLine();

            Console.Write("Enter Phone?");
            nClient.Phone = Console.ReadLine();

            Console.Write("Enter Account Balance?");
            nClient.AccountBalance = Convert.ToInt32(Console.ReadLine());

            return nClient;

        }
        static List<string> SplitString(string Input)
        {
            string[] Splits = Input.Split(new string[] { "#//#" }, StringSplitOptions.None);

            
            return new List<string>(Splits);
        }
        static sClient ConvertLineToRecord(string Client)
        {
            sClient stClient = new sClient();

            List<string> vClientData = new List<string>();
            vClientData = SplitString(Client);

            stClient.AccountNumber = (string)vClientData[0];
            stClient.PinCode = (string)vClientData[1];
            stClient.Name = (string)vClientData[2];
            stClient.Phone = (string)vClientData[3];
            double.TryParse(vClientData[4] , out stClient.AccountBalance);



            return stClient;
        }

        static void PrintClientRecord(sClient Client)
        {
            Console.WriteLine("\nThe Following is the extracted client record:\n");
            Console.WriteLine("Account Number: " + Client.AccountNumber);
            Console.WriteLine("PinCode: " + Client.PinCode);
            Console.WriteLine("Name: " + Client.Name);
            Console.WriteLine("Phone: " + Client.Phone);
            Console.WriteLine("Account Balance: " + Client.AccountBalance);

        }

        static void Main(string[] args)
        {
            string stLine = "A150#//#1234#//#Osama#//#0787833842#//#3000";
            Console.WriteLine("Line Record is:\n" + stLine);
            sClient Client = ConvertLineToRecord(stLine);

            PrintClientRecord(Client);
            Console.ReadKey();
        }
    }
}
```

## Problem 42
**Write a program to ask you to enter clients and save them to file.**

```c#
using System;
using System.Collections.Generic;
using System.IO;
namespace ConsoleApp2
{
    internal class Program
    {
        static string ClientsFileName = "MyClient/Clients.txt";
        struct sClient
        {
           public string AccountNumber;
           public string PinCode;
           public string Name;
           public string Phone;
           public double AccountBalance;
        }
 
        static sClient ReadNewClient()
        {
            sClient nClient = new sClient();

            //Console.WriteLine("Please Enter Client Data:");

            Console.Write("\nEnter Account number?");
            nClient.AccountNumber  = Console.ReadLine();

            Console.Write("Enter PinCode?");
            nClient.PinCode = Console.ReadLine();

            Console.Write("Enter Name?");
            nClient.Name = Console.ReadLine();

            Console.Write("Enter Phone?");
            nClient.Phone = Console.ReadLine();

            Console.Write("Enter Account Balance?");
            nClient.AccountBalance = Convert.ToInt32(Console.ReadLine());

            return nClient;

        }

        static string ConvertRecoredToLine(sClient Client, string Seperator = "#//#")
        {
            string stClientRecord = "";

            stClientRecord += Client.AccountNumber + Seperator;
            stClientRecord += Client.PinCode + Seperator;
            stClientRecord += Client.Name + Seperator;
            stClientRecord += Client.Phone + Seperator;
            stClientRecord += Client.AccountBalance;

            return stClientRecord;
        }

        static void AddDataLineToFile(string FileName ,string Line)
        {
            

            StreamWriter stWriter = new StreamWriter(FileName,true);

            stWriter.WriteLine(Line);
            stWriter.Close();

        }

        static void AddNewClient()
        {
            sClient stClient = new sClient();
            stClient = ReadNewClient();
            AddDataLineToFile(ClientsFileName, ConvertRecoredToLine(stClient));
        }

        static void AddClients()
        {
            
            char AddMore;
            do
            {
                Console.Clear();
                Console.WriteLine("Adding New Client:");
                AddNewClient();
                Console.Write("Client Added Successfully, do you want to add more clients? (Y/N)");
                AddMore = Convert.ToChar(Console.ReadLine());
            } while (char.ToUpper(AddMore) == 'Y' );

        }

        static void Main(string[] args)
        { 
            AddClients();
        }
    }
}
```

## Problem 43
**Write a program to read clients file and show them on the screen.**

```c#
using System;
using System.Collections.Generic;
using System.IO;
using System.Threading;
namespace ConsoleApp2
{
    internal class Program
    {
        static string ClientsFileName = "MyClient/Clients.txt";
        static int countLine = CountLineInFile();
        static string repeatedString = new string('_', 90);
        struct sClient
        {
            public string AccountNumber;
            public string PinCode;
            public string Name;
            public string Phone;
            public double AccountBalance;
        }

        static List<string> SplitString(string Input)
        {
            string[] Splits = Input.Split(new string[] { "#//#" }, StringSplitOptions.None);


            return new List<string>(Splits);
        }
        static sClient ConvertLineToRecord(string Client)
        {
            sClient stClient = new sClient();

            List<string> vClientData = new List<string>();
            vClientData = SplitString(Client);

            stClient.AccountNumber = (string)vClientData[0];
            stClient.PinCode = (string)vClientData[1];
            stClient.Name = (string)vClientData[2];
            stClient.Phone = (string)vClientData[3];
            double.TryParse(vClientData[4], out stClient.AccountBalance);



            return stClient;
        }

        static void PrintHeader()
        {
           
            Console.Write($"{" ",35}");
            Console.Write("Client List("+countLine+") Client(s).\n\n");
            Console.WriteLine(repeatedString);
            Console.WriteLine("\n| Account Number    | Pin Code   | Client Name"+($"{" ",20}") + "| Phone      | Balance");
            Console.WriteLine(repeatedString + "\n");

        }
        static void PrintClients(sClient Client)
        {
            Console.WriteLine(string.Format("|{0,-19}|", " " + Client.AccountNumber) + string.Format("{0,-12}|", " " + Client.PinCode) + string.Format("{0,-32}"," " + Client.Name)+string.Format("|{0,-12}|", " " + Client.Phone)  + string.Format("{0,-8}", " " + Client.AccountBalance));
        }

        static void ReadLineFromFile()
        {
            StreamReader st = new StreamReader(ClientsFileName);
            string Line = st.ReadLine();

            while (Line != null)
            {
                PrintClients(ConvertLineToRecord(Line));
                Line = st.ReadLine();
            }

        }

        static void PrintFooter()
        {
            Console.WriteLine("\n"+repeatedString);
        }

        static int CountLineInFile()
        {
            StreamReader st = new StreamReader(ClientsFileName);
            string line = st.ReadLine();
            int count = 0;
            while (line != null)
            {
                line = st.ReadLine();
                count++;
            }
            return count;
        }
        static void Main(string[] args)
        {

            PrintHeader();
            ReadLineFromFile();
            PrintFooter();
            Console.ReadKey();
        }
    }
}
```

## Problem 44
**Write a program to find client by AccountNumber and print it to the screen.**

```c#
using System;
using System.Collections.Generic;
using System.IO;
using System.Threading;
namespace ConsoleApp2
{
    internal class Program
    {
        static string ClientsFileName = "MyClient/Clients.txt";
        struct sClient
        {
            public string AccountNumber;
            public string PinCode;
            public string Name;
            public string Phone;
            public double AccountBalance;
        }

        static List<string> SplitString(string Input)
        {
            string[] Splits = Input.Split(new string[] { "#//#" }, StringSplitOptions.None);


            return new List<string>(Splits);
        }
        static sClient ConvertLineToRecord(string Client)
        {
            sClient stClient = new sClient();

            List<string> vClientData = new List<string>();
            vClientData = SplitString(Client);

            stClient.AccountNumber = (string)vClientData[0];
            stClient.PinCode = (string)vClientData[1];
            stClient.Name = (string)vClientData[2];
            stClient.Phone = (string)vClientData[3];
            double.TryParse(vClientData[4], out stClient.AccountBalance);



            return stClient;
        }

        static void PrintClientCard(sClient Client)
        {
            Console.WriteLine("\nThe Following are the client details:\n");
            Console.WriteLine("Account Number: " + Client.AccountNumber);
            Console.WriteLine("PinCode: " + Client.PinCode);
            Console.WriteLine("Name: " + Client.Name);
            Console.WriteLine("Phone: " + Client.Phone);
            Console.WriteLine("Account Balance: " + Client.AccountBalance);

        }
        static void SearchForAccountInFile()
        {
            StreamReader st = new StreamReader(ClientsFileName);
            string Line = st.ReadLine();
            Console.WriteLine("Please Enter Account Number?");
            string Input = Console.ReadLine();
            while (Line != null)
            {
                if (Line.Contains(Input))
                {
                    PrintClientCard(ConvertLineToRecord(Line));
                    return;
                }
                Line = st.ReadLine();
            }

            Console.WriteLine("\nClient with Account Number(" + Input + ") NOT Found!");

        }
    
        static void Main(string[] args)
        {

            SearchForAccountInFile();
            Console.ReadKey();
        }
    }
}
```

## Problem 45
**Write a program to delete client by AccountNumber.**

```c#
using System;
using System.Collections.Generic;
using System.IO;
using System.Threading;
namespace ConsoleApp2
{
    internal class Program
    {
        static string ClientsFileName = "MyClient/Clients.txt";
        struct sClient
        {
            public string AccountNumber;
            public string PinCode;
            public string Name;
            public string Phone;
            public double AccountBalance;
        }

        static string ReadClientAccountNumber()
        {
            Console.Write("Please Enter AccountNumber?");
            string AccountNumber = Console.ReadLine();

            return AccountNumber;
        }
        static List<string> SplitString(string Input)
        {
            string[] Splits = Input.Split(new string[] { "#//#" }, StringSplitOptions.None);


            return new List<string>(Splits);
        }
        static sClient ConvertLineToRecord(string Client)
        {
            sClient stClient = new sClient();

            List<string> vClientData = new List<string>();
            vClientData = SplitString(Client);

            stClient.AccountNumber = (string)vClientData[0];
            stClient.PinCode = (string)vClientData[1];
            stClient.Name = (string)vClientData[2];
            stClient.Phone = (string)vClientData[3];
            double.TryParse(vClientData[4], out stClient.AccountBalance);



            return stClient;
        }

        static void PrintClientCard(sClient Client)
        {
            Console.WriteLine("\nThe Following are the client details:\n");
            Console.WriteLine("Account Number: " + Client.AccountNumber);
            Console.WriteLine("PinCode: " + Client.PinCode);
            Console.WriteLine("Name: " + Client.Name);
            Console.WriteLine("Phone: " + Client.Phone);
            Console.WriteLine("Account Balance: " + Client.AccountBalance);

        }
        static bool SearchForAccountInFile(string AccountNumber)
        {
            using (StreamReader st = new StreamReader(ClientsFileName))
            { 
            string Line = st.ReadLine();
            while (Line != null)
            {
                if (Line.Contains(AccountNumber))
                {
                    PrintClientCard(ConvertLineToRecord(Line));
                    return true;
                }
                Line = st.ReadLine();
            }
            }
            return false;
        }

        static void DeleteClient(string AccountNumber)
        {
            if (!(SearchForAccountInFile(AccountNumber)))
            {
                Console.WriteLine("\nClient with Account Number(" + AccountNumber + ") NOT Found!");
                return;
            }

            Console.WriteLine("Are you sure you want delte this client? (Y/N) ? ");
            char Deleted = Convert.ToChar(Console.ReadLine());
            if (char.ToUpper(Deleted) == 'Y')
            {
                List<string> Lines = new List<string>(File.ReadAllLines(ClientsFileName));
                using (StreamWriter st = new StreamWriter(ClientsFileName))
                {
                    foreach (string Line in Lines)
                    {
                        if (!(Line.Contains(AccountNumber)))
                        {
                            st.WriteLine(Line);
                        }
                    }
                }

                Console.WriteLine("\nClient Deleted Successfully.");
            }

        }
        static void Main(string[] args)
        {

            DeleteClient(ReadClientAccountNumber());
            Console.ReadKey();
        }
    }
}
```

## Problem 46
**Write a program to Update client by AccountNumber.**

```c#
using System;
using System.Collections.Generic;
using System.IO;
using System.Threading;
namespace ConsoleApp2
{
    internal class Program
    {
        static string ClientsFileName = "MyClient/Clients.txt";
        struct sClient
        {
            public string AccountNumber;
            public string PinCode;
            public string Name;
            public string Phone;
            public double AccountBalance;
        }

        static string ReadClientAccountNumber()
        {
            Console.Write("Please Enter AccountNumber?");
            string AccountNumber = Console.ReadLine();

            return AccountNumber;
        }
        static List<string> SplitString(string Input)
        {
            string[] Splits = Input.Split(new string[] { "#//#" }, StringSplitOptions.None);


            return new List<string>(Splits);
        }
        static sClient ConvertLineToRecord(string Client)
        {
            sClient stClient = new sClient();

            List<string> vClientData = new List<string>();
            vClientData = SplitString(Client);

            stClient.AccountNumber = (string)vClientData[0];
            stClient.PinCode = (string)vClientData[1];
            stClient.Name = (string)vClientData[2];
            stClient.Phone = (string)vClientData[3];
            double.TryParse(vClientData[4], out stClient.AccountBalance);



            return stClient;
        }

        static string ConvertRecoredToLine(sClient Client, string Seperator = "#//#")
        {
            string stClientRecord = "";

            stClientRecord += Client.AccountNumber + Seperator;
            stClientRecord += Client.PinCode + Seperator;
            stClientRecord += Client.Name + Seperator;
            stClientRecord += Client.Phone + Seperator;
            stClientRecord += Client.AccountBalance;

            return stClientRecord;
        }
        static void PrintClientCard(sClient Client)
        {
            Console.WriteLine("\nThe Following are the client details:\n");
            Console.WriteLine("Account Number: " + Client.AccountNumber);
            Console.WriteLine("PinCode: " + Client.PinCode);
            Console.WriteLine("Name: " + Client.Name);
            Console.WriteLine("Phone: " + Client.Phone);
            Console.WriteLine("Account Balance: " + Client.AccountBalance);

        }

        static bool SearchForAccountInFile(string AccountNumber)
        {
            using (StreamReader st = new StreamReader(ClientsFileName))
            { 
            string Line = st.ReadLine();
            while (Line != null)
            {
                if (Line.Contains(AccountNumber))
                {
                    PrintClientCard(ConvertLineToRecord(Line));
                    return true;
                }
                Line = st.ReadLine();
            }
            }
            return false;
        }
         

        static string ReadDataUpdated(sClient nClient)
        {

            Console.Write("Enter PinCode?");
            nClient.PinCode = Console.ReadLine();

            Console.Write("Enter Name?");
            nClient.Name = Console.ReadLine();

            Console.Write("Enter Phone?");
            nClient.Phone = Console.ReadLine();

            Console.Write("Enter Account Balance?");
            nClient.AccountBalance = Convert.ToInt32(Console.ReadLine());

            return ConvertRecoredToLine(nClient);

        }
        static void UpdateClient(string AccountNumber)
        {
            if (!(SearchForAccountInFile(AccountNumber)))
            {
                Console.WriteLine("\nClient with Account Number(" + AccountNumber + ") NOT Found!");
                return;
            }

            Console.WriteLine("Are you sure you want update this client? (Y/N) ? ");
            char Update = Convert.ToChar(Console.ReadLine());
            if (char.ToUpper(Update) == 'Y')
            {
                List<string> Lines = new List<string>(File.ReadAllLines(ClientsFileName));
                using (StreamWriter st = new StreamWriter(ClientsFileName))
                {
                    foreach (string Line in Lines)
                    {
                        if (!(Line.Contains(AccountNumber)))
                        {
                            st.WriteLine(Line);
                        }
                        else
                        {
                            st.WriteLine(ReadDataUpdated(ConvertLineToRecord(Line)));
                        }
                    }
                }

                Console.WriteLine("\nClient Updated Successfully.");
            }

        }
        static void Main(string[] args)
        {

            UpdateClient(ReadClientAccountNumber());
            Console.ReadKey();
        }
    }
}
```