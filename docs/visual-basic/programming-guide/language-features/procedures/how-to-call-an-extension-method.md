---
title: Как выполнить Вызов метода расширения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
ms.openlocfilehash: 4e9391a4c4a159cd5e198689bf7af7cd64c3a872
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54620452"
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>Как выполнить Вызов метода расширения (Visual Basic)
Методы расширения позволяют добавлять методы к существующему классу. После объявления и добавлены в область действия методом расширения, его можно вызывать как метод экземпляра типа, который он расширяет. Дополнительные сведения о том, как написание метода расширения, см. в разделе [как: Написание метода расширения](./how-to-write-an-extension-method.md).  
  
 Приведенные ниже инструкции относятся к методу расширения `PrintAndPunctuate`, для второго параметра, который будет отображать экземпляр строки и вызывает его, любое значение отправляется в `punc`.  
  
```vb  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
 Метод должен находиться в области, при вызове.  
  
### <a name="to-call-an-extension-method"></a>Для вызова метода расширения  
  
1.  Объявите переменную, которая имеет тип данных первого параметра метода расширения. Для `PrintAndPunctuate`, вам потребуется <xref:System.String> переменной:  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  Переменная будет вызвать метод расширения, что его значение, привязанное к первому параметру `aString`. Следующая инструкция вызова будет отображать `Ready?`.  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     Обратите внимание, что вызов этого метода расширения выглядит, как вызов любого из <xref:System.String> экземпляра методов, которым требуется один параметр:  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  Объявите другую строковую переменную и вызовите метод еще раз, чтобы увидеть, что он работает с любой строкой.  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     Результатом является это время: `or not!!!`.  
  
## <a name="example"></a>Пример  
 Ниже приведен полный пример создания и использования метода простого расширения.  
  
```vb  
Imports System.Runtime.CompilerServices  
Imports ConsoleApplication1.StringExtensions  
  
Module Module1  
  
    Sub Main()  
  
        Dim example = "Hello"  
        example.PrintAndPunctuate(".")  
        example.PrintAndPunctuate("!!!!")  
  
        Dim example2 = "Goodbye"  
        example2.PrintAndPunctuate("?")  
    End Sub  
  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
End Module  
  
' Output:  
' Hello.  
' Hello!!!!  
' Goodbye?  
```  
  
## <a name="see-also"></a>См. также
- [Практическое руководство. Написание метода расширения](./how-to-write-an-extension-method.md)
- [Методы расширения](./extension-methods.md)
- [Область, в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
