---
title: "Практическое руководство: изменение деревьев выражений (Visual Basic) | Документы Microsoft"
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
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
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
ms.openlocfilehash: fb4e818eed7d6547e091c914d40b3ce87af59512
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-modify-expression-trees-visual-basic"></a>Практическое руководство: изменение деревьев выражений (Visual Basic)
В этом разделе показано, как изменить дерево выражений. Деревья выражений являются неизменяемыми, что означает, что их нельзя изменить непосредственно. Чтобы изменить дерево выражения, необходимо создать копию существующего дерева выражения и при создании копии, внесите требуемые изменения. Можно использовать <xref:System.Linq.Expressions.ExpressionVisitor>класс для обхода существующего дерева выражения и копирования каждого пройденного узла.</xref:System.Linq.Expressions.ExpressionVisitor>  
  
### <a name="to-modify-an-expression-tree"></a>Чтобы изменить дерево выражения  
  
1.  Создайте новый **консольное приложение** проекта.  
  
2.  Добавить `Imports` файл для `System.Linq.Expressions` пространства имен.  
  
3.  Добавление `AndAlsoModifier` класс в проект.  
  
    ```vb  
    Public Class AndAlsoModifier  
        Inherits ExpressionVisitor  
  
        Public Function Modify(ByVal expr As Expression) As Expression  
            Return Visit(expr)  
        End Function  
  
        Protected Overrides Function VisitBinary(ByVal b As BinaryExpression) As Expression  
            If b.NodeType = ExpressionType.AndAlso Then  
                Dim left = Me.Visit(b.Left)  
                Dim right = Me.Visit(b.Right)  
  
                ' Make this binary expression an OrElse operation instead   
                ' of an AndAlso operation.  
                Return Expression.MakeBinary(ExpressionType.OrElse, left, right, _  
                                             b.IsLiftedToNull, b.Method)  
            End If  
  
            Return MyBase.VisitBinary(b)  
        End Function  
    End Class  
    ```  
  
     Этот класс наследует <xref:System.Linq.Expressions.ExpressionVisitor>класса и специально предназначен для изменения выражений, которые представляют условные `AND` операций.</xref:System.Linq.Expressions.ExpressionVisitor> Он изменяет эти операции с условного `AND` на условное `OR`. Для этого класс переопределяет <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>метод базового типа, поскольку условного `AND` выражения, представлены как двоичные выражения.</xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> В `VisitBinary` метода, если выражение, которое передается в него представляет условную `AND` операции, код создает новое выражение, которое содержит условный `OR` оператор вместо условного `AND` оператор. Если выражение, которое передается в `VisitBinary` представляет условную `AND` операции, метод передает выполнение реализации базового класса. Методы базового класса создают узлы, которые похожи на деревья выражений, которые передаются в, но узлы имеют поддеревья этих деревьев заменены деревьев выражений, которые создаются рекурсивно посетителем.  
  
4.  Добавить `Imports` файл для `System.Linq.Expressions` пространства имен.  
  
5.  Добавьте код для `Main` метод в файл Module1.vb для создания дерева выражений и передайте его методу, будет изменен.  
  
    ```vb  
    Dim expr As Expression(Of Func(Of String, Boolean)) = _  
        Function(name) name.Length > 10 AndAlso name.StartsWith("G")  
  
    Console.WriteLine(expr)  
  
    Dim modifier As New AndAlsoModifier()  
    Dim modifiedExpr = modifier.Modify(CType(expr, Expression))  
  
    Console.WriteLine(modifiedExpr)  
  
    ' This code produces the following output:  
    ' name => ((name.Length > 10) && name.StartsWith("G"))  
    ' name => ((name.Length > 10) || name.StartsWith("G"))  
    ```  
  
     Код создает выражение, которое содержит условную `AND` операции. Затем он создает экземпляр `AndAlsoModifier` класса и передает выражение `Modify` метод этого класса. Как исходное, так и измененное дерево выражения выводятся для отображения изменений.  
  
6.  Скомпилируйте и запустите приложение.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство: выполнение деревьев выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)   
 [Деревья выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)
