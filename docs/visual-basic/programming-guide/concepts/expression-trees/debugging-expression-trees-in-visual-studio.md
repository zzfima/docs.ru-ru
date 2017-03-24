---
title: "Отладка деревьев выражений в Visual Studio (Visual Basic) | Документы Microsoft"
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
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: efbd8c19947c45b3ba15ce7b574000d56526ef45
ms.lasthandoff: 03/13/2017

---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Отладка деревьев выражений в Visual Studio (Visual Basic)
При отладке приложений можно анализировать структуру и содержимое деревьев выражений. Чтобы получить краткий обзор структуру дерева выражений, можно использовать `DebugView` свойства, которое доступно только в режиме отладки. Дополнительные сведения об отладке см. в разделе [отладки в Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio).  
  
 Для оптимизации представления содержимого деревьев выражений `DebugView` свойство использует визуализаторы Visual Studio. Дополнительные сведения см. в разделе [создать пользовательские визуализаторы](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data).  
  
### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Открытие визуализатора дерева выражений  
  
1.  Щелкните значок лупы рядом `DebugView` свойство дерева выражений в **подсказки**, **Контрольные значения** окна, **видимые** окна, или **локальные** окна.  
  
     Откроется список визуализаторов.  
  
2.  Щелкните визуализатор, который необходимо использовать.  
  
 Тип каждого выражения отображается в визуализаторе, как описано в следующих разделах.  
  
## <a name="parameterexpressions"></a>ParameterExpressions  
 <xref:System.Linq.Expressions.ParameterExpression>имена переменных, отображаются с символом «$» в начале.</xref:System.Linq.Expressions.ParameterExpression>  
  
 Если параметр не имеет имени, то оно назначается автоматически, например `$var1` или `$var2`.  
  
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
 Для <xref:System.Linq.Expressions.ConstantExpression>объектов, представляющих целочисленные значения, строки, и `null`, отображается значение константы.</xref:System.Linq.Expressions.ConstantExpression>  
  
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
 Если тип <xref:System.Linq.Expressions.BlockExpression>объекта отличается от типа последнего выражения в блоке, то он отображается в `DebugInfo` свойство в угловые скобки (\< и настроек).</xref:System.Linq.Expressions.BlockExpression> В противном случае — тип <xref:System.Linq.Expressions.BlockExpression>объект не отображается.</xref:System.Linq.Expressions.BlockExpression>  
  
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
  
## <a name="lambdaexpression"></a>Лямбда-выражение  
 <xref:System.Linq.Expressions.LambdaExpression>объекты отображаются вместе с их типами делегатов.</xref:System.Linq.Expressions.LambdaExpression>  
  
 Если лямбда-выражение не имеет имени, то оно назначается автоматически, например `#Lambda1` или `#Lambda2`.  
  
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
 Если указать значение по умолчанию для <xref:System.Linq.Expressions.LabelExpression>объекта, то оно будет отображаться перед <xref:System.Linq.Expressions.LabelTarget>объекта.</xref:System.Linq.Expressions.LabelTarget> </xref:System.Linq.Expressions.LabelExpression>  
  
 `.Label` Маркер указывает на начало метки. `.LabelTarget` Маркера задает конечную цель перехода для целевого объекта.  
  
 Если подпись не имеет имени, то оно назначается автоматически, например `#Label1` или `#Label2`.  
  
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
 Проверяемые операторы отображаются с символом «#» перед оператором. Например, проверяемый оператор сложения отображается как `#+`.  
  
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
 [Деревья выражений (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md)   
 [Отладка в Visual Studio](https://docs.microsoft.com/visualstudio/debugger/debugging-in-visual-studio)   
 [Создание пользовательских визуализаторов](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data)
