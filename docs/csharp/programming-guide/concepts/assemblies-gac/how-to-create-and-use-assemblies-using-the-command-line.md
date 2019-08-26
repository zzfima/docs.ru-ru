---
title: Практическое руководство. Создание и использование сборок с помощью командной строки (C#)
ms.date: 07/20/2015
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
ms.openlocfilehash: 0a8db22a05d834d15f6e6b7f049f59f86bc1fe1d
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69595964"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="6aa6b-102">Практическое руководство. Создание и использование сборок с помощью командной строки (C#)</span><span class="sxs-lookup"><span data-stu-id="6aa6b-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="6aa6b-103">Сборка (или библиотека динамической компоновки (DLL)) связывается с программой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="6aa6b-104">Сборка и использование библиотеки DLL рассматривается в следующем сценарии:</span><span class="sxs-lookup"><span data-stu-id="6aa6b-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
- <span data-ttu-id="6aa6b-105">`MathLibrary.DLL`: Файл библиотеки с методами, вызываемыми во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="6aa6b-106">В этом примере библиотека DLL содержит два метода: `Add` и `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
- <span data-ttu-id="6aa6b-107">`Add`: Исходный файл с методом `Add`.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="6aa6b-108">Он возвращает сумму своих параметров.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="6aa6b-109">Класс `AddClass` с методом `Add` является членом пространства имен `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="6aa6b-110">`Mult`: Исходный код, содержащий метод `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="6aa6b-111">Он возвращает результат своих параметров.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-111">It returns the product of its parameters.</span></span> <span data-ttu-id="6aa6b-112">Класс `MultiplyClass` с методом `Multiply` также является членом пространства имен `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="6aa6b-113">`TestCode`: Файл с методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="6aa6b-114">Он использует методы в DLL-файле для вычисления суммы и результата аргументов времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6aa6b-115">Пример</span><span class="sxs-lookup"><span data-stu-id="6aa6b-115">Example</span></span>  
  
```csharp  
// File: Add.cs   
namespace UtilityMethods  
{  
    public class AddClass   
    {  
        public static long Add(long i, long j)   
        {   
            return (i + j);  
        }  
    }  
}  
```  
  
```csharp  
// File: Mult.cs  
namespace UtilityMethods   
{  
    public class MultiplyClass  
    {  
        public static long Multiply(long x, long y)   
        {  
            return (x * y);   
        }  
    }  
}  
```  
  
```csharp  
// File: TestCode.cs  
  
using UtilityMethods;  
  
class TestCode  
{  
    static void Main(string[] args)   
    {  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:");  
  
        if (args.Length != 2)  
        {  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>");  
            return;  
        }  
  
        long num1 = long.Parse(args[0]);  
        long num2 = long.Parse(args[1]);  
  
        long sum = AddClass.Add(num1, num2);  
        long product = MultiplyClass.Multiply(num1, num2);  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum);  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product);  
    }  
}  
/* Output (assuming 1234 and 5678 are entered as command-line arguments):  
    Calling methods from MathLibrary.DLL:  
    1234 + 5678 = 6912  
    1234 * 5678 = 7006652          
*/  
```  
  
 <span data-ttu-id="6aa6b-116">Этот файл содержит алгоритм, использующий методы DLL `Add` и `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="6aa6b-117">Алгоритм начинается с разбора аргументов, введенных в командной строке: `num1` и `num2`.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="6aa6b-118">Затем он вычисляет сумму с помощью метода `Add` в классе `AddClass` и результат с помощью метода `Multiply` в классе `MultiplyClass`.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="6aa6b-119">Следует отметить, что директива `using` в начале файла позволяет использовать неполные имена классов для ссылки на методы DLL во время компиляции, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="6aa6b-120">В противном случае потребуется использовать полные имена, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="6aa6b-121">Выполнение</span><span class="sxs-lookup"><span data-stu-id="6aa6b-121">Execution</span></span>  
 <span data-ttu-id="6aa6b-122">Для запуска программы введите имя EXE-файла и два числа, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="6aa6b-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="see-also"></a><span data-ttu-id="6aa6b-123">См. также</span><span class="sxs-lookup"><span data-stu-id="6aa6b-123">See also</span></span>

- [<span data-ttu-id="6aa6b-124">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="6aa6b-124">C# Programming Guide</span></span>](../../index.md)
- [<span data-ttu-id="6aa6b-125">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="6aa6b-125">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="6aa6b-126">Создание класса, содержащего функции DLL</span><span class="sxs-lookup"><span data-stu-id="6aa6b-126">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
