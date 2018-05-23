---
title: Практическое руководство. Создание и использование сборок с помощью командной строки (C#)
ms.date: 07/20/2015
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
ms.openlocfilehash: ef872992f17eaaeacf451fa10ef792c47445df80
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a><span data-ttu-id="904c3-102">Практическое руководство. Создание и использование сборок с помощью командной строки (C#)</span><span class="sxs-lookup"><span data-stu-id="904c3-102">How to: Create and Use Assemblies Using the Command Line (C#)</span></span>
<span data-ttu-id="904c3-103">Сборка (или библиотека динамической компоновки (DLL)) связывается с программой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="904c3-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="904c3-104">Сборка и использование библиотеки DLL рассматривается в следующем сценарии:</span><span class="sxs-lookup"><span data-stu-id="904c3-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="904c3-105">`MathLibrary.DLL`. Файл библиотеки с методами, вызываемыми во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="904c3-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="904c3-106">В этом примере библиотека DLL содержит два метода: `Add` и `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="904c3-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="904c3-107">`Add`. Исходный файл с методом `Add`.</span><span class="sxs-lookup"><span data-stu-id="904c3-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="904c3-108">Он возвращает сумму своих параметров.</span><span class="sxs-lookup"><span data-stu-id="904c3-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="904c3-109">Класс `AddClass` с методом `Add` является членом пространства имен `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="904c3-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="904c3-110">`Mult`. Исходный код, содержащий метод `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="904c3-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="904c3-111">Он возвращает результат своих параметров.</span><span class="sxs-lookup"><span data-stu-id="904c3-111">It returns the product of its parameters.</span></span> <span data-ttu-id="904c3-112">Класс `MultiplyClass` с методом `Multiply` также является членом пространства имен `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="904c3-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="904c3-113">`TestCode`. Файл с методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="904c3-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="904c3-114">Он использует методы в DLL-файле для вычисления суммы и результата аргументов времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="904c3-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="904c3-115">Пример</span><span class="sxs-lookup"><span data-stu-id="904c3-115">Example</span></span>  
  
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
  
 <span data-ttu-id="904c3-116">Этот файл содержит алгоритм, использующий методы DLL `Add` и `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="904c3-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="904c3-117">Алгоритм начинается с разбора аргументов, введенных в командной строке: `num1` и `num2`.</span><span class="sxs-lookup"><span data-stu-id="904c3-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="904c3-118">Затем он вычисляет сумму с помощью метода `Add` в классе `AddClass` и результат с помощью метода `Multiply` в классе `MultiplyClass`.</span><span class="sxs-lookup"><span data-stu-id="904c3-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="904c3-119">Следует отметить, что директива `using` в начале файла позволяет использовать неполные имена классов для ссылки на методы DLL во время компиляции, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="904c3-119">Notice that the `using` directive at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 <span data-ttu-id="904c3-120">В противном случае потребуется использовать полные имена, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="904c3-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a><span data-ttu-id="904c3-121">Выполнение</span><span class="sxs-lookup"><span data-stu-id="904c3-121">Execution</span></span>  
 <span data-ttu-id="904c3-122">Для запуска программы введите имя EXE-файла и два числа, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="904c3-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="904c3-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="904c3-123">Compiling the Code</span></span>  
 <span data-ttu-id="904c3-124">Чтобы выполнить сборку файла `MathLibrary.DLL`, скомпилируйте два файла, `Add` и `Mult`, с помощью следующей командной строки:</span><span class="sxs-lookup"><span data-stu-id="904c3-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```csharp  
csc /target:library /out:MathLibrary.DLL Add.cs Mult.cs  
```  
  
 <span data-ttu-id="904c3-125">Параметр компилятора [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) предписывает компилятору создать библиотеку DLL вместо EXE-файла.</span><span class="sxs-lookup"><span data-stu-id="904c3-125">The [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="904c3-126">Параметр компилятора [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) с именем файла используется для указания имени DLL-файла.</span><span class="sxs-lookup"><span data-stu-id="904c3-126">The [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="904c3-127">В противном случае компилятор использует первый файл (`Add.cs`) в качестве имени библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="904c3-127">Otherwise, the compiler uses the first file (`Add.cs`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="904c3-128">Для сборки исполняемого файла `TestCode.exe` служит следующая строка команд:</span><span class="sxs-lookup"><span data-stu-id="904c3-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```csharp  
csc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.cs  
```  
  
 <span data-ttu-id="904c3-129">Параметр компилятора **/out** предписывает компилятору создать EXE-файл и задает имя выходного файла (`TestCode.exe`).</span><span class="sxs-lookup"><span data-stu-id="904c3-129">The **/out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="904c3-130">Этот параметр компилятора является необязательным.</span><span class="sxs-lookup"><span data-stu-id="904c3-130">This compiler option is optional.</span></span> <span data-ttu-id="904c3-131">Параметр компилятора [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) указывает DLL-файл или файлы, используемые этой программой.</span><span class="sxs-lookup"><span data-stu-id="904c3-131">The [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) compiler option specifies the DLL file or files that this program uses.</span></span> <span data-ttu-id="904c3-132">Дополнительные сведения см. в разделе [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span><span class="sxs-lookup"><span data-stu-id="904c3-132">For more information, see [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).</span></span>  
  
 <span data-ttu-id="904c3-133">Дополнительные сведения о сборке с помощью командной строки см. в разделе [Сборка из командной строки с помощью csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span><span class="sxs-lookup"><span data-stu-id="904c3-133">For more information about building from the command line, see [Command-line Building With csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="904c3-134">См. также</span><span class="sxs-lookup"><span data-stu-id="904c3-134">See Also</span></span>  
 [<span data-ttu-id="904c3-135">Руководство по программированию на C#</span><span class="sxs-lookup"><span data-stu-id="904c3-135">C# Programming Guide</span></span>](../../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="904c3-136">Сборки и глобальный кэш сборок (C#)</span><span class="sxs-lookup"><span data-stu-id="904c3-136">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="904c3-137">Создание класса, содержащего функции DLL</span><span class="sxs-lookup"><span data-stu-id="904c3-137">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
