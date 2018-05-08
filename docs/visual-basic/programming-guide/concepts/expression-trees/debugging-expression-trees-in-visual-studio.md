---
title: Отладка деревьев выражений в Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 2addba2654067eaaf6c621c927e0992308879ae4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Отладка деревьев выражений в Visual Studio (Visual Basic)
При отладке приложений можно анализировать структуру и содержимое деревьев выражений. Чтобы получить краткий обзор структуры дерева выражения, можно использовать свойство `DebugView`, которое доступно только в режиме отладки. Дополнительные сведения об отладке см. в разделе [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio).  
  
 Для оптимизации представления содержимого деревьев выражений свойство `DebugView` использует визуализаторы Visual Studio. Дополнительные сведения см. в статье, посвященной [созданию пользовательских визуализаторов](/visualstudio/debugger/create-custom-visualizers-of-data).  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Открытие визуализатора дерева выражения  
  
1.  Щелкните значок лупы рядом с именем свойства `DebugView` дерева выражения в окне **Советы**, **Контрольные значения**, **Видимые** или **Локальные**.  
  
     Откроется список визуализаторов.  
  
2.  Щелкните визуализатор, который необходимо использовать.  
  
 Каждый тип выражения отображается в визуализаторе, как описано в следующих разделах.  
  
## <a name="parameterexpressions"></a>ParameterExpressions  
 В начале имен переменных <xref:System.Linq.Expressions.ParameterExpression> отображается символ "$".  
  
 Если параметр не имеет имени, оно назначается автоматически, например `$var1` или `$var2`.  
  
### <a name="examples"></a>Примеры  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer), "num")  
    ```  
  
     Свойство `DebugView`  
  
     `$num`  
  
-   `Expression`  
  
    ```vb  
    Dim numParam As ParameterExpression =   
    Expression.Parameter(GetType(Integer))  
    ```  
  
     Свойство `DebugView`  
  
     `$var1`  
  
## <a name="constantexpressions"></a>ConstantExpressions  
 Для объектов <xref:System.Linq.Expressions.ConstantExpression>, представляющих целочисленные значения, строки и `null`, отображается значение константы.  
  
### <a name="examples"></a>Примеры  
  
-   `Expression`  
  
    ```vb  
    Dim num as Integer= 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     Свойство `DebugView`  
  
     10  
  
-   `Expression`  
  
    ```vb  
    Dim num As Double = 10  
    Dim expr As ConstantExpression = Expression.Constant(num)  
    ```  
  
     Свойство `DebugView`  
  
     10D  
  
## <a name="blockexpression"></a>BlockExpression  
 Если тип объекта <xref:System.Linq.Expressions.BlockExpression> отличается от типа последнего выражения в блоке, то тип отображается в свойстве `DebugInfo` в угловых скобках (\< и >). В противном случае тип объекта <xref:System.Linq.Expressions.BlockExpression> не отображается.  
  
### <a name="examples"></a>Примеры  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))  
    ```  
  
     Свойство `DebugView`  
  
     `.Block() {`  
  
     `"test"`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim block As BlockExpression =   
    Expression.Block(GetType(Object), Expression.Constant("test"))  
    ```  
  
     Свойство `DebugView`  
  
     `.Block<System.Object>() {`  
  
     `"test"`  
  
     `}`  
  
## <a name="lambdaexpression"></a>LambdaExpression  
 Объекты <xref:System.Linq.Expressions.LambdaExpression> отображаются вместе со своими типами делегатов.  
  
 Если лямбда-выражение не имеет имени, оно назначается автоматически, например `#Lambda1` или `#Lambda2`.  
  
### <a name="examples"></a>Примеры  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))  
    ```  
  
     Свойство `DebugView`  
  
     `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim lambda As LambdaExpression =   
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLamda", Nothing)  
    ```  
  
     Свойство `DebugView`  
  
     `.Lambda SampleLambda<System.Func'1[System.Int32]>() {`  
  
     `1`  
  
     `}`  
  
## <a name="labelexpression"></a>LabelExpression  
 Если указать значение по умолчанию для объекта <xref:System.Linq.Expressions.LabelExpression>, оно будет отображаться перед объектом <xref:System.Linq.Expressions.LabelTarget>.  
  
 Маркер `.Label` указывает начало метки. Маркер `.LabelTarget` задает конечную цель перехода для целевого объекта.  
  
 Если метка не имеет имени, оно назначается автоматически, например `#Label1` или `#Label2`.  
  
### <a name="examples"></a>Примеры  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")  
    Dim label1 As BlockExpression = Expression.Block(  
    Expression.Goto(target, Expression.Constant(0)),  
    Expression.Label(target, Expression.Constant(-1)))  
    ```  
  
     Свойство `DebugView`  
  
     `.Block() {`  
  
     `.Goto SampleLabel { 0 };`  
  
     `.Label`  
  
     `-1`  
  
     `.LabelTarget SampleLabel:`  
  
     `}`  
  
-   `Expression`  
  
    ```vb  
    Dim target As LabelTarget = Expression.Label()  
    Dim block As BlockExpression = Expression.Block(  
    Expression.Goto(target), Expression.Label(target))  
    ```  
  
     Свойство `DebugView`  
  
     `.Block() {`  
  
     `.Goto #Label1 { };`  
  
     `.Label`  
  
     `.LabelTarget #Label1:`  
  
     `}`  
  
## <a name="checked-operators"></a>Проверяемые операторы  
 Проверяемые операторы отображаются с символом # перед оператором. Например, проверяемый оператор сложения отображается как `#+`.  
  
### <a name="examples"></a>Примеры  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.AddChecked(  
    Expression.Constant(1), Expression.Constant(2))  
    ```  
  
     Свойство `DebugView`  
  
     `1 #+ 2`  
  
-   `Expression`  
  
    ```vb  
    Dim expr As Expression = Expression.ConvertChecked(  
    Expression.Constant(10.0), GetType(Integer))  
    ```  
  
     Свойство `DebugView`  
  
     `#(System.Int32)10D`  
  
## <a name="see-also"></a>См. также  
 [Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))  
 [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)  
 [Создание настраиваемых визуализаторов](/visualstudio/debugger/create-custom-visualizers-of-data)
