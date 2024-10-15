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

## Problem 47
**Write a program to read a number and print the text of that number.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        static long ReadNumber()
        {
            Console.WriteLine("Enter a Number?");
            long number = Convert.ToInt64(Console.ReadLine());
            return number;
        }

        static string NumberToString(long number)
        {
            if (number == 0)
            {
                return "Zero";
            }

            if (number >= 1 && number <= 19)
            {
                string[] arr = { "One", "Two", "Three", "Four", "Five", "Six", "Seven", "Eight", "Nine", "Ten",
                                 "Eleven", "Twelve", "Thirteen", "Fourteen", "Fifteen", "Sixteen", "Seventeen",
                                 "Eighteen", "Nineteen" };
                return arr[number - 1];
            }
            else if (number >= 20 && number < 100)
            {
                string[] arr = { "", "", "Twenty", "Thirty", "Forty", "Fifty", "Sixty", "Seventy", "Eighty", "Ninety" };
                return arr[number / 10] + (number % 10 > 0 ? " " + NumberToString(number % 10) : "");
            }
            else if (number >= 100 && number < 1000)
            {
                return NumberToString(number / 100) + " Hundred" + (number % 100 > 0 ? " " + NumberToString(number % 100) : "");
            }
            else if (number >= 1000 && number < 1000000)
            {
                return NumberToString(number / 1000) + " Thousand" + (number % 1000 > 0 ? " " + NumberToString(number % 1000) : "");
            }
            else if (number >= 1000000 && number < 1000000000)
            {
                return NumberToString(number / 1000000) + " Million" + (number % 1000000 > 0 ? " " + NumberToString(number % 1000000) : "");
            }
            else
            {
                return NumberToString(number / 1000000000) + " Billion" + (number % 1000000000 > 0 ? " " + NumberToString(number % 1000000000) : "");
            }
        }

        static void Main(string[] args)
        {
            Console.WriteLine(NumberToString(ReadNumber()));
            Console.ReadKey();
        }
    }
}
```

## Problem 48
**Write a program to check if year is a leap year or not.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        static int ReadNumber()
        {
            Console.WriteLine("Enter a Number?");
            int Number = Convert.ToInt32(Console.ReadLine());
            return Number;
        }

       static bool LeapYear(int Number)
        {
            if ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0))
                return true;
            return false;
        }

        static void Main(string[] args)
        {
            Console.Write("Please enter a year to check");
            int Year = ReadNumber();
            if (LeapYear(Year))
            {
                Console.WriteLine("\nYes, Year [" + Year + "] is a leap year.\n");
            }
            else
            {
                Console.WriteLine("\nNo, Year [" + Year + "] is NOT a leap year.\n");
            }
            Console.ReadKey();
        }
    }
}
```

## Problem 49
**Solve Leap Year Problem with one line of code only.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        static int ReadNumber()
        {
            Console.WriteLine("Enter a Number?");
            int Number = Convert.ToInt32(Console.ReadLine());
            return Number;
        }

       static bool LeapYear(int Number)
        {

            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
          
        }

        static void Main(string[] args)
        {
            Console.Write("Please enter a year to check");
            int Year = ReadNumber();
            if (LeapYear(Year))
            {
                Console.WriteLine("\nYes, Year [" + Year + "] is a leap year.\n");
            }
            else
            {
                Console.WriteLine("\nNo, Year [" + Year + "] is NOT a leap year.\n");
            }
            Console.ReadKey();
        }
    }
}
```

## Problem 50
**Write a program to print Number of: Days , Hours , Minutes , Seconds in a certain Year.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        static int ReadNumber()
        {
            Console.WriteLine("Enter a Number?");
            int Number = Convert.ToInt32(Console.ReadLine());
            return Number;
        }

       static bool LeapYear(int Number)
        {

            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
          
        }

        static int NumberofDaysInYear(int Number)
        {
            if (LeapYear(Number))
                return 366;
            else
                return 365;
        }

        static int NumberofHoursInYear(int Number)
        {
                return NumberofDaysInYear(Number) * 24;
        }

        static int NumberofMinutesInYear(int Number)
        {
            return NumberofHoursInYear(Number) * 60;
        }

        static int NumberofSecondsInYear(int Number)
        {
            return NumberofMinutesInYear(Number) * 60;
        }
        static void Main(string[] args)
        {
            int year = ReadNumber();
            Console.WriteLine($"\nNumber of Days in Year [{year}] is {NumberofDaysInYear(year)}");
            Console.WriteLine($"\nNumber of Hours in Year [{year}] is {NumberofHoursInYear(year)}");
            Console.WriteLine($"\nNumber of Minutes in Year [{year}] is {NumberofMinutesInYear(year)}");
            Console.WriteLine($"\nNumber of Seconds in Year [{year}] is {NumberofSecondsInYear(year)}");
            Console.ReadKey();
        }
    }
}
```

## Problem 51
**Write a program to print Number of:**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        static short ReadYear()
        {
            Console.WriteLine("Please Enter a year to check?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.WriteLine("Please Enter a Month to check?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInYear(int Number)
        {
            if (LeapYear(Number))
                return 366;
            else
                return 365;
        }

        static int NumberofHoursInMonths(short Number , short year)
        {
                return NumberofDaysInMonths(Number,year) * 24;
        }

        static int NumberofMinutesInMonth(short Number, short year)
        {
            return NumberofHoursInMonths(Number,year) * 60;
        }

        static int NumberofSecondsInMonth(short Number , short year)
        {
            return NumberofMinutesInMonth(Number,year) * 60;
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 9, 11, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }
        static void Main(string[] args)
        {
            short year = ReadYear();
            short month = ReadMonth();
            Console.WriteLine($"\nNumber of Days in Month [{month}] is {NumberofDaysInMonths(month,year)}");
            Console.WriteLine($"\nNumber of Hours in Month [{month}] is {NumberofHoursInMonths(month,year)}");
            Console.WriteLine($"\nNumber of Minutes in Month [{month}] is {NumberofMinutesInMonth(month, year)}");
            Console.WriteLine($"\nNumber of Seconds in Month [{month}] is {NumberofSecondsInMonth(month, year)}");
            Console.ReadKey();
        }
    }
}
```

## Problem 52
**Write a program to print Number of Days in a certain Month in two line just.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        static short ReadYear()
        {
            Console.WriteLine("Please Enter a year to check?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.WriteLine("Please Enter a Month to check?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInYear(int Number)
        {
            if (LeapYear(Number))
                return 366;
            else
                return 365;
        }

        static int NumberofHoursInMonths(short Number , short year)
        {
                return NumberofDaysInMonths(Number,year) * 24;
        }

        static int NumberofMinutesInMonth(short Number, short year)
        {
            return NumberofHoursInMonths(Number,year) * 60;
        }

        static int NumberofSecondsInMonth(short Number , short year)
        {
            return NumberofMinutesInMonth(Number,year) * 60;
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {

            if (Number > 12 || Number < 0)
                return 0;

            int[] arr = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
            return (Number == 2 ? (LeapYear(Number) ? 29 : 28) : arr[Number - 1]);
        }
        static void Main(string[] args)
        {
            short year = ReadYear();
            short month = ReadMonth();
            Console.WriteLine($"\nNumber of Days in Month [{month}] is {NumberofDaysInMonths(month,year)}");
            Console.WriteLine($"\nNumber of Hours in Month [{month}] is {NumberofHoursInMonths(month,year)}");
            Console.WriteLine($"\nNumber of Minutes in Month [{month}] is {NumberofMinutesInMonth(month, year)}");
            Console.WriteLine($"\nNumber of Seconds in Month [{month}] is {NumberofSecondsInMonth(month, year)}");
            Console.ReadKey();
        }
    }
}
```

## Problem 53
**Write a program to read a date, and print the day name of week.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        static short ReadYear()
        {
            Console.WriteLine("Please Enter a Year?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.WriteLine("Please Enter a Month?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.WriteLine("Please Enter a Day?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
    
         static short DayofWeekOrder(short year, short month, short day)
        {
            short a = (short)((14 - month) / 12);
            short y = (short)(year - a);
            short m = (short)(month + (12 * a) - 2);

            return (short)((day + y + (y / 4) - (y / 100) + (y / 400) + ((31 * m) / 12)) % 7);

        }

        static string DayShortName(short DayofWeekOrder)
        {
            string[] arrDayNames = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };

            return arrDayNames[DayofWeekOrder];
        }
        static void Main(string[] args)
        {
            short Year = ReadYear();
            short Month = ReadMonth();
            short Day = ReadDay();

            short Days = DayofWeekOrder(Year, Month, Day);


            Console.WriteLine("Date      : " + Day + "/" + Month + "/" + Year);
            Console.WriteLine("Day Order : " + Days);
            Console.WriteLine("Day Name  : " + DayShortName(Days));
            Console.ReadKey();
        }
    }
}
```

## Problem 54
**Write a program to print Month Calendar.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        static short ReadYear()
        {
            Console.WriteLine("Please Enter a Year?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.WriteLine("Please Enter a Month?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 9, 11, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }
        static short DayofWeekOrder(short year, short month, short day)
        {
            short a = (short)((14 - month) / 12);
            short y = (short)(year - a);
            short m = (short)(month + (12 * a) - 2);

            return (short)((day + y + (y / 4) - (y / 100) + (y / 400) + ((31 * m) / 12)) % 7);

        }

        static string DayShortName(short DayofWeekOrder)
        {
            string[] arrDayNames = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };

            return arrDayNames[DayofWeekOrder];
        }

        static string MonthShortName(short MonthNumber)
        {
            string[] arrMonthDays = { "Jan" , "Feb" , "Mar" , "Apr" , "May" , "June" , "July" , "Aug" , "Sep" , "Oct" , "Nov" , "Dec"};

            return arrMonthDays[MonthNumber - 1];
        }
        static void PrintHeaderCalender()
        {
            Console.WriteLine("   Sat  Mon  Tue  Wed  Thu  Fri  Sat\n");
        }

        static void PrintDaysInMonths(short Year , short Month)
        {
            short IndexDays = DayofWeekOrder(Year,Month,1);
            short count = 0;
            short CountDay = 1;
            for (short i = 0;i< NumberofDaysInMonths(Month,Year) + IndexDays; i++)
            {
                if (count == 7)
                {
                    Console.WriteLine();
                    count = 0;
                }
                if (i < IndexDays)
                    Console.Write("     ");
                else
                {
                    Console.Write("  " + $"{CountDay,3}");
                    CountDay++;
                }
                count++;
            }
                
        }
        static void PrintMonthCalender(short Year, short Month)
        {
            string MonthName = MonthShortName(Month);
            Console.WriteLine("  ________________" + MonthName + "________________\n");
            PrintHeaderCalender();
            PrintDaysInMonths(Year,Month);
            Console.WriteLine();
            Console.WriteLine("  ___________________________________\n");
        }
        static void Main(string[] args)
        {
            short Year = ReadYear();
            short Month = ReadMonth();

            PrintMonthCalender(Year, Month);
            Console.ReadKey();
        }
    }
}
```

