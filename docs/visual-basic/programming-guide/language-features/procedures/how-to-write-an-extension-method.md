---
title: "Практическое руководство. Написание метода расширения (Visual Basic) | Microsoft Docs"
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
  - "расширение типов данных"
  - "методы расширения [Visual Basic]"
  - "запись методов расширения"
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# Практическое руководство. Написание метода расширения (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Методы расширения позволяют добавлять методы к существующему классу.  Метод расширения может вызываться так, как если бы он был экземпляром этого класса.  
  
### Для определения метода расширения  
  
1.  Откройте новое или существующее приложение Visual Basic в Visual Studio.  
  
2.  Включите следующий оператор импорта в верхнюю часть файла, в котором нужно определить метод расширения:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  Внутри модуля в новом или существующем приложении определите метод с атрибутом расширения:  
  
    ```  
    <Extension()>  
    ```  
  
4.  Объявите метод обычным способом, за исключением того, что первый параметр должен быть типом данных, который требуется расширить.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## Пример  
 В следующем примере объявляется метод расширения в модуле `StringExtensions`.  Второй модуль `Module1` импортирует `StringExtensions` и вызывает метод.  При вызове метод расширения должен быть в области.  Метод расширения `PrintAndPunctuate` расширяет класс <xref:System.String> методом, отображающим экземпляр строки, которая сопровождается строкой символов пунктуации, переданных как параметр.  
  
```vb#  
' Declarations will typically be in a separate module.  
Imports System.Runtime.CompilerServices  
  
Module StringExtensions  
    <Extension()>   
    Public Sub PrintAndPunctuate(ByVal aString As String,   
                                 ByVal punc As String)  
        Console.WriteLine(aString & punc)  
    End Sub  
  
End Module  
```  
  
```vb#  
' Import the module that holds the extension method you want to use,   
' and call it.  
  
Imports ConsoleApplication2.StringExtensions  
  
Module Module1  
  
    Sub Main()  
        Dim example = "Hello"  
        example.PrintAndPunctuate("?")  
        example.PrintAndPunctuate("!!!!")  
    End Sub  
  
End Module  
  
```  
  
 Обратите внимание, что метод определен с двумя параметрами, а вызван с только одним.  Первый параметр `aString` в определении метода привязан к `example` — экземпляру `String`, который вызывает метод.  Результат выполнения примера выглядит следующим образом:  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## См. также  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>   
 [Методы расширения](../../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)   
 [Оператор Module](../../../../visual-basic/language-reference/statements/module-statement.md)   
 [Параметры и аргументы процедуры](../../../../visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments.md)   
 [Область видимости в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)