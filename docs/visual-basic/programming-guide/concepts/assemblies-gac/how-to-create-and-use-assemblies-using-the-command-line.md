---
title: Практическое руководство. Создание и использование сборок с помощью командной строки (Visual Basic)
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: eecd644a7b91492f0a78cf969cfa71ae927609ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022289"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="5b58d-102">Практическое руководство. Создание и использование сборок с помощью командной строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5b58d-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="5b58d-103">Сборка (или библиотека динамической компоновки (DLL)) связывается с программой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5b58d-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="5b58d-104">Сборка и использование библиотеки DLL рассматривается в следующем сценарии:</span><span class="sxs-lookup"><span data-stu-id="5b58d-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
- <span data-ttu-id="5b58d-105">`MathLibrary.DLL`: Файл библиотеки с методами, вызываемыми во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="5b58d-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="5b58d-106">В этом примере библиотека DLL содержит два метода: `Add` и `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="5b58d-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
- <span data-ttu-id="5b58d-107">`Add`: Исходный файл с методом `Add`.</span><span class="sxs-lookup"><span data-stu-id="5b58d-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="5b58d-108">Он возвращает сумму своих параметров.</span><span class="sxs-lookup"><span data-stu-id="5b58d-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="5b58d-109">Класс `AddClass` с методом `Add` является членом пространства имен `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="5b58d-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="5b58d-110">`Mult`: Исходный код, содержащий метод `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="5b58d-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="5b58d-111">Он возвращает результат своих параметров.</span><span class="sxs-lookup"><span data-stu-id="5b58d-111">It returns the product of its parameters.</span></span> <span data-ttu-id="5b58d-112">Класс `MultiplyClass` с методом `Multiply` также является членом пространства имен `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="5b58d-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
- <span data-ttu-id="5b58d-113">`TestCode`: Файл с методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="5b58d-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="5b58d-114">Он использует методы в DLL-файле для вычисления суммы и результата аргументов времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="5b58d-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5b58d-115">Пример</span><span class="sxs-lookup"><span data-stu-id="5b58d-115">Example</span></span>  
  
```vb  
' File: Add.vb   
Namespace UtilityMethods  
    Public Class AddClass  
        Public Shared Function Add(ByVal i As Long, ByVal j As Long) As Long  
            Return i + j  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: Mult.vb  
Namespace UtilityMethods  
    Public Class MultiplyClass  
        Public Shared Function Multiply(ByVal x As Long, ByVal y As Long) As Long  
            Return x * y  
        End Function  
    End Class  
End Namespace  
```  
  
```vb  
' File: TestCode.vb  
  
Imports UtilityMethods  
  
Module Test  
  
    Sub Main(ByVal args As String())  
  
        System.Console.WriteLine("Calling methods from MathLibrary.DLL:")  
  
        If args.Length <> 2 Then  
            System.Console.WriteLine("Usage: TestCode <num1> <num2>")  
            Return  
        End If  
  
        Dim num1 As Long = Long.Parse(args(0))  
        Dim num2 As Long = Long.Parse(args(1))  
  
        Dim sum As Long = AddClass.Add(num1, num2)  
        Dim product As Long = MultiplyClass.Multiply(num1, num2)  
  
        System.Console.WriteLine("{0} + {1} = {2}", num1, num2, sum)  
        System.Console.WriteLine("{0} * {1} = {2}", num1, num2, product)  
  
    End Sub  
  
End Module  
  
' Output (assuming 1234 and 5678 are entered as command-line arguments):  
' Calling methods from MathLibrary.DLL:  
' 1234 + 5678 = 6912  
' 1234 * 5678 = 7006652  
```  
  
 <span data-ttu-id="5b58d-116">Этот файл содержит алгоритм, использующий методы DLL `Add` и `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="5b58d-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="5b58d-117">Алгоритм начинается с разбора аргументов, введенных в командной строке: `num1` и `num2`.</span><span class="sxs-lookup"><span data-stu-id="5b58d-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="5b58d-118">Затем он вычисляет сумму с помощью метода `Add` в классе `AddClass` и результат с помощью метода `Multiply` в классе `MultiplyClass`.</span><span class="sxs-lookup"><span data-stu-id="5b58d-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="5b58d-119">Обратите внимание, что `Imports` инструкции в начале файла позволяет использовать неполные имена классов для ссылки на методы DLL во время компиляции, следующим образом:</span><span class="sxs-lookup"><span data-stu-id="5b58d-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="5b58d-120">В противном случае потребуется использовать полные имена, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="5b58d-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="5b58d-121">Выполнение</span><span class="sxs-lookup"><span data-stu-id="5b58d-121">Execution</span></span>  
 <span data-ttu-id="5b58d-122">Для запуска программы введите имя EXE-файла и два числа, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="5b58d-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="5b58d-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="5b58d-123">Compiling the Code</span></span>  
 <span data-ttu-id="5b58d-124">Чтобы выполнить сборку файла `MathLibrary.DLL`, скомпилируйте два файла, `Add` и `Mult`, с помощью следующей командной строки:</span><span class="sxs-lookup"><span data-stu-id="5b58d-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```console  
vbc -target:library -out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 <span data-ttu-id="5b58d-125">[-Target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) параметр компилятора предписывает компилятору создать библиотеку DLL вместо exe-файла.</span><span class="sxs-lookup"><span data-stu-id="5b58d-125">The [-target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="5b58d-126">[-Out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) параметр компилятора, за которым следует имя файла используется для указания имени файла библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="5b58d-126">The [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="5b58d-127">В противном случае компилятор использует первый файл (`Add.vb`) в качестве имени библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="5b58d-127">Otherwise, the compiler uses the first file (`Add.vb`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="5b58d-128">Для сборки исполняемого файла `TestCode.exe` служит следующая строка команд:</span><span class="sxs-lookup"><span data-stu-id="5b58d-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```console  
vbc -out:TestCode.exe -reference:MathLibrary.DLL TestCode.vb  
```  
  
 <span data-ttu-id="5b58d-129">**-Out** параметр компилятора предписывает компилятору создать exe-файл и задает имя выходного файла (`TestCode.exe`).</span><span class="sxs-lookup"><span data-stu-id="5b58d-129">The **-out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="5b58d-130">Этот параметр компилятора является необязательным.</span><span class="sxs-lookup"><span data-stu-id="5b58d-130">This compiler option is optional.</span></span> <span data-ttu-id="5b58d-131">[-Ссылке (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) параметр компилятора указывает DLL-файл или файлы, используемые этой программой.</span><span class="sxs-lookup"><span data-stu-id="5b58d-131">The [-reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) compiler option specifies the DLL file or files that this program uses.</span></span>  
  
 <span data-ttu-id="5b58d-132">Дополнительные сведения о построении из командной строки см. в разделе и [построение из командной строки](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="5b58d-132">For more information about building from the command line, see  and [Building from the Command Line](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b58d-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5b58d-133">See also</span></span>

- [<span data-ttu-id="5b58d-134">Основные понятия программирования</span><span class="sxs-lookup"><span data-stu-id="5b58d-134">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="5b58d-135">Сборки в .NET</span><span class="sxs-lookup"><span data-stu-id="5b58d-135">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="5b58d-136">Создание класса, содержащего функции DLL</span><span class="sxs-lookup"><span data-stu-id="5b58d-136">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