## Problem 55
**Write a program to print Year Calender.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        static short ReadYear()
        {
            Console.WriteLine("Please Enter a Year?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.WriteLine("Please Enter a Month?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 9, 11, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }
        static short DayofWeekOrder(short year, short month, short day)
        {
            short a = (short)((14 - month) / 12);
            short y = (short)(year - a);
            short m = (short)(month + (12 * a) - 2);

            return (short)((day + y + (y / 4) - (y / 100) + (y / 400) + ((31 * m) / 12)) % 7);

        }

        static string DayShortName(short DayofWeekOrder)
        {
            string[] arrDayNames = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };

            return arrDayNames[DayofWeekOrder];
        }

        static string MonthShortName(short MonthNumber)
        {
            string[] arrMonthDays = { "Jan" , "Feb" , "Mar" , "Apr" , "May" , "June" , "July" , "Aug" , "Sep" , "Oct" , "Nov" , "Dec"};

            return arrMonthDays[MonthNumber - 1];
        }
        static void PrintHeaderCalender()
        {
            Console.WriteLine("   Sat  Mon  Tue  Wed  Thu  Fri  Sat\n");
        }

        static void PrintDaysInMonths(short Year , short Month)
        {
            short IndexDays = DayofWeekOrder(Year,Month,1);
            short count = 0;
            short CountDay = 1;
            for (short i = 0;i< NumberofDaysInMonths(Month,Year) + IndexDays; i++)
            {
                if (count == 7)
                {
                    Console.WriteLine();
                    count = 0;
                }
                if (i < IndexDays)
                    Console.Write("     ");
                else
                {
                    Console.Write("  " + $"{CountDay,3}");
                    CountDay++;
                }
                count++;
            }
                
        }
        static void PrintMonthCalendar(short Year, short Month)
        {
            string MonthName = MonthShortName(Month);
            Console.WriteLine("  ________________" + MonthName + "________________\n");
            PrintHeaderCalender();
            PrintDaysInMonths(Year,Month);
            Console.WriteLine();
            Console.WriteLine("  ___________________________________\n");
        }

        static void PrintYearsCalendar(short Year)
        {
            Console.WriteLine("  ___________________________________\n");
            Console.WriteLine($"{"Calendar - " + Year,28}");
            Console.WriteLine("  ___________________________________\n");
            
            for (short i = 1;i<=12;i++)
            {
                Console.WriteLine();
                PrintMonthCalendar(Year, i);
            }
        }
        static void Main(string[] args)
        {
            PrintYearsCalendar(ReadYear());
            Console.ReadKey();
        }
    }
}
```

## Problem 56
**Write a program to print total days from the beginning of year.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        static short ReadYear()
        {
            Console.WriteLine("Please Enter a Year?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.WriteLine("Please Enter a Month?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.WriteLine("Please Enter a Day?");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8 , 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i,Year);

            TotalDays += Day;

            return TotalDays;
        }
       
        static void Main(string[] args)
        {
            short _Day = ReadDay();
            short _Month = ReadMonth();
            short _Year = ReadYear();

            Console.WriteLine("Number of Days from the begining of the year is " + NumberOfDaysFromTheBeginingOfTheYear(_Year,_Month,_Day));
            Console.ReadKey();
        }
    }
}
```

## Problem 57
**Write a program to print total days from the beginning of year, then Take the total days and convert them back to date.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8 , 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i,Year);

            TotalDays += Day;

            return TotalDays;
        }
       
         static sDate GetDateFromDayOrderInYear(short DateOrderInYear, short Year)
        {
            sDate Date;
            short RemainingDays = DateOrderInYear;
            short MonthDays = 0;

            Date.Year = Year;
            Date.Month = 1;

            while(true)
            {
                MonthDays = (short)(NumberofDaysInMonths(Date.Month, Year));

                if (RemainingDays > MonthDays)
                {
                    RemainingDays-=MonthDays;
                    Date.Month++;
                }
                else
                {
                    Date.Day = RemainingDays;
                    break;
                }
            }
            return Date;
        }
        static void Main(string[] args)
        {
            short _Day = ReadDay();
            short _Month = ReadMonth();
            short _Year = ReadYear();

            short DaysOrderInYear = (short)(NumberOfDaysFromTheBeginingOfTheYear(_Year, _Month, _Day));
            Console.WriteLine("Number of Days from the begining of the year is " + DaysOrderInYear);

            sDate Date;

            Date = GetDateFromDayOrderInYear(DaysOrderInYear, _Year);
            Console.Write("Date for [" + DaysOrderInYear + "] is: ");
            Console.Write(Date.Day + "/" + Date.Month + "/" + Date.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 58
**Write a program to read date and read how many days to add to it, print the results on screen.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
        static int NumberofDaysInYear(int Number)
        {
            if (LeapYear(Number))
                return 366;
            else
                return 365;
        }


        static short ReadAdd()
        {
            Console.Write("How Many days to add? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8 , 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i,Year);

            TotalDays += Day;

            return TotalDays;
        }
       
         static sDate GetDateFromDayOrderInYear(short DateOrderInYear, short Year)
        {
            sDate Date;
            short RemainingDays = DateOrderInYear;
            short MonthDays = 0;

            Date.Year = Year;
            Date.Month = 1;

            while(true)
            {
                MonthDays = (short)(NumberofDaysInMonths(Date.Month, Year));

                if (RemainingDays > MonthDays)
                {
                    RemainingDays-=MonthDays;
                    Date.Month++;
                }
                else
                {
                    Date.Day = RemainingDays;
                    break;
                }
            }
            return Date;
        }

     
        static short ReadDaysToAdd()
        {
            short Days;
            Console.Write("How Many Days To Add? ");
            Days = short.Parse(Console.ReadLine());

            return Days;
        }
        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static sDate DateAddDays(short Days, sDate Date)
        {
           short RemainingDays = (short)(Days + NumberOfDaysFromTheBeginingOfTheYear(Date.Year, Date.Month, Date.Day));

            short MonthDays = 0;

            Date.Month = 1;
            while (true)
            {
                MonthDays = (short)(NumberofDaysInMonths(Date.Month, Date.Year));

                if (RemainingDays > MonthDays)
                {
                    RemainingDays -= MonthDays;
                    Date.Month++;

                    if (Date.Month > 12)
                    {
                        Date.Month = 1;
                        Date.Year++;
                    }
                }
                else
                {
                    Date.Day = RemainingDays;
                    break;
                }
            }
            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date = ReadFullDate();
            short Days = ReadDaysToAdd();

            Date = DateAddDays(Days,Date);

            Console.WriteLine("\nDate after adding [" + Days + "] days is : " + Date.Day + "/" + Date.Month + "/" + Date.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 59
**Write a program to read Date1,Date2 and check if date1 is less than date2.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }
        
        static bool IsDate1BeforeDate2(sDate Date1 , sDate Date2)
        {
            return ((Date1.Year < Date2.Year) ? true : (Date1.Year == Date2.Year) ? (Date1.Month < Date2.Month) ? true : (Date1.Month == Date2.Month) ? (Date1.Day < Date2.Day) : false : false);

        }


        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            sDate Date2 = ReadFullDate();

            if (IsDate1BeforeDate2(Date1, Date2))
                Console.WriteLine("\nYes, Date1 is Less than Date2."); 
            else 
                Console.WriteLine("\nNo, Date1 is NOT Less than Date2.");

            Console.ReadKey();
        }
    }
}
```

## Problem 60
**Write a program to read date1,date2 and check if Date1 Equals to Date2.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }
        
        static bool IsDate1EqualDate2(sDate Date1 , sDate Date2)
        {
            return (Date1.Year == Date2.Year) ? ((Date1.Month == Date2.Month) ? (Date1.Day == Date2.Day ) ? true : false : false)  : false;

        }


        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            sDate Date2 = ReadFullDate();

            if (IsDate1EqualDate2(Date1, Date2))
                Console.WriteLine("\nYes, Date1 is Equal To Date2."); 
            else 
                Console.WriteLine("\nNo, Date1 is NOT Equal To Date2.");

            Console.ReadKey();
        }
    }
}
```

## Problem 61
**Write a program to read a date and check:**  
**1.if it is last Day in Month**  
**2.If it is last Month In Year**  

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month,Date.Year);
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();

            if (IsLastDayInMonth(Date1))
                Console.WriteLine("\nYes, Day is Last Day in Month.");

            else
                Console.WriteLine("\nNo, Day is Not Last Day in Month.");

            if (IsLastMonthInYear(Date1.Month))
                Console.WriteLine("\nYes, Month is Last Month in Year.");

            else
                Console.WriteLine("\nNo, Month is Not Last Month in Year.");

            Console.ReadKey();
        }
    }
}
```

## Problem 62
**Write a program to read a date and make a function to increase date by one day.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month,Date.Year);
        }

        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
          else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();

            Date1 = IncreaseDateByOneDay(Date1);

            Console.WriteLine("\nDate after adding one day is: " + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);

            Console.ReadKey();
        }
    }
}
```

## Problem 63
**Write a program to read a Date1,Date2 and make a function to calculate the difference in days.**  
**Note: Date 1 should be less than Date2**  

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month,Date.Year);
        }

        static bool IsDate1BeforeDate2(sDate Date1, sDate Date2)
        {
            return ((Date1.Year < Date2.Year) ? true : (Date1.Year == Date2.Year) ? (Date1.Month < Date2.Month) ? true : (Date1.Month == Date2.Month) ? (Date1.Day < Date2.Day) : false : false);

        }
        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }
        static short GetDifferenceInDays(sDate Date1, sDate Date2, bool IncludeEndDay = false)
        {
            short Days = 0;

            while (IsDate1BeforeDate2(Date1,Date2))
            {
                Days++;
                Date1 = IncreaseDateByOneDay(Date1);
            }


            return IncludeEndDay ? ++Days : Days;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            sDate Date2 = ReadFullDate();

            Console.WriteLine("\nDiffrence is: " + GetDifferenceInDays(Date1,Date2));
            Console.WriteLine("\nDiffrence (Including End Day) is: " + GetDifferenceInDays(Date1, Date2,true));
            Console.ReadKey();
        }
    }
}
```

## Problem 64
**Write a program calculate you age in days.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month,Date.Year);
        }

        static bool IsDate1BeforeDate2(sDate Date1, sDate Date2)
        {
            return ((Date1.Year < Date2.Year) ? true : (Date1.Year == Date2.Year) ? (Date1.Month < Date2.Month) ? true : (Date1.Month == Date2.Month) ? (Date1.Day < Date2.Day) : false : false);

        }
        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }
        static short GetDifferenceInDays(sDate Date1, sDate Date2, bool IncludeEndDay = false)
        {
            short Days = 0;

            while (IsDate1BeforeDate2(Date1,Date2))
            {
                Days++;
                Date1 = IncreaseDateByOneDay(Date1);
            }


            return IncludeEndDay ? ++Days : Days;
        }

        static sDate GetSystemDate()
        {
            DateTime now = DateTime.Now; // Get the current date and time

            sDate date = new sDate
            {
                Year = (short)now.Year,
                Month = (short)now.Month,
                Day = (short)now.Day
            };

            return date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            sDate Date2 = GetSystemDate();

            Console.WriteLine("Your age is : " + GetDifferenceInDays(Date1,Date2,true) + " Day(s).");

            Console.ReadKey();
        }
    }
}
```

