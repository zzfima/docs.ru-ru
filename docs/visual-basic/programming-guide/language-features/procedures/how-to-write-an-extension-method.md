---
title: Практическое руководство. Написание метода расширения (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- extending data types [Visual Basic]
- writing extension methods [Visual Basic]
- extension methods [Visual Basic]
ms.assetid: fb2739cc-958d-4ef4-a38b-214a74c93413
ms.openlocfilehash: d6f8b85945bd400d1f4b54a50260d72c750add8b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2019
ms.locfileid: "58819122"
---
# <a name="how-to-write-an-extension-method-visual-basic"></a>Практическое руководство. Написание метода расширения (Visual Basic)
Методы расширения позволяют добавлять методы к существующему классу. Метод расширения может вызываться, как если бы это был экземпляр этого класса.  
  
### <a name="to-define-an-extension-method"></a>Для определения метода расширения  
  
1.  Откройте новые или существующие приложения Visual Basic в Visual Studio.  
  
2.  В верхней части файла, в котором вы хотите определить метод расширения включите следующую инструкцию import:  
  
    ```  
    Imports System.Runtime.CompilerServices  
    ```  
  
3.  В модуле нового или существующего приложения определите метод атрибутом расширения:  
  
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
 В следующем примере объявляется метод расширения в модуле `StringExtensions`. Второй модуль `Module1`, импортирует `StringExtensions` и вызывает метод. Метод расширения должен находиться в области, при вызове. Метод расширения `PrintAndPunctuate` расширяет <xref:System.String> класс с методом, который отображает экземпляр строки и строки символов пунктуации, отправляемый в качестве параметра.  
  
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
  
 Обратите внимание на то, что метод определен с двумя параметрами и только с одним именем. Первый параметр, `aString`, в методе связано `example`, экземпляр `String` , вызывает метод. Выходные данные примера могут быть следующими:  
  
 `Hello?`  
  
 `Hello!!!!`  
  
## <a name="see-also"></a>См. также

- <xref:System.Runtime.CompilerServices.ExtensionAttribute>
- [Методы расширения](./extension-methods.md)
- [Оператор Module](../../../../visual-basic/language-reference/statements/module-statement.md)
- [Параметры и аргументы процедуры](./procedure-parameters-and-arguments.md)
- [Область, в Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)
