---
title: Практическое руководство. Создание и использование сборок с помощью командной строки (Visual Basic)
ms.date: 03/14/2018
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
ms.openlocfilehash: eecd644a7b91492f0a78cf969cfa71ae927609ab
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819408"
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>Практическое руководство. Создание и использование сборок с помощью командной строки (Visual Basic)
Сборка (или библиотека динамической компоновки (DLL)) связывается с программой во время выполнения. Сборка и использование библиотеки DLL рассматривается в следующем сценарии:  
  
-   `MathLibrary.DLL`: Файл библиотеки с методами, вызываемыми во время выполнения. В этом примере библиотека DLL содержит два метода: `Add` и `Multiply`.  
  
-   `Add`: Исходный файл с методом `Add`. Он возвращает сумму своих параметров. Класс `AddClass` с методом `Add` является членом пространства имен `UtilityMethods`.  
  
-   `Mult`: Исходный код, содержащий метод `Multiply`. Он возвращает результат своих параметров. Класс `MultiplyClass` с методом `Multiply` также является членом пространства имен `UtilityMethods`.  
  
-   `TestCode`: Файл с методом `Main`. Он использует методы в DLL-файле для вычисления суммы и результата аргументов времени выполнения.  
  
## <a name="example"></a>Пример  
  
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
  
 Этот файл содержит алгоритм, использующий методы DLL `Add` и `Multiply`. Алгоритм начинается с разбора аргументов, введенных в командной строке: `num1` и `num2`. Затем он вычисляет сумму с помощью метода `Add` в классе `AddClass` и результат с помощью метода `Multiply` в классе `MultiplyClass`.  
  
 Обратите внимание, что `Imports` инструкции в начале файла позволяет использовать неполные имена классов для ссылки на методы DLL во время компиляции, следующим образом:  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 В противном случае потребуется использовать полные имена, как показано ниже.  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>Выполнение  
 Для запуска программы введите имя EXE-файла и два числа, как показано далее.  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы выполнить сборку файла `MathLibrary.DLL`, скомпилируйте два файла, `Add` и `Mult`, с помощью следующей командной строки:  
  
```console  
vbc -target:library -out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 [-Target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) параметр компилятора предписывает компилятору создать библиотеку DLL вместо exe-файла. [-Out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) параметр компилятора, за которым следует имя файла используется для указания имени файла библиотеки DLL. В противном случае компилятор использует первый файл (`Add.vb`) в качестве имени библиотеки DLL.  
  
 Для сборки исполняемого файла `TestCode.exe` служит следующая строка команд:  
  
```console  
vbc -out:TestCode.exe -reference:MathLibrary.DLL TestCode.vb  
```  
  
 **-Out** параметр компилятора предписывает компилятору создать exe-файл и задает имя выходного файла (`TestCode.exe`). Этот параметр компилятора является необязательным. [-Ссылке (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) параметр компилятора указывает DLL-файл или файлы, используемые этой программой.  
  
 Дополнительные сведения о построении из командной строки см. в разделе и [построение из командной строки](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
## <a name="see-also"></a>См. также

- [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)
- [Сборки в .NET](../../../../standard/assembly/index.md)
- [Создание класса, содержащего функции DLL](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
