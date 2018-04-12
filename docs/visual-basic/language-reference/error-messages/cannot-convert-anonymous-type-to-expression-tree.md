---
title: Не удается преобразовать анонимный тип в дерево выражений, поскольку он содержит поле, которое было использовано в инициализации другого поля
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
caps.latest.revision: 9
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c2cf8a40060359393807cfb648c46fef9ed853af
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>Не удается преобразовать анонимный тип в дерево выражений, поскольку он содержит поле, которое было использовано в инициализации другого поля
Компилятор не принимает преобразование анонимных в дерево выражения, если одно свойство анонимного типа используется для инициализации другого свойства анонимного типа. Например, в следующем коде `Prop1` объявлена в списке инициализации, а затем используется в качестве начального значения для `Prop2`.  
  
```vb  
Module M2  
  
    Sub ExpressionExample(Of T)(ByVal x As Expressions.Expression(Of Func(Of T)))  
    End Sub  
  
    Sub Main()  
        ' The following line causes the error.  
        ' ExpressionExample(Function() New With {.Prop1 = 2, .Prop2 = .Prop1})  
  
    End Sub  
End Module  
```  
  
 **Идентификатор ошибки:** BC36548  
  
## <a name="to-correct-this-error"></a>Исправление ошибки  
  
-   Присвойте начальное значение для `Prop1` локальной переменной. Назначьте этой переменной как `Prop1` и `Prop2`, как показано в следующем коде.  
  
    ```  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>См. также  
 [Анонимные типы](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Деревья выражений](http://msdn.microsoft.com/library/fb1d3ed8-d5b0-4211-a71f-dd271529294b)  
 [Практическое руководство. Использование деревьев выражений для построения динамических запросов](http://msdn.microsoft.com/library/1e37e0cc-eef3-48bb-8b69-3adabf322735)
