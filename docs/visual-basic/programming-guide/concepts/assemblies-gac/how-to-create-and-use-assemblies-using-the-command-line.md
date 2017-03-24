---
title: "Практическое руководство: Создание и использование сборок с помощью командной строки (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 229ff9fb-1bd1-403b-946b-526104864c60
caps.latest.revision: 6
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 363bca806736e5540165ea96e9b4fe60d0968098
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-create-and-use-assemblies-using-the-command-line-visual-basic"></a>Практическое руководство: Создание и использование сборок с помощью командной строки (Visual Basic)
Сборки или библиотека динамической компоновки (DLL), связан программы во время выполнения. Чтобы продемонстрировать создание и использование библиотеки DLL, рассмотрим следующий сценарий:  
  
-   `MathLibrary.DLL`: Файл библиотеки, который содержит методы для вызова во время выполнения. В этом примере библиотека DLL содержит два метода `Add` и `Multiply`.  
  
-   `Add`: Исходный файл, содержащий метод `Add`. Он возвращает сумму своих параметров. Класс `AddClass` с методом `Add` входит в пространство имен `UtilityMethods`.  
  
-   `Mult`: Исходный код, содержащий метод `Multiply`. Он возвращает результат своих параметров. Класс `MultiplyClass` с методом `Multiply` также является членом пространства имен `UtilityMethods`.  
  
-   `TestCode`: Файл, содержащий `Main` метод. Он использует методы в DLL-файле для вычисления суммы и результата аргументов времени выполнения.  
  
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
  
 Этот файл содержит алгоритм, использующий методы DLL `Add` и `Multiply`. Он начинается с разбора аргументов, введенных из командной строки, `num1` и `num2`. Затем он вычисляет сумму, используя `Add` метод `AddClass` класс и продукта с помощью `Multiply` метод `MultiplyClass` класса.  
  
 Обратите внимание, что `Imports` инструкции в начале файла позволяет использовать неполные имена классов для ссылки на методы DLL во время компиляции, как показано ниже:  
  
```vb  
MultiplyClass.Multiply(num1, num2)  
```  
  
 В противном случае необходимо использовать полные имена, как показано ниже:  
  
```vb  
UtilityMethods.MultiplyClass.Multiply(num1, num2)  
```  
  
## <a name="execution"></a>Выполнение  
 Для запуска программы введите имя EXE-файла и два числа, как показано ниже:  
  
 `TestCode 1234 5678`  
  
## <a name="compiling-the-code"></a>Компиляция кода  
 Чтобы создать файл `MathLibrary.DLL`, скомпилируйте два файла `Add` и `Mult` с помощью следующей командной строки.  
  
```vb  
vbc /target:library /out:MathLibrary.DLL Add.vb Mult.vb  
```  
  
 [/Target (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/target.md) параметр компилятора сообщает компилятору DLL, вместо файла EXE. [/Out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md) параметр компилятора, за которым следует имя файла используется для указания имени файла библиотеки DLL. В противном случае, компилятор использует первый файл (`Add.vb`) как имя библиотеки DLL.  
  
 Для построения исполняемого файла `TestCode.exe`, используйте следующую команду:  
  
```vb  
vbc /out:TestCode.exe /reference:MathLibrary.DLL TestCode.vb  
```  
  
 **/Out** параметр компилятора указывает компилятору EXE-файл и задает имя выходного файла (`TestCode.exe`). Этот параметр является необязательным. [/Reference (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/reference.md) параметр компилятора указывает DLL-файл или файлы, используемые этой программой.  
  
 Дополнительные сведения о построении из командной строки см. в разделе и [построение из командной строки](../../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md).  
  
## <a name="see-also"></a>См. также  
 [Основные понятия программирования](../../../../visual-basic/programming-guide/concepts/index.md)   
 [Сборки и глобальный кэш сборок (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Создание класса, содержащего функции DLL](http://msdn.microsoft.com/library/e08e4c34-0223-45f7-aa55-a3d8dd979b0f)
