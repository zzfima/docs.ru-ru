---
title: Не удается преобразовать анонимный тип в дерево выражений, поскольку он содержит поле, которое было использовано в инициализации другого поля
ms.date: 07/20/2015
f1_keywords:
- bc36548
- vbc36548
helpviewer_keywords:
- BC36548
ms.assetid: 27de068f-080e-4160-86bf-1ec23fd1925a
ms.openlocfilehash: ba14c0cd8781b8771ac8b746e3efec29a457294a
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701178"
---
# <a name="cannot-convert-anonymous-type-to-expression-tree-because-it-contains-a-field-that-is-used-in-the-initialization-of-another-field"></a>Не удается преобразовать анонимный тип в дерево выражений, поскольку он содержит поле, которое было использовано в инициализации другого поля
Компилятор не принимает преобразование анонимного объекта в дерево выражения, если одно свойство анонимного типа используется для инициализации другого свойства анонимного типа. Например, в следующем коде `Prop1` объявляется в списке инициализации, а затем используется в качестве начального значения для `Prop2`.  
  
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
  
- Присвойте начальное значение `Prop1` локальной переменной. Присвойте этой переменной значения `Prop1` и `Prop2`, как показано в следующем коде.  
  
    ```vb  
    Sub Main()  
  
        Dim temp = 2  
        ExpressionExample(Function() New With {.Prop1 = temp, .Prop2 = temp})  
  
    End Sub  
    ```  
  
## <a name="see-also"></a>См. также

- [Анонимные типы (Visual Basic)](../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Expression Trees (Visual Basic)](../../programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))
- [Практическое руководство. Использование деревьев выражений для построения динамических запросов (Visual Basic) ](../../programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md)
