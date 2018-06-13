---
title: 'Как: Создание и использование сборок с помощью командной строки (Visual Basic)'
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c02f694da4e03b666fa88ea6db8ddb2db4c9637d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33643293"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a><span data-ttu-id="dfb30-102">Как: Создание и использование сборок с помощью командной строки (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfb30-102">How to: Create and Use Assemblies Using the Command Line (Visual Basic)</span></span>
<span data-ttu-id="dfb30-103">Сборка (или библиотека динамической компоновки (DLL)) связывается с программой во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="dfb30-103">An assembly, or a dynamic linking library (DLL), is linked to your program at run time.</span></span> <span data-ttu-id="dfb30-104">Сборка и использование библиотеки DLL рассматривается в следующем сценарии:</span><span class="sxs-lookup"><span data-stu-id="dfb30-104">To demonstrate building and using a DLL, consider the following scenario:</span></span>  
  
-   <span data-ttu-id="dfb30-105">`MathLibrary.DLL`. Файл библиотеки с методами, вызываемыми во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="dfb30-105">`MathLibrary.DLL`: The library file that contains the methods to be called at run time.</span></span> <span data-ttu-id="dfb30-106">В этом примере библиотека DLL содержит два метода: `Add` и `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="dfb30-106">In this example, the DLL contains two methods, `Add` and `Multiply`.</span></span>  
  
-   <span data-ttu-id="dfb30-107">`Add`. Исходный файл с методом `Add`.</span><span class="sxs-lookup"><span data-stu-id="dfb30-107">`Add`: The source file that contains the method `Add`.</span></span> <span data-ttu-id="dfb30-108">Он возвращает сумму своих параметров.</span><span class="sxs-lookup"><span data-stu-id="dfb30-108">It returns the sum of its parameters.</span></span> <span data-ttu-id="dfb30-109">Класс `AddClass` с методом `Add` является членом пространства имен `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="dfb30-109">The class `AddClass` that contains the method `Add` is a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="dfb30-110">`Mult`. Исходный код, содержащий метод `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="dfb30-110">`Mult`: The source code that contains the method `Multiply`.</span></span> <span data-ttu-id="dfb30-111">Он возвращает результат своих параметров.</span><span class="sxs-lookup"><span data-stu-id="dfb30-111">It returns the product of its parameters.</span></span> <span data-ttu-id="dfb30-112">Класс `MultiplyClass` с методом `Multiply` также является членом пространства имен `UtilityMethods`.</span><span class="sxs-lookup"><span data-stu-id="dfb30-112">The class `MultiplyClass` that contains the method `Multiply` is also a member of the namespace `UtilityMethods`.</span></span>  
  
-   <span data-ttu-id="dfb30-113">`TestCode`. Файл с методом `Main`.</span><span class="sxs-lookup"><span data-stu-id="dfb30-113">`TestCode`: The file that contains the `Main` method.</span></span> <span data-ttu-id="dfb30-114">Он использует методы в DLL-файле для вычисления суммы и результата аргументов времени выполнения.</span><span class="sxs-lookup"><span data-stu-id="dfb30-114">It uses the methods in the DLL file to calculate the sum and the product of the run-time arguments.</span></span>  
  
## <a name="example"></a><span data-ttu-id="dfb30-115">Пример</span><span class="sxs-lookup"><span data-stu-id="dfb30-115">Example</span></span>  
  
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
  
 <span data-ttu-id="dfb30-116">Этот файл содержит алгоритм, использующий методы DLL `Add` и `Multiply`.</span><span class="sxs-lookup"><span data-stu-id="dfb30-116">This file contains the algorithm that uses the DLL methods, `Add` and `Multiply`.</span></span> <span data-ttu-id="dfb30-117">Алгоритм начинается с разбора аргументов, введенных в командной строке: `num1` и `num2`.</span><span class="sxs-lookup"><span data-stu-id="dfb30-117">It starts with parsing the arguments entered from the command line, `num1` and `num2`.</span></span> <span data-ttu-id="dfb30-118">Затем он вычисляет сумму с помощью метода `Add` в классе `AddClass` и результат с помощью метода `Multiply` в классе `MultiplyClass`.</span><span class="sxs-lookup"><span data-stu-id="dfb30-118">Then it calculates the sum by using the `Add` method on the `AddClass` class, and the product by using the `Multiply` method on the `MultiplyClass` class.</span></span>  
  
 <span data-ttu-id="dfb30-119">Обратите внимание, что `Imports` инструкции в начале файла позволяет использовать неполные имена классов для ссылки на методы DLL во время компиляции, как показано ниже:</span><span class="sxs-lookup"><span data-stu-id="dfb30-119">Notice that the  `Imports` statement at the beginning of the file enables you to use the unqualified class names to reference the DLL methods at compile time, as follows:</span></span>  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 <span data-ttu-id="dfb30-120">В противном случае потребуется использовать полные имена, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="dfb30-120">Otherwise, you have to use the fully qualified names, as follows:</span></span>  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a><span data-ttu-id="dfb30-121">Выполнение</span><span class="sxs-lookup"><span data-stu-id="dfb30-121">Execution</span></span>  
 <span data-ttu-id="dfb30-122">Для запуска программы введите имя EXE-файла и два числа, как показано далее.</span><span class="sxs-lookup"><span data-stu-id="dfb30-122">To run the program, enter the name of the EXE file, followed by two numbers, as follows:</span></span>  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a><span data-ttu-id="dfb30-123">Компиляция кода</span><span class="sxs-lookup"><span data-stu-id="dfb30-123">Compiling the Code</span></span>  
 <span data-ttu-id="dfb30-124">Чтобы выполнить сборку файла `MathLibrary.DLL`, скомпилируйте два файла, `Add` и `Mult`, с помощью следующей командной строки:</span><span class="sxs-lookup"><span data-stu-id="dfb30-124">To build the file `MathLibrary.DLL`, compile the two files `Add` and `Mult` by using the following command line.</span></span>  
  
```console  
vbc -target:library -out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 <span data-ttu-id="dfb30-125">[-Target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) параметр компилятора сообщает компилятору библиотеку DLL, а не является EXE-файлом.</span><span class="sxs-lookup"><span data-stu-id="dfb30-125">The [-target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) compiler option tells the compiler to output a DLL instead of an EXE file.</span></span> <span data-ttu-id="dfb30-126">[-Out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) параметр компилятора, за которым следует имя файла используется для указания имени файла DLL.</span><span class="sxs-lookup"><span data-stu-id="dfb30-126">The [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) compiler option followed by a file name is used to specify the DLL file name.</span></span> <span data-ttu-id="dfb30-127">В противном случае компилятор использует первый файл (`Add.vb`) в качестве имени библиотеки DLL.</span><span class="sxs-lookup"><span data-stu-id="dfb30-127">Otherwise, the compiler uses the first file (`Add.vb`) as the name of the DLL.</span></span>  
  
 <span data-ttu-id="dfb30-128">Для сборки исполняемого файла `TestCode.exe` служит следующая строка команд:</span><span class="sxs-lookup"><span data-stu-id="dfb30-128">To build the executable file, `TestCode.exe`, use the following command line:</span></span>  
  
