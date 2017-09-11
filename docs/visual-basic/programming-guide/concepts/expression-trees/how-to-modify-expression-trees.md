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
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 2f0d383cbac639212519177fb1825875682f6233
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-modify-expression-trees-visual-basic"></a><span data-ttu-id="04093-102">Практическое руководство: изменение деревьев выражений (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04093-102">How to: Modify Expression Trees (Visual Basic)</span></span>
<span data-ttu-id="04093-103">В этом разделе показано, как изменить дерево выражений.</span><span class="sxs-lookup"><span data-stu-id="04093-103">This topic shows you how to modify an expression tree.</span></span> <span data-ttu-id="04093-104">Деревья выражений являются неизменяемыми, что означает, что их нельзя изменить непосредственно.</span><span class="sxs-lookup"><span data-stu-id="04093-104">Expression trees are immutable, which means that they cannot be modified directly.</span></span> <span data-ttu-id="04093-105">Чтобы изменить дерево выражения, необходимо создать копию существующего дерева выражения и при создании копии, внесите требуемые изменения.</span><span class="sxs-lookup"><span data-stu-id="04093-105">To change an expression tree, you must create a copy of an existing expression tree and when you create the copy, make the required changes.</span></span> <span data-ttu-id="04093-106">Можно использовать <xref:System.Linq.Expressions.ExpressionVisitor>класс для обхода существующего дерева выражения и копирования каждого пройденного узла.</xref:System.Linq.Expressions.ExpressionVisitor></span><span class="sxs-lookup"><span data-stu-id="04093-106">You can use the <xref:System.Linq.Expressions.ExpressionVisitor> class to traverse an existing expression tree and to copy each node that it visits.</span></span>  
  
### <a name="to-modify-an-expression-tree"></a><span data-ttu-id="04093-107">Чтобы изменить дерево выражения</span><span class="sxs-lookup"><span data-stu-id="04093-107">To modify an expression tree</span></span>  
  
1.  <span data-ttu-id="04093-108">Создайте новый **консольное приложение** проекта.</span><span class="sxs-lookup"><span data-stu-id="04093-108">Create a new **Console Application** project.</span></span>  
  
2.  <span data-ttu-id="04093-109">Добавить `Imports` файл для `System.Linq.Expressions` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="04093-109">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
3.  <span data-ttu-id="04093-110">Добавление `AndAlsoModifier` класс в проект.</span><span class="sxs-lookup"><span data-stu-id="04093-110">Add the `AndAlsoModifier` class to your project.</span></span>  
  
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
  
     <span data-ttu-id="04093-111">Этот класс наследует <xref:System.Linq.Expressions.ExpressionVisitor>класса и специально предназначен для изменения выражений, которые представляют условные `AND` операций.</xref:System.Linq.Expressions.ExpressionVisitor></span><span class="sxs-lookup"><span data-stu-id="04093-111">This class inherits the <xref:System.Linq.Expressions.ExpressionVisitor> class and is specialized to modify expressions that represent conditional `AND` operations.</span></span> <span data-ttu-id="04093-112">Он изменяет эти операции с условного `AND` на условное `OR`.</span><span class="sxs-lookup"><span data-stu-id="04093-112">It changes these operations from a conditional `AND` to a conditional `OR`.</span></span> <span data-ttu-id="04093-113">Для этого класс переопределяет <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A>метод базового типа, поскольку условного `AND` выражения, представлены как двоичные выражения.</xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A></span><span class="sxs-lookup"><span data-stu-id="04093-113">To do this, the class overrides the <xref:System.Linq.Expressions.ExpressionVisitor.VisitBinary%2A> method of the base type, because conditional `AND` expressions are represented as binary expressions.</span></span> <span data-ttu-id="04093-114">В `VisitBinary` метода, если выражение, которое передается в него представляет условную `AND` операции, код создает новое выражение, которое содержит условный `OR` оператор вместо условного `AND` оператор.</span><span class="sxs-lookup"><span data-stu-id="04093-114">In the `VisitBinary` method, if the expression that is passed to it represents a conditional `AND` operation, the code constructs a new expression that contains the conditional `OR` operator instead of the conditional `AND` operator.</span></span> <span data-ttu-id="04093-115">Если выражение, которое передается в `VisitBinary` представляет условную `AND` операции, метод передает выполнение реализации базового класса.</span><span class="sxs-lookup"><span data-stu-id="04093-115">If the expression that is passed to `VisitBinary` does not represent a conditional `AND` operation, the method defers to the base class implementation.</span></span> <span data-ttu-id="04093-116">Методы базового класса создают узлы, которые похожи на деревья выражений, которые передаются в, но узлы имеют поддеревья этих деревьев заменены деревьев выражений, которые создаются рекурсивно посетителем.</span><span class="sxs-lookup"><span data-stu-id="04093-116">The base class methods construct nodes that are like the expression trees that are passed in, but the nodes have their sub trees replaced with the expression trees that are produced recursively by the visitor.</span></span>  
  
4.  <span data-ttu-id="04093-117">Добавить `Imports` файл для `System.Linq.Expressions` пространства имен.</span><span class="sxs-lookup"><span data-stu-id="04093-117">Add an `Imports` statement to the file for the `System.Linq.Expressions` namespace.</span></span>  
  
5.  <span data-ttu-id="04093-118">Добавьте код для `Main` метод в файл Module1.vb для создания дерева выражений и передайте его методу, будет изменен.</span><span class="sxs-lookup"><span data-stu-id="04093-118">Add code to the `Main` method in the Module1.vb file to create an expression tree and pass it to the method that will modify it.</span></span>  
  
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
  
     <span data-ttu-id="04093-119">Код создает выражение, которое содержит условную `AND` операции.</span><span class="sxs-lookup"><span data-stu-id="04093-119">The code creates an expression that contains a conditional `AND` operation.</span></span> <span data-ttu-id="04093-120">Затем он создает экземпляр `AndAlsoModifier` класса и передает выражение `Modify` метод этого класса.</span><span class="sxs-lookup"><span data-stu-id="04093-120">It then creates an instance of the `AndAlsoModifier` class and passes the expression to the `Modify` method of this class.</span></span> <span data-ttu-id="04093-121">Как исходное, так и измененное дерево выражения выводятся для отображения изменений.</span><span class="sxs-lookup"><span data-stu-id="04093-121">Both the original and the modified expression trees are outputted to show the change.</span></span>  
  
6.  <span data-ttu-id="04093-122">Скомпилируйте и запустите приложение.</span><span class="sxs-lookup"><span data-stu-id="04093-122">Compile and run the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04093-123">См. также</span><span class="sxs-lookup"><span data-stu-id="04093-123">See Also</span></span>  
 <span data-ttu-id="04093-124">[Практическое руководство: выполнение деревьев выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span><span class="sxs-lookup"><span data-stu-id="04093-124">[How to: Execute Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md) </span></span>  
<span data-ttu-id="04093-125"> [Деревья выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span><span class="sxs-lookup"><span data-stu-id="04093-125"> [Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)</span></span>