## Problem 65
**Write a program to read a Date1,Date2 and make a function to calculate the difference in days.**  
**Note: if date2 is less than date1 print the results in Minutes**  

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month,Date.Year);
        }

        static bool IsDate1BeforeDate2(sDate Date1, sDate Date2)
        {
            return ((Date1.Year < Date2.Year) ? true : (Date1.Year == Date2.Year) ? (Date1.Month < Date2.Month) ? true : (Date1.Month == Date2.Month) ? (Date1.Day < Date2.Day) : false : false);

        }
        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }
        static void SwapDate(ref sDate Date1, ref sDate Date2)
        {
            sDate TempDate;

            TempDate.Year = Date1.Year;
            TempDate.Month = Date1.Month;
            TempDate.Day = Date1.Day;

            Date1.Year = Date2.Year;
            Date1.Day = Date2.Day;
            Date1.Month = Date2.Month;

            Date2.Year  = TempDate.Year;
            Date2.Month = TempDate.Month;
            Date2.Day = TempDate.Day;
        }
        static short GetDifferenceInDays(sDate Date1, sDate Date2, bool IncludeEndDay = false)
        {
            short Days = 0;
            short SwapFlagValue = 1;

            if (!IsDate1BeforeDate2(Date1,Date2))
            {
               SwapDate(ref Date1, ref Date2);
               SwapFlagValue = -1;
            }
          
            while (IsDate1BeforeDate2(Date1,Date2))
            {
                Days++;
                Date1 = IncreaseDateByOneDay(Date1);
            }


            return IncludeEndDay ? (short)(SwapFlagValue * ++Days) :(short)(SwapFlagValue * Days);
        }

    
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            sDate Date2 = ReadFullDate();

            Console.WriteLine("\nDiffrence is: " + GetDifferenceInDays(Date1, Date2));
            Console.WriteLine("\nDiffrence (Including End Day) is: " + GetDifferenceInDays(Date1, Date2, true));
            Console.ReadKey();
        }
    }
}
```

## Problem 66
**Write a program to read a date and make a function to increase date by X days.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month,Date.Year);
        }

   
        
        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }
      
        static sDate IncreaseDateByXDays(sDate Date, short Increase)
        {

            for (int i = 0; i < Increase; i++)
                Date = IncreaseDateByOneDay(Date);

            return Date;
        }
      

    
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            sDate Date2 = IncreaseDateByXDays(Date1, 1);
            Console.WriteLine("Adding one day is:" + Date2.Day + "/" + Date2.Month + "/" + Date2.Year);
            Date1 = IncreaseDateByXDays(Date1, 10);
            Console.WriteLine("Adding one day is:" + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 67
**Write a program to read a date and make a function to increase date by One Week.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month,Date.Year);
        }

   
        
        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }
      
        static sDate IncreaseDateByOneWeek(sDate Date)
        {

            for (int i = 0; i < 7; i++)
                Date = IncreaseDateByOneDay(Date);

            return Date;
        }
      

    
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = IncreaseDateByOneWeek(Date1);
            Console.WriteLine("Adding one week is:" + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}

```

