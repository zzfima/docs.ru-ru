---
title: "Практическое руководство. Написание метода расширения (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 65cdabf59886e7457a327ee9cde968a6a73f2280
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Практическое руководство. Написание метода расширения (Visual Basic)
Методы расширения позволяют добавлять методы в существующий класс. Метод расширения может вызываться, как если бы он был экземпляром этого класса.  
  
### <a name="to-define-an-extension-method"></a>Для определения метода расширения  
  
1.  Откройте новый или существующий приложения Visual Basic в Visual Studio.  
  
2.  В верхней части файла, в котором необходимо определить метод расширения включают следующие инструкции import:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  Внутри модуля нового или существующего приложения определите метод с атрибутом расширения:  
  
    ```  
    <Extension()>  
    ```  
  
4.  Объявите метод обычным способом, за исключением того, что тип первого параметра должен быть тип данных, который требуется расширить.  
  
    ```  
    <Extension()>   
    Public Sub subName (ByVal para1 As ExtendedType, <other parameters>)  
         ' < Body of the method >  
    End Sub  
    ```  
  
## <a name="example"></a>Пример  
 В следующем примере объявляется метод расширения в модуль `StringExtensions`. Второй модуль `Module1`, импортирует `StringExtensions` и вызывает метод. Метод расширения должен быть в области видимости при вызове. Метод расширения `PrintAndPunctuate` расширяет <xref:System.String> класс с методом, который отображает экземпляр строки и строки символов пунктуации, отправляемый в качестве параметра.  
  
```vb  
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
  
```vb  
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
  
 Обратите внимание, что метод определен с двумя параметрами и только с одним именем. Первый параметр `aString`, в методе связано `example`, экземпляр `String` , вызывает метод. Выходные данные примера выглядит следующим образом:  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>См. также  
 <xref:System.Runtime.CompilerServices.ExtensionAttribute>  
 [Методы расширения](./extension-methods.md)  
 [Оператор Module](../../../../visual-basic/language-reference/statements/module-statement.md)  
 [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)  
 [Область в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
