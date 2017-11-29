---
title: "Как: изменение деревьев выражений (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 28a79a2dc8817a3fc6c7f3e2e01c1270d2981334
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-modify-expression-trees-visual-basic"></a>Как: изменение деревьев выражений (Visual Basic)
В этом разделе показано, как изменить дерево выражения. Деревья выражений являются неизменяемыми, что означает невозможность их изменения напрямую. Чтобы изменить дерево выражения, необходимо создать копию существующего дерева выражения, а затем внести необходимые изменения. Для прохода по существующему дереву выражения и копирования каждого пройденного узла можно использовать класс <xref:System.Linq.Expressions.ExpressionVisitor>.  
  
### <a name="to-modify-an-expression-tree"></a>Изменение дерева выражения  
  
1.  Создайте новый проект **консольного приложения**.  
  
2.  Добавить `Imports` инструкции в файл для `System.Linq.Expressions` пространства имен.  
  
3.  Добавьте в проект класс `AndAlsoModifier`.  
  
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
  
     Этот класс наследует класс <xref:System.Linq.Expressions.ExpressionVisitor> и специально предназначен для изменения выражений, которые представляют условные операции `AND`. Он изменяет эти операции с условного `AND` на условное `OR`. Для этого класс переопределяет метод <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> базового типа, потому что условные выражения `AND` представлены как двоичные выражения. Если выражение, переданное в метод `VisitBinary`, представляет условную операцию `AND`, код создает новое выражение, которое содержит условный оператор `OR` вместо условного оператора `AND`. Если выражение, передаваемое в `VisitBinary`, не представляет условную операцию `AND`, метод передает выполнение реализации базового класса. Методы базового класса создают узлы, которые похожи на переданные деревья выражений, однако поддеревья этих деревьев заменены на деревья выражений, которые были рекурсивно созданы при обходе.  
  
4.  Добавить `Imports` инструкции в файл для `System.Linq.Expressions` пространства имен.  
  
5.  Добавьте код для `Main` метод в файле Module1.vb создания дерева выражений и передать его методу, он будет изменен.  
  
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
  
     В приведенном ниже коде создается выражение, которое содержит условную операцию `AND`. Затем в нем создается экземпляр класса `AndAlsoModifier`, и в метод `Modify` этого класса передается выражение. Как исходные, так и измененные деревья выражений выводятся для отображения изменения.  
  
6.  Скомпилируйте и запустите приложение.  
  
## <a name="see-also"></a>См. также  
 [Как: выполнение деревьев выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)  
 [Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))
