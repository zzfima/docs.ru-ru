---
title: "Практическое руководство: выполнение деревьев выражений (Visual Basic) | Документы Microsoft"
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
ms.assetid: 9dfb5ab3-f48f-417e-975f-f8f6f1cdc18d
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e12c45b417310f097d597561b2652ee793a4b2c0
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-execute-expression-trees-visual-basic"></a>Практическое руководство: выполнение деревьев выражений (Visual Basic)
В этом разделе показано, как выполнить дерево выражения. Выполнения дерева выражения может возвращаться значение или просто выполняться действие, например вызов метода.  
  
 Могут быть выполнены только деревьев выражений, представляющих лямбда-выражения. Деревья выражений, представляющие лямбда-выражения имеют тип <xref:System.Linq.Expressions.LambdaExpression>или <xref:System.Linq.Expressions.Expression%601>.</xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression> Для выполнения таких деревьев выражений, вызовите <xref:System.Linq.Expressions.LambdaExpression.Compile%2A>метод, чтобы создать исполняемый делегат, а затем вызвать делегата.</xref:System.Linq.Expressions.LambdaExpression.Compile%2A>  
  
> [!NOTE]
>  Если тип делегата неизвестен, то есть лямбда-выражение имеет тип <xref:System.Linq.Expressions.LambdaExpression>и не <xref:System.Linq.Expressions.Expression%601>, необходимо вызвать метод <xref:System.Delegate.DynamicInvoke%2A>метод делегата вместо вызова этого метода напрямую.</xref:System.Delegate.DynamicInvoke%2A> </xref:System.Linq.Expressions.Expression%601> </xref:System.Linq.Expressions.LambdaExpression>  
  
 Если дерево выражения не представляет лямбда-выражение, можно создать новый лямбда-выражение, имеет исходное дерево выражения, что его тело, путем вызова <xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29>метод.</xref:System.Linq.Expressions.Expression.Lambda%60%601%28System.Linq.Expressions.Expression%2CSystem.Collections.Generic.IEnumerable%7BSystem.Linq.Expressions.ParameterExpression%7D%29> Затем можно выполнить лямбда-выражение, как описано ранее в этом разделе.  
  
## <a name="example"></a>Пример  
 В следующем примере кода показано, как выполнить дерево выражения, представляющий возведение числа в степень, создавая лямбда-выражения и его выполнением. Результат, представляющий число, возведенное в степень, отображается.  
  
```vb  
' The expression tree to execute.  
Dim be As BinaryExpression = Expression.Power(Expression.Constant(2.0R), Expression.Constant(3.0R))  
  
' Create a lambda expression.  
Dim le As Expression(Of Func(Of Double)) = Expression.Lambda(Of Func(Of Double))(be)  
  
' Compile the lambda expression.  
Dim compiledExpression As Func(Of Double) = le.Compile()  
  
' Execute the lambda expression.  
Dim result As Double = compiledExpression()  
  
' Display the result.  
MsgBox(result)  
  
' This code produces the following output:  
' 8  
```  
  
## <a name="compiling-the-code"></a>Компиляция кода  
  
-   Добавьте ссылку на библиотеку System.Core.dll, если нет ссылок.  
  
-   Включите пространство имен System.Linq.Expressions.  
  
## <a name="see-also"></a>См. также  
 [Деревья выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [Практическое руководство: изменение деревьев выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
