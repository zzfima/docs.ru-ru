---
title: "Практическое руководство. Создание и использование сборок с помощью командной строки (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 408ddce3-89e3-4e12-8353-34a49beeb72b
caps.latest.revision: 4
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 630a799331e03860fbee34eab6bea3bb594ef0f0
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-c"></a>Практическое руководство. Создание и использование сборок с помощью командной строки (C#)
Сборка (или библиотека динамической компоновки (DLL)) связывается с программой во время выполнения. Сборка и использование библиотеки DLL рассматривается в следующем сценарии:  
  
-   `MathLibrary.DLL`. Файл библиотеки с методами, вызываемыми во время выполнения. В этом примере библиотека DLL содержит два метода: `Add` и `Multiply`.  
  
-   `Add`. Исходный файл с методом `Add`. Он возвращает сумму своих параметров. Класс `AddClass` с методом `Add` является членом пространства имен `UtilityMethods`.  
  
-   `Mult`. Исходный код, содержащий метод `Multiply`. Он возвращает результат своих параметров. Класс `MultiplyClass` с методом `Multiply` также является членом пространства имен `UtilityMethods`.  
  
-   `TestCode`. Файл с методом `Main`. Он использует методы в DLL-файле для вычисления суммы и результата аргументов времени выполнения.  
  
## <a name="example"></a>Пример  
  
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
  
 Этот файл содержит алгоритм, использующий методы DLL `Add` и `Multiply`. Алгоритм начинается с разбора аргументов, введенных в командной строке: `num1` и `num2`. Затем он вычисляет сумму с помощью метода `Add` в классе `AddClass` и результат с помощью метода `Multiply` в классе `MultiplyClass`.  
  
 Следует отметить, что директива `using` в начале файла позволяет использовать неполные имена классов для ссылки на методы DLL во время компиляции, как показано ниже.  
  
```csharp  
MultiplyClass.Multiply(num1, num2);  
```  
  
 В противном случае потребуется использовать полные имена, как показано ниже.  
  
```csharp  
UtilityMethods.MultiplyClass.Multiply(num1, num2);  
```  
  
## <a name="execution"></a>Выполнение  
 Для запуска программы введите имя EXE-файла и два числа, как показано далее.  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы выполнить сборку файла `MathLibrary.DLL`, скомпилируйте два файла, `Add` и `Mult`, с помощью следующей командной строки:  
  
```csharp  
csc /target:library /out:MathLibrary.DLL Add.cs Mult.cs  
```  
  
 Параметр компилятора [/target:library](../../../../csharp/language-reference/compiler-options/target-library-compiler-option.md) предписывает компилятору создать библиотеку DLL вместо EXE-файла. Параметр компилятора [/out](../../../../csharp/language-reference/compiler-options/out-compiler-option.md) с именем файла используется для указания имени DLL-файла. В противном случае компилятор использует первый файл (`Add.cs`) в качестве имени библиотеки DLL.  
  
 Для сборки исполняемого файла `TestCode.exe` служит следующая строка команд:  
  
```csharp  
csc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.cs  
```  
  
 Параметр компилятора **/out** предписывает компилятору создать EXE-файл и задает имя выходного файла (`TestCode.exe`). Этот параметр компилятора является необязательным. Параметр компилятора [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md) указывает DLL-файл или файлы, используемые этой программой. Дополнительные сведения см. в разделе [/reference](../../../../csharp/language-reference/compiler-options/reference-compiler-option.md).  
  
 Дополнительные сведения о сборке с помощью командной строки см. в разделе [Сборка из командной строки с помощью csc.exe](../../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).  
  
## <a name="see-also"></a>См. также  
 [Руководство по программированию на C#](../../../../csharp/programming-guide/index.md)   
 [Сборки и глобальный кэш сборок (C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)   
 [Создание класса, содержащего функции DLL](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)

