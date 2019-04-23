---
title: Как выполнить Изменение деревьев выражений (C#)
ms.date: 07/20/2015
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
ms.openlocfilehash: 26c00f3acc7ab44e74a81e346ab1c017d95d53b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59308644"
---
# <a name="how-to-modify-expression-trees-c"></a>Как выполнить Изменение деревьев выражений (C#)
В этом разделе показано, как изменить дерево выражения. Деревья выражений являются неизменяемыми, что означает невозможность их изменения напрямую. Чтобы изменить дерево выражения, необходимо создать копию существующего дерева выражения, а затем внести необходимые изменения. Для прохода по существующему дереву выражения и копирования каждого пройденного узла можно использовать класс <xref:System.Linq.Expressions.ExpressionVisitor>.  
  
### <a name="to-modify-an-expression-tree"></a>Изменение дерева выражения  
  
1. Создайте новый проект **консольного приложения**.  
  
2. Добавьте в файл директиву `using` для пространства имен `System.Linq.Expressions`.  
  
3. Добавьте в проект класс `AndAlsoModifier`.  
  
    ```csharp  
    public class AndAlsoModifier : ExpressionVisitor  
    {  
        public Expression Modify(Expression expression)  
        {  
            return Visit(expression);  
        }  
  
        protected override Expression VisitBinary(BinaryExpression b)  
        {  
            if (b.NodeType == ExpressionType.AndAlso)  
            {  
                Expression left = this.Visit(b.Left);  
                Expression right = this.Visit(b.Right);  
  
                // Make this binary expression an OrElse operation instead of an AndAlso operation.  
                return Expression.MakeBinary(ExpressionType.OrElse, left, right, b.IsLiftedToNull, b.Method);  
            }  
  
            return base.VisitBinary(b);  
        }  
    }  
    ```  
  
     Этот класс наследует класс <xref:System.Linq.Expressions.ExpressionVisitor> и специально предназначен для изменения выражений, которые представляют условные операции `AND`. Он изменяет эти операции с условного `AND` на условное `OR`. Для этого класс переопределяет метод <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> базового типа, потому что условные выражения `AND` представлены как двоичные выражения. Если выражение, переданное в метод `VisitBinary`, представляет условную операцию `AND`, код создает новое выражение, которое содержит условный оператор `OR` вместо условного оператора `AND`. Если выражение, передаваемое в `VisitBinary`, не представляет условную операцию `AND`, метод передает выполнение реализации базового класса. Методы базового класса создают узлы, которые похожи на переданные деревья выражений, однако поддеревья этих деревьев заменены на деревья выражений, которые были рекурсивно созданы при обходе.  
  
4. Добавьте в файл директиву `using` для пространства имен `System.Linq.Expressions`.  
  
5. Добавьте код в метод `Main` в файле Program.cs для создания дерева выражения и передачи его в метод, который изменит его.  
  
    ```csharp  
    Expression<Func<string, bool>> expr = name => name.Length > 10 && name.StartsWith("G");  
    Console.WriteLine(expr);  
  
    AndAlsoModifier treeModifier = new AndAlsoModifier();  
    Expression modifiedExpr = treeModifier.Modify((Expression) expr);  
  
    Console.WriteLine(modifiedExpr);  
  
    /*  This code produces the following output:  
  
        name => ((name.Length > 10) && name.StartsWith("G"))  
        name => ((name.Length > 10) || name.StartsWith("G"))  
    */  
    ```  
  
     В приведенном ниже коде создается выражение, которое содержит условную операцию `AND`. Затем в нем создается экземпляр класса `AndAlsoModifier`, и в метод `Modify` этого класса передается выражение. Как исходные, так и измененные деревья выражений выводятся для отображения изменения.  
  
6. Скомпилируйте и запустите приложение.  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Выполнение деревьев выражений (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
- [Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (C#))
