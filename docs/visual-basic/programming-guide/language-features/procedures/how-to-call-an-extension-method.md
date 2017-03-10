---
title: "Практическое руководство. Вызов метода расширения (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "вызов методов расширения"
  - "методы расширения [Visual Basic]"
ms.assetid: df07750f-40f4-4c07-a79e-1113a27cfbea
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Практическое руководство. Вызов метода расширения (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Методы расширения позволяют добавлять методы к существующему классу.  После объявления и помещения в область видимости метод расширения можно вызвать как метод экземпляра типа, который он расширяет.  Дополнительные сведения о том, как написать метод расширения, содержатся в разделе [Практическое руководство. Написание метода расширения](../../../../visual-basic/programming-guide/language-features/procedures/how-to-write-an-extension-method.md).  
  
 Следующие инструкции относятся к методу расширения `PrintAndPunctuate`, который будет отображать экземпляр вызывающей его строки и любое значение, отправленное во второй параметр `punc`.  
  
```vb#  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
  
```  
  
 Метод должен быть в области видимости, в которой он вызывается.  
  
### Для вызова метода расширения  
  
1.  Объявите переменную с типом данных первого аргумента метода расширения.  Для `PrintAndPunctuate` необходима переменная <xref:System.String>:  
  
    ```  
    Dim example = "Ready"  
    ```  
  
2.  Эта переменная будет вызвать метод расширения, и ее значение связано с первым параметром `aString`.  Следующая инструкция вызова будет отображать `Ready?`.  
  
    ```  
    example.PrintAndPunctuate("?")  
    ```  
  
     Обратите внимание, что вызов этого метода расширения выглядит, как вызов любого из методов экземпляра <xref:System.String>, требующих одного параметра:  
  
    ```  
    example.EndsWith("dy")  
    example.IndexOf("R")  
    ```  
  
3.  Объявите другую строковую переменную и вызовите метод еще раз, чтобы увидеть, что он работает с любой строкой.  
  
    ```  
    Dim example2 = " or not"  
    example2.PrintAndPunctuate("!!!")  
    ```  
  
     Результат на этот раз: `or not!!!`.  
  
## Пример  
 Ниже приведен полный пример создания и использования метода простого расширения.  
  
```vb#  
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
  
## См. также  
 [Практическое руководство. Написание метода расширения](../../../../visual-basic/programming-guide/language-features/procedures/how-to-write-an-extension-method.md)   
 [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Область видимости в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)