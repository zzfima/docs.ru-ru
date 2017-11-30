---
title: "Практическое руководство. Вызов метода расширения (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- calling extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 25b5a86af15694e6f64f96a5d5d645a01f8f1f12
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-call-an-extension-method-visual-basic"></a>Практическое руководство. Вызов метода расширения (Visual Basic)
Методы расширения позволяют добавлять методы в существующий класс. После объявления метода расширения и добавлены в область действия, его можно вызывать как метод экземпляра типа, который он расширяет. Дополнительные сведения о написании метода расширения см. в разделе [как: написание метода расширения](./how-to-write-an-extension-method.md).  
  
 Следующие инструкции относятся к методу расширения `PrintAndPunctuate`, который будет отображать экземпляр строки и вызывает его любое значение отправляется для второго параметра `punc`.  
  
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
  
 Метод должен быть в области, когда он вызывается.  
  
### <a name="to-call-an-extension-method"></a>Вызов метода расширения  
  
1.  Объявите переменную, которая имеет тип данных первого параметра метода расширения. Для `PrintAndPunctuate`, требуется <xref:System.String> переменной:  
  
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
  
3.  Объявите другую строковую переменную и вызовите метод, чтобы проверить, что он работает с любой строкой.  
  
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
 [Практическое руководство. Написание метода расширения](./how-to-write-an-extension-method.md)  
 [Методы расширения](./extension-methods.md)  
 [Область в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
