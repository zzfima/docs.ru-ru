---
title: Практическое руководство. Изменение деревьев выражений (Visual Basic)
ms.date: 07/20/2015
ms.assetid: d1309fff-28bd-4d8e-a2cf-75725999e8f2
ms.openlocfilehash: ac196b56f178659765437a97a25f46c04f8040fa
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2019
ms.locfileid: "71054204"
---
# <a name="how-to-modify-expression-trees-visual-basic"></a>Практическое руководство. Изменение деревьев выражений (Visual Basic)

В этом разделе показано, как изменить дерево выражения. Деревья выражений являются неизменяемыми, что означает невозможность их изменения напрямую. Чтобы изменить дерево выражения, необходимо создать копию существующего дерева выражения, а затем внести необходимые изменения. Для прохода по существующему дереву выражения и копирования каждого пройденного узла можно использовать класс <xref:System.Linq.Expressions.ExpressionVisitor>.

## <a name="to-modify-an-expression-tree"></a>Изменение дерева выражения

1. Создайте новый проект **консольного приложения**.

2. Добавьте в файл `System.Linq.Expressions`инструкцию для пространства имен. `Imports`

3. Добавьте в проект класс `AndAlsoModifier`.

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

4. Добавьте в файл `System.Linq.Expressions`инструкцию для пространства имен. `Imports`

5. Добавьте код в `Main` метод в файле Module1. vb, чтобы создать дерево выражения и передать его в метод, который будет изменять его.

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

6. Скомпилируйте и запустите приложение.

## <a name="see-also"></a>См. также

- [Практическое руководство. Выполнение деревьев выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
- [Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))
