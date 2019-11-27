---
title: Expression Trees
ms.date: 07/20/2015
ms.assetid: 8bbbb02d-7ffc-476b-8c25-118d82bf5d46
ms.openlocfilehash: 4ca3b56f48368e465560fc5edd60c0df8dd4e1c0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344706"
---
# <a name="expression-trees-visual-basic"></a>Деревья выражений (Visual Basic)
Деревья выражений представляют код в виде древовидной структуры, где каждый узел является выражением, например, вызовом метода или двоичной операцией, такой как `x < y`.  
  
 Вы можете компилировать и выполнять код, представленный деревьями выражений. Это позволяет динамически изменять выполняемый код, выполнять запросы LINQ в различных базах данных и создавать динамические запросы. Дополнительные сведения о деревьях выражений в LINQ см. в разделе [Практическое руководство. Использование деревьев выражений для создания динамических запросов (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-use-expression-trees-to-build-dynamic-queries.md).  
  
 Кроме того, деревья выражений используются в среде выполнения динамического языка (DLR) для обеспечения взаимодействия между динамическими языками и платформой .NET Framework, а также и предоставления разработчикам компиляторов возможности выдавать деревья выражений вместо промежуточного языка Microsoft (MSIL). Дополнительные сведения о DLR см. в разделе [Общие сведения о среде DLR](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md).  
  
 Вы можете использовать компилятор C# или Visual Basic для создания дерева выражений на основе анонимного лямбда-выражения или создания деревьев выражений вручную с помощью пространства имен <xref:System.Linq.Expressions>.  
  
## <a name="creating-expression-trees-from-lambda-expressions"></a>Создание деревьев выражений на основе лямбда-выражений  
 Когда лямбда-выражение назначается переменной с типом <xref:System.Linq.Expressions.Expression%601>, компилятор выдает код для создания дерева выражений, представляющего лямбда-выражение.  
  
 Компилятор Visual Basic может создавать деревья выражений только на основе лямбда-выражений (или однострочных лямбда-функций). Они не могут анализировать лямбды операторов (или многострочные лямбды). Дополнительные сведения о лямбда-выражениях в Visual Basic см. в разделе [Лямбда-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 В следующем примере кода демонстрируется способ применения компилятора Visual Basic для создания дерева выражений, представляющего лямбда-выражение `Function(num) num < 5`.  
  
```vb  
Dim lambda As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
```  
  
## <a name="creating-expression-trees-by-using-the-api"></a>Создание деревьев выражений с помощью API-интерфейса  
 Для создания деревьев выражений с помощью API-интерфейса используйте класс <xref:System.Linq.Expressions.Expression>. Этот класс содержит статические методы фабрики, позволяющие создать узлы дерева выражения конкретного типа, например, <xref:System.Linq.Expressions.ParameterExpression>, который представляет переменную или параметр, или <xref:System.Linq.Expressions.MethodCallExpression>, который представляет вызов метода. <xref:System.Linq.Expressions.ParameterExpression>, <xref:System.Linq.Expressions.MethodCallExpression> и другие зависящие от выражения типы также определяются в пространстве имен <xref:System.Linq.Expressions>. Эти типы являются производными от абстрактного типа <xref:System.Linq.Expressions.Expression>.  
  
 В следующем примере кода демонстрируется способ создания дерева выражений, представляющего лямбда-выражение `Function(num) num < 5`, с помощью API.  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Manually build the expression tree for the lambda expression num => num < 5.  
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")  
Dim five As ConstantExpression = Expression.Constant(5, GetType(Integer))  
Dim numLessThanFive As BinaryExpression = Expression.LessThan(numParam, five)  
Dim lambda1 As Expression(Of Func(Of Integer, Boolean)) =  
  Expression.Lambda(Of Func(Of Integer, Boolean))(  
        numLessThanFive,  
        New ParameterExpression() {numParam})  
```  
  
 На платформе .NET Framework 4 или более поздней версии API деревьев выражений также поддерживает присваивание и выражения потока управления, такие как циклы, условные блоки и блоки `try-catch`. С помощью API можно создавать деревья выражений более сложные, чем деревья, создаваемые компилятором Visual Basic из лямбда-выражений. В следующем примере показан способ создания дерева выражений, которое вычисляет факториал числа.  
  
```vb  
' Creating a parameter expression.  
Dim value As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "value")  
  
' Creating an expression to hold a local variable.   
Dim result As ParameterExpression =  
    Expression.Parameter(GetType(Integer), "result")  
  
' Creating a label to jump to from a loop.  
Dim label As LabelTarget = Expression.Label(GetType(Integer))  
  
' Creating a method body.  
Dim block As BlockExpression = Expression.Block(  
    New ParameterExpression() {result},  
    Expression.Assign(result, Expression.Constant(1)),  
    Expression.Loop(  
        Expression.IfThenElse(  
            Expression.GreaterThan(value, Expression.Constant(1)),  
            Expression.MultiplyAssign(result,  
                Expression.PostDecrementAssign(value)),  
            Expression.Break(label, result)  
        ),  
        label  
    )  
)  
  
' Compile an expression tree and return a delegate.  
Dim factorial As Integer =  
    Expression.Lambda(Of Func(Of Integer, Integer))(block, value).Compile()(5)  
  
Console.WriteLine(factorial)  
' Prints 120.  
```

Дополнительные сведения см. в записи блога [Generating Dynamic Methods with Expression Trees in Visual Studio 2010](https://devblogs.microsoft.com/csharpfaq/generating-dynamic-methods-with-expression-trees-in-visual-studio-2010/) (Создание динамических методов с использованием деревьев выражений в Visual Studio 2010), которая также применима к более поздним версиям Visual Studio.
  
## <a name="parsing-expression-trees"></a>Синтаксический анализ деревьев выражений  
 В следующем примере кода показано, как дерево выражений, представляющее лямбда-выражение `Function(num) num < 5`, может быть разложено на части.  
  
```vb  
' Import the following namespace to your project: System.Linq.Expressions  
  
' Create an expression tree.  
Dim exprTree As Expression(Of Func(Of Integer, Boolean)) = Function(num) num < 5  
  
' Decompose the expression tree.  
Dim param As ParameterExpression = exprTree.Parameters(0)  
Dim operation As BinaryExpression = exprTree.Body  
Dim left As ParameterExpression = operation.Left  
Dim right As ConstantExpression = operation.Right  
  
Console.WriteLine(String.Format("Decomposed expression: {0} => {1} {2} {3}",  
                  param.Name, left.Name, operation.NodeType, right.Value))  
  
' This code produces the following output:  
'  
' Decomposed expression: num => num LessThan 5  
```  
  
## <a name="immutability-of-expression-trees"></a>Неизменность деревьев выражений  
 Деревья выражений должны быть неизменными. Это означает, что если требуется изменить дерево выражений, следует создать новое дерево выражений путем копирования существующего и заменить узлы в нем. Для прохода по существующему дереву выражений можно использовать другое дерево выражений (посетитель). Дополнительные сведения см. в разделе [Практическое руководство. Изменение деревьев выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md).  
  
## <a name="compiling-expression-trees"></a>Компиляция деревьев выражений  
 Тип <xref:System.Linq.Expressions.Expression%601> предоставляет метод  <xref:System.Linq.Expressions.Expression%601.Compile%2A>, который компилирует код, представляемый деревом выражений, в исполняемый делегат.  
  
 В следующем примере кода показан способ компиляции дерева выражений и выполнения результирующего кода.  
  
```vb  
' Creating an expression tree.  
Dim expr As Expression(Of Func(Of Integer, Boolean)) =  
    Function(num) num < 5  
  
' Compiling the expression tree into a delegate.  
Dim result As Func(Of Integer, Boolean) = expr.Compile()  
  
' Invoking the delegate and writing the result to the console.  
Console.WriteLine(result(4))  
  
' Prints True.  
  
' You can also use simplified syntax  
' to compile and run an expression tree.  
' The following line can replace two previous statements.  
Console.WriteLine(expr.Compile()(4))  
  
' Also prints True.  
```  
  
 Дополнительные сведения см. в разделе [Практическое руководство. Выполнение деревьев выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md).  
  
## <a name="see-also"></a>См. также

- <xref:System.Linq.Expressions>
- [Инструкции. Выполнение деревьев выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-execute-expression-trees.md)
- [Руководство. изменение деревьев выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/how-to-modify-expression-trees.md)
- [Лямбда-выражения](../../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
- [Общие сведения о среде DLR](../../../../framework/reflection-and-codedom/dynamic-language-runtime-overview.md)
- [Основные понятия программирования (Visual Basic)](../../../../visual-basic/programming-guide/concepts/index.md)
