---
title: "Практическое руководство. Изменение деревьев выражений (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 9b0cd8c2-457e-4833-9e36-31e79545f442
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b665f3bfa1228e2e8834241f010792e9d5975c96
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-modify-expression-trees-c"></a><span data-ttu-id="32a5a-102">Практическое руководство. Изменение деревьев выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="32a5a-102">How to: Modify Expression Trees (C#)</span></span>
<span data-ttu-id="32a5a-103">В этом разделе показано, как изменить дерево выражения.</span><span class="sxs-lookup"><span data-stu-id="32a5a-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="32a5a-104">Деревья выражений являются неизменяемыми, что означает невозможность их изменения напрямую.</span><span class="sxs-lookup"><span data-stu-id="32a5a-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="32a5a-105">Чтобы изменить дерево выражения, необходимо создать копию существующего дерева выражения, а затем внести необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="32a5a-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="32a5a-106">Для прохода по существующему дереву выражения и копирования каждого пройденного узла можно использовать класс <xref:System.Linq.Expressions.ExpressionVisitor>.</span><span class="sxs-lookup"><span data-stu-id="32a5a-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="32a5a-107">Изменение дерева выражения</span><span class="sxs-lookup"><span data-stu-id="32a5a-107">To modify an expression tree</span></span>  
  
1.  <span data-ttu-id="32a5a-108">Создайте новый проект **консольного приложения**.</span><span class="sxs-lookup"><span data-stu-id="32a5a-108">Create a new **Console Application** project.</span></span>  
  
2.  <span data-ttu-id="32a5a-109">Добавьте в файл директиву `using` для пространства имен `System.Linq.Expressions`.</span><span class="sxs-lookup"><span data-stu-id="32a5a-109">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3.  <span data-ttu-id="32a5a-110">Добавьте в проект класс `AndAlsoModifier`.</span><span class="sxs-lookup"><span data-stu-id="32a5a-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
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
  
     <span data-ttu-id="32a5a-111">Этот класс наследует класс <xref:System.Linq.Expressions.ExpressionVisitor> и специально предназначен для изменения выражений, которые представляют условные операции `AND`.</span><span class="sxs-lookup"><span data-stu-id="32a5a-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="32a5a-112">Он изменяет эти операции с условного `AND` на условное `OR`.</span><span class="sxs-lookup"><span data-stu-id="32a5a-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="32a5a-113">Для этого класс переопределяет метод <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> базового типа, потому что условные выражения `AND` представлены как двоичные выражения.</span><span class="sxs-lookup"><span data-stu-id="32a5a-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="32a5a-114">Если выражение, переданное в метод `VisitBinary`, представляет условную операцию `AND`, код создает новое выражение, которое содержит условный оператор `OR` вместо условного оператора `AND`.</span><span class="sxs-lookup"><span data-stu-id="32a5a-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="32a5a-115">Если выражение, передаваемое в `VisitBinary`, не представляет условную операцию `AND`, метод передает выполнение реализации базового класса.</span><span class="sxs-lookup"><span data-stu-id="32a5a-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="32a5a-116">Методы базового класса создают узлы, которые похожи на переданные деревья выражений, однако поддеревья этих деревьев заменены на деревья выражений, которые были рекурсивно созданы при обходе.</span><span class="sxs-lookup"><span data-stu-id="32a5a-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4.  <span data-ttu-id="32a5a-117">Добавьте в файл директиву `using` для пространства имен `System.Linq.Expressions`.</span><span class="sxs-lookup"><span data-stu-id="32a5a-117">Add a `using` directive to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5.  <span data-ttu-id="32a5a-118">Добавьте код в метод `Main` в файле Program.cs для создания дерева выражения и передачи его в метод, который изменит его.</span><span class="sxs-lookup"><span data-stu-id="32a5a-118">Add code to the `Main` method in the Program.cs file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
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
  
     <span data-ttu-id="32a5a-119">В приведенном ниже коде создается выражение, которое содержит условную операцию `AND`.</span><span class="sxs-lookup"><span data-stu-id="32a5a-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="32a5a-120">Затем в нем создается экземпляр класса `AndAlsoModifier`, и в метод `Modify` этого класса передается выражение.</span><span class="sxs-lookup"><span data-stu-id="32a5a-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="32a5a-121">Как исходные, так и измененные деревья выражений выводятся для отображения изменения.</span><span class="sxs-lookup"><span data-stu-id="32a5a-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6.  <span data-ttu-id="32a5a-122">Скомпилируйте и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="32a5a-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32a5a-123">См. также</span><span class="sxs-lookup"><span data-stu-id="32a5a-123">See Also</span></span>  
 <span data-ttu-id="32a5a-124">[Практическое руководство. Выполнение деревьев выражений (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span><span class="sxs-lookup"><span data-stu-id="32a5a-124">[How to: Execute Expression Trees (C#)](../../../../csharp/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span></span>  
 [<span data-ttu-id="32a5a-125">Деревья выражений (C#)</span><span class="sxs-lookup"><span data-stu-id="32a5a-125">Expression Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/expression-trees/index.md)