## Problem 68
**Write a program to read a date and make a function to increase date by X Weeks.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
        }



        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }

        static sDate IncreaseDateByOneWeek(sDate Date)
        {

            for (int i = 0; i < 7; i++)
                Date = IncreaseDateByOneDay(Date);

            return Date;
        }

        static sDate IncreaseDateByXWeek(sDate Date, short Weeks)
        { 
            for (int i = 0 ;i<Weeks;i++)
            {
                Date = IncreaseDateByOneWeek(Date);
            }
            return Date;

        }
    
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = IncreaseDateByXWeek(Date1,10);
            Console.WriteLine("Adding one week is:" + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 69
**Write a program to read a date and make a function to increase date by OneMonth.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
        }



        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }

        static sDate IncreaseDateByOneWeek(sDate Date)
        {

            for (int i = 0; i < 7; i++)
                Date = IncreaseDateByOneDay(Date);

            return Date;
        }

        static sDate IncreaseDateByXWeek(sDate Date, short Weeks)
        { 
            for (int i = 0 ;i<Weeks;i++)
            {
                Date = IncreaseDateByOneWeek(Date);
            }
            return Date;

        }
        
        static sDate IncreaseDateByOneMonth(sDate Date)
        {
            if (Date.Month == 12)
            {
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Month++;
            }

            short NumberOfDaysInCurrentMonth = (short) (NumberofDaysInMonths(Date.Month, Date.Year));

            if (Date.Month > NumberOfDaysInCurrentMonth)
                Date.Month = NumberOfDaysInCurrentMonth;

            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = IncreaseDateByOneMonth(Date1);
            Console.WriteLine("Adding one Month is:" + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 70
**Write a program to read a date and make a function to increase date by X Month.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
        }



        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }

        static sDate IncreaseDateByOneWeek(sDate Date)
        {

            for (int i = 0; i < 7; i++)
                Date = IncreaseDateByOneDay(Date);

            return Date;
        }

        static sDate IncreaseDateByXWeek(sDate Date, short Weeks)
        { 
            for (int i = 0 ;i<Weeks;i++)
            {
                Date = IncreaseDateByOneWeek(Date);
            }
            return Date;

        }
        
        static sDate IncreaseDateByOneMonth(sDate Date)
        {
            if (Date.Month == 12)
            {
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Month++;
            }

            short NumberOfDaysInCurrentMonth = (short) (NumberofDaysInMonths(Date.Month, Date.Year));

            if (Date.Month > NumberOfDaysInCurrentMonth)
                Date.Month = NumberOfDaysInCurrentMonth;

            return Date;
        }

        static sDate IncreaseDateByXMonth(sDate Date, short Month)
        {
            for (int i = 0;i<Month;i++)
                Date = IncreaseDateByOneMonth(Date);

            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = IncreaseDateByXMonth(Date1,5);
            Console.WriteLine("Adding 5 Month is:" + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 71
**Write a program to read a date and make a function to increase date by One Year.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
        }



        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }

        static sDate IncreaseDateByOneWeek(sDate Date)
        {

            for (int i = 0; i < 7; i++)
                Date = IncreaseDateByOneDay(Date);

            return Date;
        }

        static sDate IncreaseDateByXWeek(sDate Date, short Weeks)
        { 
            for (int i = 0 ;i<Weeks;i++)
            {
                Date = IncreaseDateByOneWeek(Date);
            }
            return Date;

        }
        
        static sDate IncreaseDateByOneMonth(sDate Date)
        {
            if (Date.Month == 12)
            {
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Month++;
            }

            short NumberOfDaysInCurrentMonth = (short) (NumberofDaysInMonths(Date.Month, Date.Year));

            if (Date.Month > NumberOfDaysInCurrentMonth)
                Date.Month = NumberOfDaysInCurrentMonth;

            return Date;
        }

        static sDate IncreaseDateByXMonth(sDate Date, short Month)
        {
            for (int i = 0;i<Month;i++)
                Date = IncreaseDateByOneMonth(Date);

            return Date;
        }

        static sDate IncreaseDateByOneYear(sDate Date)
        {
            Date.Year++;
            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = IncreaseDateByOneYear(Date1);
            Console.WriteLine("Adding One Year is:" + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 72
**Write a program to read a date and make a function to increase date by X Years.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
        }



        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }

        static sDate IncreaseDateByOneWeek(sDate Date)
        {

            for (int i = 0; i < 7; i++)
                Date = IncreaseDateByOneDay(Date);

            return Date;
        }

        static sDate IncreaseDateByXWeek(sDate Date, short Weeks)
        { 
            for (int i = 0 ;i<Weeks;i++)
            {
                Date = IncreaseDateByOneWeek(Date);
            }
            return Date;

        }
        
        static sDate IncreaseDateByOneMonth(sDate Date)
        {
            if (Date.Month == 12)
            {
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Month++;
            }

            short NumberOfDaysInCurrentMonth = (short) (NumberofDaysInMonths(Date.Month, Date.Year));

            if (Date.Month > NumberOfDaysInCurrentMonth)
                Date.Month = NumberOfDaysInCurrentMonth;

            return Date;
        }

        static sDate IncreaseDateByXMonth(sDate Date, short Month)
        {
            for (int i = 0;i<Month;i++)
                Date = IncreaseDateByOneMonth(Date);

            return Date;
        }

        static sDate IncreaseDateByOneYear(sDate Date)
        {
            Date.Year++;
            return Date;
        }

        static sDate IncreaseDateByXYear(sDate Date,short Years)
        {

            Date.Year += Years;
            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = IncreaseDateByXYear(Date1,10);
            Console.WriteLine("Adding One Year is:" + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 73
**Write a program to read a date and make a function to increase date by One Decade.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
        }



        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }

        static sDate IncreaseDateByOneWeek(sDate Date)
        {

            for (int i = 0; i < 7; i++)
                Date = IncreaseDateByOneDay(Date);

            return Date;
        }

        static sDate IncreaseDateByXWeek(sDate Date, short Weeks)
        { 
            for (int i = 0 ;i<Weeks;i++)
            {
                Date = IncreaseDateByOneWeek(Date);
            }
            return Date;

        }
        
        static sDate IncreaseDateByOneMonth(sDate Date)
        {
            if (Date.Month == 12)
            {
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Month++;
            }

            short NumberOfDaysInCurrentMonth = (short) (NumberofDaysInMonths(Date.Month, Date.Year));

            if (Date.Month > NumberOfDaysInCurrentMonth)
                Date.Month = NumberOfDaysInCurrentMonth;

            return Date;
        }

        static sDate IncreaseDateByXMonth(sDate Date, short Month)
        {
            for (int i = 0;i<Month;i++)
                Date = IncreaseDateByOneMonth(Date);

            return Date;
        }

        static sDate IncreaseDateByOneYear(sDate Date)
        {
            Date.Year++;
            return Date;
        }

        static sDate IncreaseDateByXYear(sDate Date,short Years)
        {

            Date.Year += Years;
            return Date;
        }

        static sDate IncreaseDateByOneDecade(sDate Date)
        {
            Date.Year += 10;
            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = IncreaseDateByOneDecade(Date1);
            Console.WriteLine("Adding One Decade is:" + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 74
**Write a program to read a date and make a function to increase date by X Decade.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
        }



        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }

        static sDate IncreaseDateByOneWeek(sDate Date)
        {

            for (int i = 0; i < 7; i++)
                Date = IncreaseDateByOneDay(Date);

            return Date;
        }

        static sDate IncreaseDateByXWeek(sDate Date, short Weeks)
        { 
            for (int i = 0 ;i<Weeks;i++)
            {
                Date = IncreaseDateByOneWeek(Date);
            }
            return Date;

        }
        
        static sDate IncreaseDateByOneMonth(sDate Date)
        {
            if (Date.Month == 12)
            {
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Month++;
            }

            short NumberOfDaysInCurrentMonth = (short) (NumberofDaysInMonths(Date.Month, Date.Year));

            if (Date.Month > NumberOfDaysInCurrentMonth)
                Date.Month = NumberOfDaysInCurrentMonth;

            return Date;
        }

        static sDate IncreaseDateByXMonth(sDate Date, short Month)
        {
            for (int i = 0;i<Month;i++)
                Date = IncreaseDateByOneMonth(Date);

            return Date;
        }

        static sDate IncreaseDateByOneYear(sDate Date)
        {
            Date.Year++;
            return Date;
        }

        static sDate IncreaseDateByXYear(sDate Date,short Years)
        {

            Date.Year += Years;
            return Date;
        }

       

        static sDate IncreaseDateByOneDecade(sDate Date)
        {
            Date.Year += 10;
            return Date;
        }
        static sDate IncreaseDateByXDecade(sDate Date, short Years)
        {
            Date.Year += (short)(Years * 10);

            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = IncreaseDateByXDecade(Date1,5);
            Console.WriteLine("Adding 5 Decade is:" + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 75
**Write a program to read a date and make a function to increase date by One Century.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
        }



        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }

        static sDate IncreaseDateByOneWeek(sDate Date)
        {

            for (int i = 0; i < 7; i++)
                Date = IncreaseDateByOneDay(Date);

            return Date;
        }

        static sDate IncreaseDateByXWeek(sDate Date, short Weeks)
        { 
            for (int i = 0 ;i<Weeks;i++)
            {
                Date = IncreaseDateByOneWeek(Date);
            }
            return Date;

        }
        
        static sDate IncreaseDateByOneMonth(sDate Date)
        {
            if (Date.Month == 12)
            {
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Month++;
            }

            short NumberOfDaysInCurrentMonth = (short) (NumberofDaysInMonths(Date.Month, Date.Year));

            if (Date.Month > NumberOfDaysInCurrentMonth)
                Date.Month = NumberOfDaysInCurrentMonth;

            return Date;
        }

        static sDate IncreaseDateByXMonth(sDate Date, short Month)
        {
            for (int i = 0;i<Month;i++)
                Date = IncreaseDateByOneMonth(Date);

            return Date;
        }

        static sDate IncreaseDateByOneYear(sDate Date)
        {
            Date.Year++;
            return Date;
        }

        static sDate IncreaseDateByXYear(sDate Date,short Years)
        {

            Date.Year += Years;
            return Date;
        }

       

        static sDate IncreaseDateByOneDecade(sDate Date)
        {
            Date.Year += 10;
            return Date;
        }
        static sDate IncreaseDateByXDecade(sDate Date, short Years)
        {
            Date.Year += (short)(Years * 10);

            return Date;
        }

        static sDate IncreaseDateByOneCentury(sDate Date)
        {
            Date.Year += 100;

            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = IncreaseDateByOneCentury(Date1);
            Console.WriteLine("Adding One Century is:" + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 76
**Write a program to read a date and make a function to increase date by One Millennium.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }


        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool IsLastMonthInYear(short Month)
        {
            return Month == 12;
        }

        static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
        {
            int TotalDays = 0;

            for (short i = 1; i < Month; i++)
                TotalDays += NumberofDaysInMonths(i, Year);

            TotalDays += Day;

            return TotalDays;
        }
        static bool IsLastDayInMonth(sDate Date)
        {
            return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
        }



        static sDate IncreaseDateByOneDay(sDate Date)
        {
            if (IsLastMonthInYear(Date.Month))
            {
                if (IsLastDayInMonth(Date))
                {
                    Date.Day = 1;
                    Date.Month = 1;
                    Date.Year++;
                }
                else
                {
                    Date.Day++;
                }
            }
            else if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month++;
            }
            else
                Date.Day++;
            return Date;
        }

        static sDate IncreaseDateByOneWeek(sDate Date)
        {

            for (int i = 0; i < 7; i++)
                Date = IncreaseDateByOneDay(Date);

            return Date;
        }

        static sDate IncreaseDateByXWeek(sDate Date, short Weeks)
        { 
            for (int i = 0 ;i<Weeks;i++)
            {
                Date = IncreaseDateByOneWeek(Date);
            }
            return Date;

        }
        
        static sDate IncreaseDateByOneMonth(sDate Date)
        {
            if (Date.Month == 12)
            {
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Month++;
            }

            short NumberOfDaysInCurrentMonth = (short) (NumberofDaysInMonths(Date.Month, Date.Year));

            if (Date.Month > NumberOfDaysInCurrentMonth)
                Date.Month = NumberOfDaysInCurrentMonth;

            return Date;
        }

        static sDate IncreaseDateByXMonth(sDate Date, short Month)
        {
            for (int i = 0;i<Month;i++)
                Date = IncreaseDateByOneMonth(Date);

            return Date;
        }

        static sDate IncreaseDateByOneYear(sDate Date)
        {
            Date.Year++;
            return Date;
        }

        static sDate IncreaseDateByXYear(sDate Date,short Years)
        {

            Date.Year += Years;
            return Date;
        }

       

        static sDate IncreaseDateByOneDecade(sDate Date)
        {
            Date.Year += 10;
            return Date;
        }
        static sDate IncreaseDateByXDecade(sDate Date, short Years)
        {
            Date.Year += (short)(Years * 10);

            return Date;
        }

        static sDate IncreaseDateByOneCentury(sDate Date)
        {
            Date.Year += 100;

            return Date;
        }

        static sDate IncreaseDateByOneMillennium(sDate Date)
        { 
            Date.Year += 1000;
            return Date; 
        }
            static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = IncreaseDateByOneMillennium(Date1);
            Console.WriteLine("Adding One Millennium is:" + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 77
**Write a program to read a date and make a function to Decrease date by One Day.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }
        static bool IsFirstMonthInYear(short Month)
        {
            return Month == 1;
        }

        static bool IsFirstDayInMonth(short Day)
        {
            return Day == 1;
        }

        static sDate DecreaseDateByOneDay(sDate Date)
        {
            if (IsFirstMonthInYear(Date.Month))
            {
                if (IsFirstDayInMonth(Date.Day))
                {
                    Date.Day = 31;
                    Date.Month = 12;
                    Date.Year--;
                }
                else
                {
                    Date.Day--;
                }
            }
            else if (IsFirstDayInMonth(Date.Day))
            {
                Date.Day = (short) (NumberofDaysInMonths(--Date.Month,Date.Year));

            }
            else
                Date.Day--;
            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = DecreaseDateByOneDay(Date1);
            Console.WriteLine("Subtracting one day is : " + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 78
**Write a program to read a date and make a function to Decrease date by X Day.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }
        static bool IsFirstMonthInYear(short Month)
        {
            return Month == 1;
        }

        static bool IsFirstDayInMonth(short Day)
        {
            return Day == 1;
        }

        static sDate DecreaseDateByOneDay(sDate Date)
        {
            if (IsFirstMonthInYear(Date.Month))
            {
                if (IsFirstDayInMonth(Date.Day))
                {
                    Date.Day = 31;
                    Date.Month = 12;
                    Date.Year--;
                }
                else
                {
                    Date.Day--;
                }
            }
            else if (IsFirstDayInMonth(Date.Day))
            {
                Date.Day = (short)(NumberofDaysInMonths(--Date.Month, Date.Year));

            }
            else
                Date.Day--;
            return Date;
        }

        static sDate DecreaseDateByXDay(sDate Date, short Days)
        {
            for (int i = 0; i < Days; i++)
            {
                Date = DecreaseDateByOneDay(Date);
            }
            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = DecreaseDateByXDay(Date1,5);
            Console.WriteLine("Subtracting 5 day is : " + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 79
**Write a program to read a date and make a function to Decrease date by One Week.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }
        static bool IsFirstMonthInYear(short Month)
        {
            return Month == 1;
        }

        static bool IsFirstDayInMonth(short Day)
        {
            return Day == 1;
        }

        static sDate DecreaseDateByOneDay(sDate Date)
        {
            if (IsFirstMonthInYear(Date.Month))
            {
                if (IsFirstDayInMonth(Date.Day))
                {
                    Date.Day = 31;
                    Date.Month = 12;
                    Date.Year--;
                }
                else
                {
                    Date.Day--;
                }
            }
            else if (IsFirstDayInMonth(Date.Day))
            {
                Date.Day = (short)(NumberofDaysInMonths(--Date.Month, Date.Year));

            }
            else
                Date.Day--;
            return Date;
        }

        static sDate DecreaseDateByXDay(sDate Date, short Days)
        {
            for (int i = 0; i < Days; i++)
            {
                Date = DecreaseDateByOneDay(Date);
            }
            return Date;
        }

        static sDate DecreaseDateByOneWeek(sDate Date)
        {
           for (int i = 0;i<7;i++)
                Date = DecreaseDateByOneDay(Date);

            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = DecreaseDateByOneWeek(Date1);
            Console.WriteLine("Subtracting One Week is : " + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 80
**Write a program to read a date and make a function to Decrease date by X Weeks.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }
        static bool IsFirstMonthInYear(short Month)
        {
            return Month == 1;
        }

        static bool IsFirstDayInMonth(short Day)
        {
            return Day == 1;
        }

        static sDate DecreaseDateByOneDay(sDate Date)
        {
            if (IsFirstMonthInYear(Date.Month))
            {
                if (IsFirstDayInMonth(Date.Day))
                {
                    Date.Day = 31;
                    Date.Month = 12;
                    Date.Year--;
                }
                else
                {
                    Date.Day--;
                }
            }
            else if (IsFirstDayInMonth(Date.Day))
            {
                Date.Day = (short)(NumberofDaysInMonths(--Date.Month, Date.Year));

            }
            else
                Date.Day--;
            return Date;
        }

        static sDate DecreaseDateByXDay(sDate Date, short Days)
        {
            for (int i = 0; i < Days; i++)
            {
                Date = DecreaseDateByOneDay(Date);
            }
            return Date;
        }

        static sDate DecreaseDateByOneWeek(sDate Date)
        {
           for (int i = 0;i<7;i++)
                Date = DecreaseDateByOneDay(Date);

            return Date;
        }

        static sDate DecreaseDateByXWeek(sDate Date,short Weeks)
        {
            for (int i = 0;i<Weeks;i++)
                Date = DecreaseDateByOneWeek(Date);

            return Date;

        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = DecreaseDateByXWeek(Date1,10);
            Console.WriteLine("Subtracting 10 Week is : " + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 81
**Write a program to read a date and make a function to Decrease date by X Months.**

```c#
using System;

namespace ConsoleApp3
{
    internal class Program
    {
        struct sDate
        {
            public short Year;
            public short Month;
            public short Day;
        }
        static short ReadYear()
        {
            Console.Write("Please Enter a Year? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadMonth()
        {
            Console.Write("Please Enter a Month? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }

        static short ReadDay()
        {
            Console.Write("Please Enter a Day? ");
            short Number = short.Parse(Console.ReadLine());
            return Number;
        }
        static sDate ReadFullDate()
        {
            sDate Date;

            Date.Day = ReadDay();
            Date.Month = ReadMonth();
            Date.Year = ReadYear();

            return Date;
        }

        static bool LeapYear(int Number)
        {
            return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
        }

        static int NumberofDaysInMonths(short Number, short Year)
        {
            if (Number > 12 || Number < 0)
                return 0;
            if (Number == 2)
            {
                return LeapYear(Year) ? 29 : 28;
            }

            short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
            for (short i = 0; i < arr.Length; i++)
            {
                if (Number == arr[i])
                    return 31;
            }
            return 30;
        }
        static bool IsFirstMonthInYear(short Month)
        {
            return Month == 1;
        }

        static bool IsFirstDayInMonth(short Day)
        {
            return Day == 1;
        }

        static sDate DecreaseDateByOneDay(sDate Date)
        {
            if (IsFirstMonthInYear(Date.Month))
            {
                if (IsFirstDayInMonth(Date.Day))
                {
                    Date.Day = 31;
                    Date.Month = 12;
                    Date.Year--;
                }
                else
                {
                    Date.Day--;
                }
            }
            else if (IsFirstDayInMonth(Date.Day))
            {
                Date.Day = (short)(NumberofDaysInMonths(--Date.Month, Date.Year));

            }
            else
                Date.Day--;
            return Date;
        }

        static sDate DecreaseDateByXDay(sDate Date, short Days)
        {
            for (int i = 0; i < Days; i++)
            {
                Date = DecreaseDateByOneDay(Date);
            }
            return Date;
        }

        static sDate DecreaseDateByOneWeek(sDate Date)
        {
           for (int i = 0;i<7;i++)
                Date = DecreaseDateByOneDay(Date);

            return Date;
        }

        static sDate DecreaseDateByXWeek(sDate Date,short Weeks)
        {
            for (int i = 0;i<Weeks;i++)
                Date = DecreaseDateByOneWeek(Date);

            return Date;

        }

        static sDate DecreaseDateByOneMonths(sDate Date)
        {
            if (Date.Month == 1)
            {
                Date.Month = 12;
                Date.Year--;
            }
            else
            Date.Month--;

            short NumberOfDaysInCurrentMonth = (short)(NumberofDaysInMonths(Date.Month, Date.Year));
            if (NumberOfDaysInCurrentMonth < Date.Day)
                Date.Day = NumberOfDaysInCurrentMonth; 

            return Date;
        }
        static sDate DecreaseDateByXMonths(sDate Date, short Months)
        {
            for (int i =0; i<Months;i++)
                Date = DecreaseDateByOneMonths(Date);

            return Date;
        }
        static void Main(string[] args)
        {
            sDate Date1 = ReadFullDate();
            Console.WriteLine();
            Date1 = DecreaseDateByXMonths(Date1,5);
            Console.WriteLine("Subtracting 5 Months is : " + Date1.Day + "/" + Date1.Month + "/" + Date1.Year);
            Console.ReadKey();
        }
    }
}
```

## Problem 82
**Write a program to read a date and make functions as follows:**  
**1.Overload the DayOfWeekOrder to take date structure.**  
**2.IsEndOfWeek.**  
**3.IsWeekEnd.**  
**4.IsBusinessDay.**
**5.DaysUntilTheEndOfWeek.**
**6.DaysUntilTheEndOfMonth.**
**7.DaysUntilTheEndOfYear.**

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;

struct sDate
{
    public short Year;
    public short Month;
    public short Day;
}

class Program
{
    static bool IsLeapYear(short year)
    {
        return (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
    }



    static short ReadDay()
    {
        Console.Write("\nPlease enter a Day? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadMonth()
    {
        Console.Write("Please enter a Month? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadYear()
    {
        Console.Write("Please enter a Year? ");
        return short.Parse(Console.ReadLine());
    }

    static sDate ReadFullDate()
    {
        sDate date;
        date.Day = ReadDay();
        date.Month = ReadMonth();
        date.Year = ReadYear();
        return date;
    }

    static sDate GetSystemDate()
    {
        DateTime now = DateTime.Now;
        return new sDate
        {
            Year = (short)now.Year,
            Month = (short)now.Month,
            Day = (short)now.Day
        };
    }

    static short NumberOfDaysInAMonth(short month, short year)
    {
        if (month < 1 || month > 12)
            return 0;

        int[] days = { 31, 28, 31, 30, 31, 30, 31, 31, 30, 31, 30, 31 };
        return (short)((month == 2 && IsLeapYear(year)) ? 29 : days[month - 1]);
    }
    static short DayOfWeekOrder(short day, short month, short year)
    {
        short a = (short)((14 - month) / 12);
        short y = (short)(year - a);
        short m = (short)(month + 12 * a - 2);
        return (short)((day + y + (y / 4) - (y / 100) + (y / 400) + (31 * m / 12)) % 7);
    }

    static string DayShortName(short dayOfWeekOrder)
    {
        string[] arrDayNames = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
        return arrDayNames[dayOfWeekOrder];
    }
    static short DayOfWeekOrder(sDate date)
    {
        return DayOfWeekOrder(date.Day, date.Month, date.Year);
    }

    static bool isEndOfWeek(sDate date)
    {
        return DayOfWeekOrder(date.Day, date.Month, date.Year) == 6;
    }

    static bool isWeekend(sDate date)
    {
        short DayIndex = DayOfWeekOrder(date.Day, date.Month, date.Year);
        return DayIndex == 5 || DayIndex == 6;
    }

    static bool IsBusinessDay(sDate date)
    {
        return !(isWeekend(date));
    }

    static short DaysUntilTheEndOfWeek(sDate date)
    {
        return (short)(6 - (DayOfWeekOrder(date.Day, date.Month, date.Year)));
    }

    static short DaysUntilTheEndOfMonth(sDate date)
    {
        return (short)(NumberOfDaysInAMonth(date.Month, date.Year) - date.Day);
    }

    static short DaysUntilTheEndOfYear(sDate date)
    {
        short DaysUntil = 0;
        short Month = date.Month;
        while (Month <=12)
        {
                DaysUntil += NumberOfDaysInAMonth(Month, date.Year);
                Month++;
        }
        return (short)(DaysUntil - date.Day);
    }
    static void Main(string[] args)
    {
        sDate date = GetSystemDate();

        Console.WriteLine("Today is " + DayShortName(DayOfWeekOrder(date)) + " , " + date.Day + "/" + date.Month + "/" + date.Year + "\n");

        Console.WriteLine("Is it End of Week?");
        if (isEndOfWeek(date))
            Console.WriteLine("Yes end of week.\n");
        else
            Console.WriteLine("No NOT end of week.\n");

        Console.WriteLine("Is it Weekend?");
        if (isWeekend(date))
            Console.WriteLine("Yes it is a week end.\n");
        else
            Console.WriteLine("No it is NOT a week end.\n");

        Console.WriteLine("Is it Business Day?");
        if (IsBusinessDay(date))
            Console.WriteLine("Yes it is a business day.\n");
        else
            Console.WriteLine("No it is NOT a business day.\n");

        Console.WriteLine("Days until end of week : " + DaysUntilTheEndOfWeek(date));
        Console.WriteLine("Days until end of month : " + DaysUntilTheEndOfMonth(date));
        Console.WriteLine("Days until end of year : " + DaysUntilTheEndOfYear(date));

        Console.ReadKey();
    }
}
```

## Problem 83
**Write a program to read Vacation Period DateFrom and DateTo and make a function to calculate the actual vacation days. Note: Weekends are excluded**

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;

struct sDate
{
    public short Year;
    public short Month;
    public short Day;
}

class Program
{

    static short ReadDay()
    {
        Console.Write("\nPlease enter a Day? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadMonth()
    {
        Console.Write("Please enter a Month? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadYear()
    {
        Console.Write("Please enter a Year? ");
        return short.Parse(Console.ReadLine());
    }

    static sDate ReadFullDate()
    {
        sDate date;
        date.Day = ReadDay();
        date.Month = ReadMonth();
        date.Year = ReadYear();
        return date;
    }

    static bool LeapYear(int Number)
    {
        return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
    }

    static int NumberofDaysInMonths(short Number, short Year)
    {
        if (Number > 12 || Number < 0)
            return 0;
        if (Number == 2)
        {
            return LeapYear(Year) ? 29 : 28;
        }

        short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
        for (short i = 0; i < arr.Length; i++)
        {
            if (Number == arr[i])
                return 31;
        }
        return 30;
    }

    static short DayOfWeekOrder(short day, short month, short year)
    {
        short a = (short)((14 - month) / 12);
        short y = (short)(year - a);
        short m = (short)(month + 12 * a - 2);
        return (short)((day + y + (y / 4) - (y / 100) + (y / 400) + (31 * m / 12)) % 7);
    }

    static string DayShortName(short dayOfWeekOrder)
    {
        string[] arrDayNames = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
        return arrDayNames[dayOfWeekOrder];
    }
    static short DayOfWeekOrder(sDate date)
    {
        return DayOfWeekOrder(date.Day, date.Month, date.Year);
    }

    static bool isEndOfWeek(sDate date)
    {
        return DayOfWeekOrder(date.Day, date.Month, date.Year) == 6;
    }

    static bool isWeekend(sDate date)
    {
        short DayIndex = DayOfWeekOrder(date.Day, date.Month, date.Year);
        return DayIndex == 5 || DayIndex == 6;
    }

    static bool IsBusinessDay(sDate date)
    {
        return !(isWeekend(date));
    }

    static bool IsLastMonthInYear(short Month)
    {
        return Month == 12;
    }

    static bool IsLastDayInMonth(sDate Date)
    {
        return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
    }

    static sDate IncreaseDateByOneDay(sDate Date)
    {
        if (IsLastMonthInYear(Date.Month))
        {
            if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Day++;
            }
        }
        else if (IsLastDayInMonth(Date))
        {
            Date.Day = 1;
            Date.Month++;
        }
        else
            Date.Day++;
        return Date;
    }
    static bool IsDate1EqualDate2(sDate Date1, sDate Date2)
    {
        return (Date1.Year == Date2.Year) ? ((Date1.Month == Date2.Month) ? (Date1.Day == Date2.Day) ? true : false : false) : false;

    }
    static short ActualVacation(sDate DateFrom , sDate DateTo)
    {
        short DaysCount = 0;
        while(!(IsDate1EqualDate2(DateFrom, DateTo)))
        {
                if (IsBusinessDay(DateFrom))
                DaysCount++;

            DateFrom = IncreaseDateByOneDay(DateFrom);

        }

        return DaysCount;
        
    }

  
    static void Main(string[] args)
    {
        Console.Write("Vacation Starts: ");
        sDate DateFrom = ReadFullDate();

        Console.Write("\nVacation End: ");
        sDate DateTo = ReadFullDate();

        Console.WriteLine("\nVacation From: " + DayShortName(DayOfWeekOrder(DateFrom.Day, DateFrom.Month, DateFrom.Year)) + " , " + DateFrom.Day + "/" + DateFrom.Month + "/" + DateFrom.Year);
        Console.WriteLine("Vacation To: " + DayShortName(DayOfWeekOrder(DateTo.Day, DateTo.Month, DateTo.Year)) + " , " + DateTo.Day + "/" + DateTo.Month + "/" + DateTo.Year);

        Console.WriteLine("\n\nActucal Vacation Days is: " + ActualVacation(DateFrom, DateTo));




        Console.ReadKey();
    }
}
``` 

## Problem 84
**Write a program to read Vacation Start DateFrom and VacationDays, then make a function to calculate the vacation return Date.**

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;

struct sDate
{
    public short Year;
    public short Month;
    public short Day;
}

class Program
{

    static short ReadDay()
    {
        Console.Write("\nPlease enter a Day? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadMonth()
    {
        Console.Write("Please enter a Month? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadYear()
    {
        Console.Write("Please enter a Year? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadVacation()
    {
        Console.Write("\nPlease enter vacation days?");
        return short.Parse(Console.ReadLine());
    }
    static sDate ReadFullDate()
    {
        sDate date;
        date.Day = ReadDay();
        date.Month = ReadMonth();
        date.Year = ReadYear();
        return date;
    }

    static bool LeapYear(int Number)
    {
        return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
    }

    static int NumberofDaysInMonths(short Number, short Year)
    {
        if (Number > 12 || Number < 0)
            return 0;
        if (Number == 2)
        {
            return LeapYear(Year) ? 29 : 28;
        }

        short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
        for (short i = 0; i < arr.Length; i++)
        {
            if (Number == arr[i])
                return 31;
        }
        return 30;
    }

    static short DayOfWeekOrder(short day, short month, short year)
    {
        short a = (short)((14 - month) / 12);
        short y = (short)(year - a);
        short m = (short)(month + 12 * a - 2);
        return (short)((day + y + (y / 4) - (y / 100) + (y / 400) + (31 * m / 12)) % 7);
    }

    static string DayShortName(short dayOfWeekOrder)
    {
        string[] arrDayNames = { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
        return arrDayNames[dayOfWeekOrder];
    }
    static short DayOfWeekOrder(sDate date)
    {
        return DayOfWeekOrder(date.Day, date.Month, date.Year);
    }

    static bool isEndOfWeek(sDate date)
    {
        return DayOfWeekOrder(date.Day, date.Month, date.Year) == 6;
    }

    static bool isWeekend(sDate date)
    {
        short DayIndex = DayOfWeekOrder(date.Day, date.Month, date.Year);
        return DayIndex == 5 || DayIndex == 6;
    }

    static bool IsBusinessDay(sDate date)
    {
        return !(isWeekend(date));
    }

    static bool IsLastMonthInYear(short Month)
    {
        return Month == 12;
    }

    static bool IsLastDayInMonth(sDate Date)
    {
        return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
    }

    static sDate IncreaseDateByOneDay(sDate Date)
    {
        if (IsLastMonthInYear(Date.Month))
        {
            if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Day++;
            }
        }
        else if (IsLastDayInMonth(Date))
        {
            Date.Day = 1;
            Date.Month++;
        }
        else
            Date.Day++;
        return Date;
    }
    static bool IsDate1EqualDate2(sDate Date1, sDate Date2)
    {
        return (Date1.Year == Date2.Year) ? ((Date1.Month == Date2.Month) ? (Date1.Day == Date2.Day) ? true : false : false) : false;

    }
    static short ActualVacation(sDate DateFrom , sDate DateTo)
    {
        short DaysCount = 0;
        while(!(IsDate1EqualDate2(DateFrom, DateTo)))
        {
                if (IsBusinessDay(DateFrom))
                DaysCount++;

            DateFrom = IncreaseDateByOneDay(DateFrom);

        }

        return DaysCount;
        
    }

    static string ReturnDate(sDate DateFrom , short DaysVacation)
    {
        short DaysCount = 0;

        while (DaysVacation != 0)
        {
            if(IsBusinessDay(DateFrom))
            {
                DaysVacation--;
            }
            DateFrom = IncreaseDateByOneDay(DateFrom);
        }

        return DayShortName(DayOfWeekOrder(DateFrom.Day, DateFrom.Month, DateFrom.Year)) + " , " + DateFrom.Day + "/" + DateFrom.Month + "/" +DateFrom.Year;
    }
    static void Main(string[] args)
    {
        Console.Write("Vacation Starts: ");
        sDate DateFrom = ReadFullDate();

        short DaysVacation = ReadVacation();


        Console.WriteLine("\nReturn Date: " + ReturnDate(DateFrom,DaysVacation));




        Console.ReadKey();
    }
}
```

## Problem 85
**Write a program to read Date1& Date2, and check if Date1 is after Date2 or not.**

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;

struct sDate
{
    public short Year;
    public short Month;
    public short Day;
}

class Program
{

    static short ReadDay()
    {
        Console.Write("\nPlease enter a Day? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadMonth()
    {
        Console.Write("Please enter a Month? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadYear()
    {
        Console.Write("Please enter a Year? ");
        return short.Parse(Console.ReadLine());
    }

    static sDate ReadFullDate()
    {
        sDate date;
        date.Day = ReadDay();
        date.Month = ReadMonth();
        date.Year = ReadYear();
        return date;
    }


    static bool IsDate1EqualDate2(sDate Date1, sDate Date2)
    {
        return (Date1.Year == Date2.Year) ? ((Date1.Month == Date2.Month) ? (Date1.Day == Date2.Day) ? true : false : false) : false;

    }

    static bool IsDate1BeforeDate2(sDate Date1, sDate Date2)
    {
        return ((Date1.Year < Date2.Year) ? true : (Date1.Year == Date2.Year) ? (Date1.Month < Date2.Month) ? true : (Date1.Month == Date2.Month) ? (Date1.Day < Date2.Day) : false : false);

    }

    static bool IsDate1AfterDate2(sDate Date1, sDate Date2)
    {
        return (!IsDate1BeforeDate2(Date1,Date2)) && (!IsDate1EqualDate2(Date1, Date2)) ;
    }

    static void Main(string[] args)
    {
        Console.Write("Enter Date1:");
        sDate Date1 = ReadFullDate();

        Console.Write("\nEnter Date2:");
        sDate Date2 = ReadFullDate();

        if (IsDate1AfterDate2(Date1,Date2))
            Console.WriteLine("\nYes, Date1 is After Date2."); 
        else
            Console.WriteLine("\nNo, Date1 is NOT After Date2.");

        Console.ReadKey();
    }
}
```

## Problem 86
**Write a program to read Date1 & Date2, and write a function to compare dates, it should return:**  
**-1 Before**  
**0 Equals**  
**1 After**  

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;

struct sDate
{
    public short Year;
    public short Month;
    public short Day;
}

enum enDateCompare { Before = -1 , Equal = 0 , After = 1  };

class Program
{

    static short ReadDay()
    {
        Console.Write("\nPlease enter a Day? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadMonth()
    {
        Console.Write("Please enter a Month? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadYear()
    {
        Console.Write("Please enter a Year? ");
        return short.Parse(Console.ReadLine());
    }

    static sDate ReadFullDate()
    {
        sDate date;
        date.Day = ReadDay();
        date.Month = ReadMonth();
        date.Year = ReadYear();
        return date;
    }


    static bool IsDate1EqualDate2(sDate Date1, sDate Date2)
    {
        return (Date1.Year == Date2.Year) ? ((Date1.Month == Date2.Month) ? (Date1.Day == Date2.Day) ? true : false : false) : false;

    }

    static bool IsDate1BeforeDate2(sDate Date1, sDate Date2)
    {
        return ((Date1.Year < Date2.Year) ? true : (Date1.Year == Date2.Year) ? (Date1.Month < Date2.Month) ? true : (Date1.Month == Date2.Month) ? (Date1.Day < Date2.Day) : false : false);

    }

    static bool IsDate1AfterDate2(sDate Date1, sDate Date2)
    {
        return (!IsDate1BeforeDate2(Date1,Date2)) && (!IsDate1EqualDate2(Date1, Date2)) ;
    }

    static enDateCompare ComapreDates(sDate date1, sDate date2)
    {
        if (IsDate1BeforeDate2(date1, date2))
            return enDateCompare.Before;
        else if (IsDate1EqualDate2(date1, date2))
            return enDateCompare.Equal;

        return enDateCompare.After;
    }
    static void Main(string[] args)
    {
        Console.Write("Enter Date1:");
        sDate Date1 = ReadFullDate();

        Console.Write("\nEnter Date2:");
        sDate Date2 = ReadFullDate();

        Console.WriteLine("\nCompare Results: " + (int) (ComapreDates(Date1,Date2)));

        Console.ReadKey();
    }
}
```

## Problem 87
**Write a program to read Two Periods and check if they overlap or not.**

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;

struct stDate
{
    public short Year;
    public short Month;
    public short Day;
}

struct stPeriod
{
    public stDate StartDate;
    public stDate EndDate;
}
enum enDateCompare { Before = -1 , Equal = 0 , After = 1  };

class Program
{

    static short ReadDay()
    {
        Console.Write("\nPlease enter a Day? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadMonth()
    {
        Console.Write("Please enter a Month? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadYear()
    {
        Console.Write("Please enter a Year? ");
        return short.Parse(Console.ReadLine());
    }

    static stDate ReadFullDate()
    {
        stDate date;
        date.Day = ReadDay();
        date.Month = ReadMonth();
        date.Year = ReadYear();
        return date;
    }


    static bool IsDate1EqualDate2(stDate Date1, stDate Date2)
    {
        return (Date1.Year == Date2.Year) ? ((Date1.Month == Date2.Month) ? (Date1.Day == Date2.Day) ? true : false : false) : false;

    }

    static bool IsDate1BeforeDate2(stDate Date1, stDate Date2)
    {
        return ((Date1.Year < Date2.Year) ? true : (Date1.Year == Date2.Year) ? (Date1.Month < Date2.Month) ? true : (Date1.Month == Date2.Month) ? (Date1.Day < Date2.Day) : false : false);

    }

    static bool IsDate1AfterDate2(stDate Date1, stDate Date2)
    {
        return (!IsDate1BeforeDate2(Date1,Date2)) && (!IsDate1EqualDate2(Date1, Date2)) ;
    }

    static enDateCompare ComapreDates(stDate date1, stDate date2)
    {
        if (IsDate1BeforeDate2(date1, date2))
            return enDateCompare.Before;
        else if (IsDate1EqualDate2(date1, date2))
            return enDateCompare.Equal;

        return enDateCompare.After;
    }

    static bool IsPeriodOverLap(stPeriod Period1, stPeriod Period2)
    {
        if((ComapreDates(Period2.EndDate,Period1.StartDate) == enDateCompare.Before || ComapreDates(Period2.StartDate, Period1.EndDate) == enDateCompare.After))
        {
                return false;
        }
        return true;
    }
    static void Main(string[] args)
    {
        Console.WriteLine("Enter Period 1:");
        Console.WriteLine("Enter Start Date:");
        stPeriod Period1 = new stPeriod();
        Period1.StartDate = ReadFullDate();
        Console.WriteLine("\nEnter End Date:");
        Period1.EndDate = ReadFullDate();

        Console.WriteLine("\nEnter Period 2:");
        Console.WriteLine("Enter Start Date:");
        stPeriod Period2 = new stPeriod();
        Period2.StartDate = ReadFullDate();
        Console.WriteLine("\nEnter End Date:");
        Period2.EndDate = ReadFullDate();

        if (IsPeriodOverLap(Period1, Period2))
            Console.WriteLine("\nYes, Periods OverLap");
        else
            Console.WriteLine("\nNo, Is NOT Periods OverLap");

        Console.ReadKey();
    }
}
```

## Problem 88
**Write a program to read a Period and calculate period length in days.**

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;
using System.Security.Policy;

struct stDate
{
    public short Year;
    public short Month;
    public short Day;
}

struct stPeriod
{
    public stDate StartDate;
    public stDate EndDate;
}
enum enDateCompare { Before = -1 , Equal = 0 , After = 1  };

class Program
{

    static short ReadDay()
    {
        Console.Write("\nPlease enter a Day? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadMonth()
    {
        Console.Write("Please enter a Month? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadYear()
    {
        Console.Write("Please enter a Year? ");
        return short.Parse(Console.ReadLine());
    }

    static stDate ReadFullDate()
    {
        stDate date;
        date.Day = ReadDay();
        date.Month = ReadMonth();
        date.Year = ReadYear();
        return date;
    }

    static bool LeapYear(int Number)
    {
        return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
    }

    static int NumberofDaysInMonths(short Number, short Year)
    {
        if (Number > 12 || Number < 0)
            return 0;
        if (Number == 2)
        {
            return LeapYear(Year) ? 29 : 28;
        }

        short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
        for (short i = 0; i < arr.Length; i++)
        {
            if (Number == arr[i])
                return 31;
        }
        return 30;
    }

    static bool IsDate1EqualDate2(stDate Date1, stDate Date2)
    {
        return (Date1.Year == Date2.Year) ? ((Date1.Month == Date2.Month) ? (Date1.Day == Date2.Day) ? true : false : false) : false;

    }

    static bool IsDate1BeforeDate2(stDate Date1, stDate Date2)
    {
        return ((Date1.Year < Date2.Year) ? true : (Date1.Year == Date2.Year) ? (Date1.Month < Date2.Month) ? true : (Date1.Month == Date2.Month) ? (Date1.Day < Date2.Day) : false : false);

    }

    static bool IsDate1AfterDate2(stDate Date1, stDate Date2)
    {
        return (!IsDate1BeforeDate2(Date1,Date2)) && (!IsDate1EqualDate2(Date1, Date2)) ;
    }

    static enDateCompare ComapreDates(stDate date1, stDate date2)
    {
        if (IsDate1BeforeDate2(date1, date2))
            return enDateCompare.Before;
        else if (IsDate1EqualDate2(date1, date2))
            return enDateCompare.Equal;

        return enDateCompare.After;
    }
    static bool IsLastMonthInYear(short Month)
    {
        return Month == 12;
    }

    static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
    {
        int TotalDays = 0;

        for (short i = 1; i < Month; i++)
            TotalDays += NumberofDaysInMonths(i, Year);

        TotalDays += Day;

        return TotalDays;
    }
    static bool IsLastDayInMonth(stDate Date)
    {
        return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
    }
    static stDate IncreaseDateByOneDay(stDate Date)
    {
        if (IsLastMonthInYear(Date.Month))
        {
            if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Day++;
            }
        }
        else if (IsLastDayInMonth(Date))
        {
            Date.Day = 1;
            Date.Month++;
        }
        else
            Date.Day++;
        return Date;
    }
    static short GetDifferenceInDays(stDate Date1, stDate Date2, bool IncludeEndDay = false)
    {
        short Days = 0;

        while (IsDate1BeforeDate2(Date1, Date2))
        {
            Days++;
            Date1 = IncreaseDateByOneDay(Date1);
        }


        return IncludeEndDay ? ++Days : Days;
    }

    static bool IsPeriodOverLap(stPeriod Period1, stPeriod Period2)
    {
        if((ComapreDates(Period2.EndDate,Period1.StartDate) == enDateCompare.Before || ComapreDates(Period2.StartDate, Period1.EndDate) == enDateCompare.After))
        {
                return false;
        }
        return true;
    }

    static stPeriod ReadFullPeriod()
    {
        Console.WriteLine("Enter Start Date:");
        stPeriod Period = new stPeriod();
        Period.StartDate = ReadFullDate();
        Console.WriteLine("\nEnter End Date:");
        Period.EndDate = ReadFullDate();

        return Period;
    }

    static short PeriodLength(stPeriod Period , bool IncludeEndDate = false)
    {
        return GetDifferenceInDays(Period.StartDate,Period.EndDate,IncludeEndDate);
    }
    static void Main(string[] args)
    {
        Console.WriteLine("Enter Period 1:");
        stPeriod Period = ReadFullPeriod();

        Console.WriteLine("\nPeriod Length is: " + PeriodLength(Period));
        Console.WriteLine("Period Length (Including End Date) is: " + PeriodLength(Period,true));
        Console.ReadKey();
    }
}
```

## Problem 89
**Write a program to read a Period and Date, then check if date is within this period or not.**

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;
using System.Security.Policy;

struct stDate
{
    public short Year;
    public short Month;
    public short Day;
}

struct stPeriod
{
    public stDate StartDate;
    public stDate EndDate;
}
enum enDateCompare { Before = -1 , Equal = 0 , After = 1  };

class Program
{

    static short ReadDay()
    {
        Console.Write("\nPlease enter a Day? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadMonth()
    {
        Console.Write("Please enter a Month? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadYear()
    {
        Console.Write("Please enter a Year? ");
        return short.Parse(Console.ReadLine());
    }

    static stDate ReadFullDate()
    {
        stDate date;
        date.Day = ReadDay();
        date.Month = ReadMonth();
        date.Year = ReadYear();
        return date;
    }

    static bool LeapYear(int Number)
    {
        return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
    }

    static int NumberofDaysInMonths(short Number, short Year)
    {
        if (Number > 12 || Number < 0)
            return 0;
        if (Number == 2)
        {
            return LeapYear(Year) ? 29 : 28;
        }

        short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
        for (short i = 0; i < arr.Length; i++)
        {
            if (Number == arr[i])
                return 31;
        }
        return 30;
    }

    static bool IsDate1EqualDate2(stDate Date1, stDate Date2)
    {
        return (Date1.Year == Date2.Year) ? ((Date1.Month == Date2.Month) ? (Date1.Day == Date2.Day) ? true : false : false) : false;

    }

    static bool IsDate1BeforeDate2(stDate Date1, stDate Date2)
    {
        return ((Date1.Year < Date2.Year) ? true : (Date1.Year == Date2.Year) ? (Date1.Month < Date2.Month) ? true : (Date1.Month == Date2.Month) ? (Date1.Day < Date2.Day) : false : false);

    }

    static bool IsDate1AfterDate2(stDate Date1, stDate Date2)
    {
        return (!IsDate1BeforeDate2(Date1,Date2)) && (!IsDate1EqualDate2(Date1, Date2)) ;
    }

    static enDateCompare ComapreDates(stDate date1, stDate date2)
    {
        if (IsDate1BeforeDate2(date1, date2))
            return enDateCompare.Before;
        else if (IsDate1EqualDate2(date1, date2))
            return enDateCompare.Equal;

        return enDateCompare.After;
    }
    static bool IsLastMonthInYear(short Month)
    {
        return Month == 12;
    }

    static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
    {
        int TotalDays = 0;

        for (short i = 1; i < Month; i++)
            TotalDays += NumberofDaysInMonths(i, Year);

        TotalDays += Day;

        return TotalDays;
    }
    static bool IsLastDayInMonth(stDate Date)
    {
        return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
    }
    static stDate IncreaseDateByOneDay(stDate Date)
    {
        if (IsLastMonthInYear(Date.Month))
        {
            if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Day++;
            }
        }
        else if (IsLastDayInMonth(Date))
        {
            Date.Day = 1;
            Date.Month++;
        }
        else
            Date.Day++;
        return Date;
    }
    
    static bool isDateInPeriod(stPeriod Period , stDate date2 )
    {
        if (ComapreDates(Period.StartDate,date2) == enDateCompare.Before && ComapreDates(Period.EndDate,date2) == enDateCompare.After)
        {
            return true;
        }
        return false;
    }

    static stPeriod ReadFullPeriod()
    {
        Console.WriteLine("Enter Start Date:");
        stPeriod Period = new stPeriod();
        Period.StartDate = ReadFullDate();
        Console.WriteLine("\nEnter End Date:");
        Period.EndDate = ReadFullDate();

        return Period;
    }

    static void Main(string[] args)
    {
        Console.WriteLine("Enter Period 1:");
        stPeriod Period = ReadFullPeriod();

        Console.WriteLine("Enter Date to check:");
        stDate Date = ReadFullDate();

        if (isDateInPeriod(Period, Date))
            Console.WriteLine("\nYes,Date is within period");
        else
            Console.WriteLine("\nNo, Date is NOT within period");
        Console.ReadKey();
    }
}
```

## Problem 90
**Write a program to read a two periods then count overlap days.**

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;
using System.Security.Policy;

struct stDate
{
    public short Year;
    public short Month;
    public short Day;
}

struct stPeriod
{
    public stDate StartDate;
    public stDate EndDate;
}
enum enDateCompare { Before = -1 , Equal = 0 , After = 1  };

class Program
{

    static short ReadDay()
    {
        Console.Write("\nPlease enter a Day? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadMonth()
    {
        Console.Write("Please enter a Month? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadYear()
    {
        Console.Write("Please enter a Year? ");
        return short.Parse(Console.ReadLine());
    }

    static stDate ReadFullDate()
    {
        stDate date;
        date.Day = ReadDay();
        date.Month = ReadMonth();
        date.Year = ReadYear();
        return date;
    }

    static bool LeapYear(int Number)
    {
        return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
    }

    static int NumberofDaysInMonths(short Number, short Year)
    {
        if (Number > 12 || Number < 0)
            return 0;
        if (Number == 2)
        {
            return LeapYear(Year) ? 29 : 28;
        }

        short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
        for (short i = 0; i < arr.Length; i++)
        {
            if (Number == arr[i])
                return 31;
        }
        return 30;
    }

    static bool IsDate1EqualDate2(stDate Date1, stDate Date2)
    {
        return (Date1.Year == Date2.Year) ? ((Date1.Month == Date2.Month) ? (Date1.Day == Date2.Day) ? true : false : false) : false;

    }

    static bool IsDate1BeforeDate2(stDate Date1, stDate Date2)
    {
        return ((Date1.Year < Date2.Year) ? true : (Date1.Year == Date2.Year) ? (Date1.Month < Date2.Month) ? true : (Date1.Month == Date2.Month) ? (Date1.Day < Date2.Day) : false : false);

    }

    static bool IsDate1AfterDate2(stDate Date1, stDate Date2)
    {
        return (!IsDate1BeforeDate2(Date1,Date2)) && (!IsDate1EqualDate2(Date1, Date2)) ;
    }

    static enDateCompare ComapreDates(stDate date1, stDate date2)
    {
        if (IsDate1BeforeDate2(date1, date2))
            return enDateCompare.Before;
        else if (IsDate1EqualDate2(date1, date2))
            return enDateCompare.Equal;

        return enDateCompare.After;
    }
    static bool IsLastMonthInYear(short Month)
    {
        return Month == 12;
    }

    static int NumberOfDaysFromTheBeginingOfTheYear(short Year, short Month, short Day)
    {
        int TotalDays = 0;

        for (short i = 1; i < Month; i++)
            TotalDays += NumberofDaysInMonths(i, Year);

        TotalDays += Day;

        return TotalDays;
    }
    static bool IsLastDayInMonth(stDate Date)
    {
        return Date.Day == NumberofDaysInMonths(Date.Month, Date.Year);
    }
    static stDate IncreaseDateByOneDay(stDate Date)
    {
        if (IsLastMonthInYear(Date.Month))
        {
            if (IsLastDayInMonth(Date))
            {
                Date.Day = 1;
                Date.Month = 1;
                Date.Year++;
            }
            else
            {
                Date.Day++;
            }
        }
        else if (IsLastDayInMonth(Date))
        {
            Date.Day = 1;
            Date.Month++;
        }
        else
            Date.Day++;
        return Date;
    }
    
    static bool isDateInPeriod(stDate Date , stPeriod Period)
    {
        return !(ComapreDates(Date, Period.StartDate) == enDateCompare.Before || ComapreDates(Date, Period.EndDate) == enDateCompare.After);
    }

    static stPeriod ReadFullPeriod()
    {
        Console.WriteLine("Enter Start Date:");
        stPeriod Period = new stPeriod();
        Period.StartDate = ReadFullDate();
        Console.WriteLine("\nEnter End Date:");
        Period.EndDate = ReadFullDate();

        return Period;
    }
    static bool IsPeriodOverLap(stPeriod Period1, stPeriod Period2)
    {
        if ((ComapreDates(Period2.EndDate, Period1.StartDate) == enDateCompare.Before || ComapreDates(Period2.StartDate, Period1.EndDate) == enDateCompare.After))
        {
            return false;
        }
        return true;
    }

    static short GetDifferenceInDays(stDate Date1, stDate Date2, bool IncludeEndDay = false)
    {
        short Days = 0;

        while (IsDate1BeforeDate2(Date1, Date2))
        {
            Days++;
            Date1 = IncreaseDateByOneDay(Date1);
        }


        return IncludeEndDay ? ++Days : Days;
    }
    static short PeriodLength(stPeriod Period, bool IncludeEndDate = false)
    {
        return GetDifferenceInDays(Period.StartDate, Period.EndDate, IncludeEndDate);
    }

    static int CountOverLap(stPeriod Period1, stPeriod Period2)
    {
        int Period1Length = PeriodLength(Period1,true);
        int Period2Length = PeriodLength(Period2,true);
        int OverLapDays = 0;

        if (!IsPeriodOverLap(Period1, Period2))
            return 0;

        if(Period1Length < Period2Length)
        {
            while(IsDate1BeforeDate2(Period1.StartDate, Period1.EndDate))
            {
                if (isDateInPeriod(Period1.StartDate, Period2))
                    OverLapDays++;

                Period1.StartDate = IncreaseDateByOneDay(Period1.StartDate);
            }
        }
        else
        {
            while(IsDate1BeforeDate2(Period2.StartDate, Period2.EndDate))
            {
                if (isDateInPeriod(Period2.StartDate, Period1))
                    OverLapDays++;

                Period2.StartDate = IncreaseDateByOneDay(Period2.StartDate);
            }
        }

        return OverLapDays;
    }
    static void Main(string[] args)
    {
        Console.WriteLine("Enter Period 1:");
        stPeriod Period1 = ReadFullPeriod();

        Console.WriteLine("Enter Period 2:");
        stPeriod Period2 = ReadFullPeriod();

        Console.WriteLine("\nOverLap Days Count Is: " + CountOverLap(Period1,Period2));

        Console.ReadKey();
    }
}
```

## Problem 91
**Write a program to read Date and write a function to validate this date.**

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;
using System.Security.Policy;

struct stDate
{
    public short Year;
    public short Month;
    public short Day;
}

struct stPeriod
{
    public stDate StartDate;
    public stDate EndDate;
}
enum enDateCompare { Before = -1 , Equal = 0 , After = 1  };

class Program
{

    static short ReadDay()
    {
        Console.Write("\nPlease enter a Day? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadMonth()
    {
        Console.Write("Please enter a Month? ");
        return short.Parse(Console.ReadLine());
    }

    static short ReadYear()
    {
        Console.Write("Please enter a Year? ");
        return short.Parse(Console.ReadLine());
    }

    static stDate ReadFullDate()
    {
        stDate date;
        date.Day = ReadDay();
        date.Month = ReadMonth();
        date.Year = ReadYear();
        return date;
    }

    static bool LeapYear(int Number)
    {
        return ((Number % 400 == 0) || (Number % 100 != 0 && Number % 4 == 0) ? true : false);
    }

    static int NumberofDaysInMonths(short Number, short Year)
    {
        if (Number > 12 || Number < 0)
            return 0;
        if (Number == 2)
        {
            return LeapYear(Year) ? 29 : 28;
        }

        short[] arr = { 1, 3, 5, 7, 8, 10, 12 };
        for (short i = 0; i < arr.Length; i++)
        {
            if (Number == arr[i])
                return 31;
        }
        return 30;
    }

    static bool isValidDate(stDate date)
    {
        if (date.Month <= 12 && date.Month >= 1)
        {
            if (date.Day >= 1 && NumberofDaysInMonths(date.Month, date.Year) >= date.Day)
                return true;
        }
        return false;
    }
    static void Main(string[] args)
    {
        stDate Date = ReadFullDate();

        if(isValidDate(Date))
         Console.WriteLine("\nYes, date is a valide date");
        else
         Console.WriteLine("\nNo, date is NOT a valide date");

        Console.ReadKey();
    }
}
```

## Problem 92
**Write a program to Read Date String, Convert it to date structure, Print Day, Month, Year separately, Then convert Date Structure to string and print it on the screen.**  
**Note: Write the following functions:**  
**StringToDate,DateToString**

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;
using System.Security.Policy;

struct stDate
{
    public short Year;
    public short Month;
    public short Day;
}


enum enDateCompare { Before = -1 , Equal = 0 , After = 1  };

class Program
{

    static string ReadStringDate(string Message)
    {
        Console.Write(Message);
        return Console.ReadLine();
    }

    static stDate StringToDate(string StringDate)
    {
        string[] Splits = StringDate.Split(new string[] { "/" }, StringSplitOptions.None);

        stDate Date = new stDate();
        Date.Day = Convert.ToInt16(Splits[0]);
        Date.Month = Convert.ToInt16(Splits[1]);
        Date.Year = Convert.ToInt16(Splits[2]);

        return Date;

    }

    static string DateToString(stDate Date)
    {
        string sDate = "";

        sDate += Date.Day + "/";
        sDate += Date.Month + "/";
        sDate += Date.Year;

        return sDate;
    }
    static void Main(string[] args)
    {

        string DateString = ReadStringDate("\nPlease Enter Date dd/mm/yyyy? ");

        stDate Date = StringToDate(DateString);
        Console.WriteLine("\nDay:" + Date.Day);
        Console.WriteLine("Month:" + Date.Month);
        Console.WriteLine("Year:"  + Date.Year + "\n");

        Console.WriteLine("You Entered: " + DateToString(Date));

        Console.ReadKey();
    }
}
```


## Problem 93
**Write a program to read Date and write a function to format that date.**

```c#
using System;
using System.Runtime.Remoting.Metadata.W3cXsd2001;
using System.Security.Policy;

struct stDate
{
    public short Year;
    public short Month;
    public short Day;
}


enum enDateCompare { Before = -1 , Equal = 0 , After = 1  };

class Program
{

    static string ReadStringDate(string Message)
    {
        Console.Write(Message);
        return Console.ReadLine();
    }

    static string ReplaceWordInString(string S1, string StringToReplace, string sReplaceTo)
    {
        int pos = S1.IndexOf(StringToReplace);

        while (pos != -1) 
        {
            S1 = S1.Remove(pos, StringToReplace.Length).Insert(pos, sReplaceTo);
            pos = S1.IndexOf(StringToReplace, pos + sReplaceTo.Length);
        }

        return S1;
    }

    static string FormatDate(stDate Date, string DateFormat = "dd/mm/yyyy")
    {
        string FormattedDateString = "";

        FormattedDateString = ReplaceWordInString(DateFormat, "dd" , Date.Day.ToString());
        FormattedDateString = ReplaceWordInString(FormattedDateString, "mm" , Date.Month.ToString());
        FormattedDateString = ReplaceWordInString(FormattedDateString, "yyyy" , Date.Year.ToString());

        return FormattedDateString;

    }
    static stDate StringToDate(string StringDate)
    {
        string[] Splits = StringDate.Split(new string[] { "/" }, StringSplitOptions.None);

        stDate Date = new stDate();
        Date.Day = Convert.ToInt16(Splits[0]);
        Date.Month = Convert.ToInt16(Splits[1]);
        Date.Year = Convert.ToInt16(Splits[2]);

        return Date;

    }

    static string DateToString(stDate Date)
    {
        string sDate = "";

        sDate += Date.Day + "/";
        sDate += Date.Month + "/";
        sDate += Date.Year;

        return sDate;
    }
    static void Main(string[] args)
    {

        string dateString = ReadStringDate("\nPlease Enter Date (dd/mm/yyyy): ");

        stDate date = StringToDate(dateString);

        Console.WriteLine("\n" + FormatDate(date));
        Console.WriteLine("\n" + FormatDate(date, "yyyy/dd/mm"));
        Console.WriteLine("\n" + FormatDate(date, "mm/dd/yyyy"));
        Console.WriteLine("\n" + FormatDate(date, "mm-dd-yyyy"));
        Console.WriteLine("\n" + FormatDate(date, "dd-mm-yyyy"));
        Console.WriteLine("\n" + FormatDate(date, "Day:dd, Month:mm, Year:yyyy"));

        Console.ReadKey();
    }
}
```