```console  
vbc -out:TestCode.exe -reference:MathLibrary.DLL TestCode.vb  
```  
  
 <span data-ttu-id="dfb30-129">**-Out** параметр компилятора указывает компилятору EXE-файл и задает имя выходного файла (`TestCode.exe`).</span><span class="sxs-lookup"><span data-stu-id="dfb30-129">The **-out** compiler option tells the compiler to output an EXE file and specifies the name of the output file (`TestCode.exe`).</span></span> <span data-ttu-id="dfb30-130">Этот параметр компилятора является необязательным.</span><span class="sxs-lookup"><span data-stu-id="dfb30-130">This compiler option is optional.</span></span> <span data-ttu-id="dfb30-131">[-Ссылке (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) указывает параметр компилятора DLL-файл или файлы, используемые этой программой.</span><span class="sxs-lookup"><span data-stu-id="dfb30-131">The [-reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) compiler option specifies the DLL file or files that this program uses.</span></span>  
  
 <span data-ttu-id="dfb30-132">Дополнительные сведения о построении из командной строки см. в разделе и [построение из командной строки](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span><span class="sxs-lookup"><span data-stu-id="dfb30-132">For more information about building from the command line, see  and [Building from the Command Line](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfb30-133">См. также</span><span class="sxs-lookup"><span data-stu-id="dfb30-133">See Also</span></span>  
 [<span data-ttu-id="dfb30-134">Основные понятия программирования</span><span class="sxs-lookup"><span data-stu-id="dfb30-134">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)  
 [<span data-ttu-id="dfb30-135">Сборки и глобальный кэш сборок (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="dfb30-135">Assemblies and the Global Assembly Cache (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="dfb30-136">Создание класса, содержащего функции DLL</span><span class="sxs-lookup"><span data-stu-id="dfb30-136">Creating a Class to Hold DLL Functions</span></span>](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
