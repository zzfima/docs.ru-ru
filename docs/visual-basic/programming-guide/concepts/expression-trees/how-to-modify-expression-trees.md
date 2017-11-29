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
# <a name="how-to-modify-expression-trees-visual-basic"></a><span data-ttu-id="d96e4-102">Как: изменение деревьев выражений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d96e4-102">How to: Modify Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="d96e4-103">В этом разделе показано, как изменить дерево выражения.</span><span class="sxs-lookup"><span data-stu-id="d96e4-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="d96e4-104">Деревья выражений являются неизменяемыми, что означает невозможность их изменения напрямую.</span><span class="sxs-lookup"><span data-stu-id="d96e4-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="d96e4-105">Чтобы изменить дерево выражения, необходимо создать копию существующего дерева выражения, а затем внести необходимые изменения.</span><span class="sxs-lookup"><span data-stu-id="d96e4-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="d96e4-106">Для прохода по существующему дереву выражения и копирования каждого пройденного узла можно использовать класс <xref:System.Linq.Expressions.ExpressionVisitor>.</span><span class="sxs-lookup"><span data-stu-id="d96e4-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="d96e4-107">Изменение дерева выражения</span><span class="sxs-lookup"><span data-stu-id="d96e4-107">To modify an expression tree</span></span>  
  
1.  <span data-ttu-id="d96e4-108">Создайте новый проект **консольного приложения**.</span><span class="sxs-lookup"><span data-stu-id="d96e4-108">Create a new **Console Application** project.</span></span>  
  
2.  <span data-ttu-id="d96e4-109">Добавить `Imports` инструкции в файл для `System.Linq.Expressions` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d96e4-109">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3.  <span data-ttu-id="d96e4-110">Добавьте в проект класс `AndAlsoModifier`.</span><span class="sxs-lookup"><span data-stu-id="d96e4-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
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
  
     <span data-ttu-id="d96e4-111">Этот класс наследует класс <xref:System.Linq.Expressions.ExpressionVisitor> и специально предназначен для изменения выражений, которые представляют условные операции `AND`.</span><span class="sxs-lookup"><span data-stu-id="d96e4-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="d96e4-112">Он изменяет эти операции с условного `AND` на условное `OR`.</span><span class="sxs-lookup"><span data-stu-id="d96e4-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="d96e4-113">Для этого класс переопределяет метод <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> базового типа, потому что условные выражения `AND` представлены как двоичные выражения.</span><span class="sxs-lookup"><span data-stu-id="d96e4-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="d96e4-114">Если выражение, переданное в метод `VisitBinary`, представляет условную операцию `AND`, код создает новое выражение, которое содержит условный оператор `OR` вместо условного оператора `AND`.</span><span class="sxs-lookup"><span data-stu-id="d96e4-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="d96e4-115">Если выражение, передаваемое в `VisitBinary`, не представляет условную операцию `AND`, метод передает выполнение реализации базового класса.</span><span class="sxs-lookup"><span data-stu-id="d96e4-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="d96e4-116">Методы базового класса создают узлы, которые похожи на переданные деревья выражений, однако поддеревья этих деревьев заменены на деревья выражений, которые были рекурсивно созданы при обходе.</span><span class="sxs-lookup"><span data-stu-id="d96e4-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4.  <span data-ttu-id="d96e4-117">Добавить `Imports` инструкции в файл для `System.Linq.Expressions` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="d96e4-117">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5.  <span data-ttu-id="d96e4-118">Добавьте код для `Main` метод в файле Module1.vb создания дерева выражений и передать его методу, он будет изменен.</span><span class="sxs-lookup"><span data-stu-id="d96e4-118">Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
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
  
     <span data-ttu-id="d96e4-119">В приведенном ниже коде создается выражение, которое содержит условную операцию `AND`.</span><span class="sxs-lookup"><span data-stu-id="d96e4-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="d96e4-120">Затем в нем создается экземпляр класса `AndAlsoModifier`, и в метод `Modify` этого класса передается выражение.</span><span class="sxs-lookup"><span data-stu-id="d96e4-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="d96e4-121">Как исходные, так и измененные деревья выражений выводятся для отображения изменения.</span><span class="sxs-lookup"><span data-stu-id="d96e4-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6.  <span data-ttu-id="d96e4-122">Скомпилируйте и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="d96e4-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d96e4-123">См. также</span><span class="sxs-lookup"><span data-stu-id="d96e4-123">See Also</span></span>  
 [<span data-ttu-id="d96e4-124">Как: выполнение деревьев выражений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d96e4-124">How to: Execute Expression Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)  
 <span data-ttu-id="d96e4-125">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))</span><span class="sxs-lookup"><span data-stu-id="d96e4-125">[Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>
