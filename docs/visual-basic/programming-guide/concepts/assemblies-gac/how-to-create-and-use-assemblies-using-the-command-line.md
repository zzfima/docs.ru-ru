---
title: "Как: Создание и использование сборок с помощью командной строки (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 72f3e91f9fb88019f937dcd281aa14ab4e887daf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>Как: Создание и использование сборок с помощью командной строки (Visual Basic)
Сборка (или библиотека динамической компоновки (DLL)) связывается с программой во время выполнения. Сборка и использование библиотеки DLL рассматривается в следующем сценарии:  
  
-   `MathLibrary.DLL`. Файл библиотеки с методами, вызываемыми во время выполнения. В этом примере библиотека DLL содержит два метода: `Add` и `Multiply`.  
  
-   `Add`. Исходный файл с методом `Add`. Он возвращает сумму своих параметров. Класс `AddClass` с методом `Add` является членом пространства имен `UtilityMethods`.  
  
-   `Mult`. Исходный код, содержащий метод `Multiply`. Он возвращает результат своих параметров. Класс `MultiplyClass` с методом `Multiply` также является членом пространства имен `UtilityMethods`.  
  
-   `TestCode`. Файл с методом `Main`. Он использует методы в DLL-файле для вычисления суммы и результата аргументов времени выполнения.  
  
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
  
 Обратите внимание, что `Imports` инструкции в начале файла позволяет использовать неполные имена классов для ссылки на методы DLL во время компиляции, как показано ниже:  
  
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
  
```vb  
vbc /target:library /out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 [/Target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) параметр компилятора сообщает компилятору библиотеку DLL, а не является EXE-файлом. [/Out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) параметр компилятора, за которым следует имя файла используется для указания имени файла DLL. В противном случае компилятор использует первый файл (`Add.vb`) в качестве имени библиотеки DLL.  
  
 Для сборки исполняемого файла `TestCode.exe` служит следующая строка команд:  
  
```vb  
vbc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.vb  
```  
  
 Параметр компилятора **/out** предписывает компилятору создать EXE-файл и задает имя выходного файла (`TestCode.exe`). Этот параметр компилятора является необязательным. [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) указывает параметр компилятора DLL-файл или файлы, используемые этой программой.  
  
 Дополнительные сведения о построении из командной строки см. в разделе и [построение из командной строки](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
## <a name="see-also"></a>См. также  
 [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)  
 [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [Создание класса, содержащего функции DLL](../../../../framework/interop/creating-a-class-to-hold-dll-functions.md)
