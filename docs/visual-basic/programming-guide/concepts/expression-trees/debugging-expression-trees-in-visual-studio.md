---
title: Отладка деревьев выражений в Visual Studio (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 492cc28f-b7a2-4c47-b582-b3c437b8a5d5
ms.openlocfilehash: 7fc97d898c5956b5a569036e6e0fe1174714576d
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65879827"
---
# <a name="debugging-expression-trees-in-visual-studio-visual-basic"></a>Отладка деревьев выражений в Visual Studio (Visual Basic)
При отладке приложений можно анализировать структуру и содержимое деревьев выражений. Чтобы получить краткий обзор структуры дерева выражения, можно использовать `DebugView` свойства, которое представляет деревья выражений, используя специальный синтаксис, описанный [ниже](#debugview-syntax). (Обратите внимание, что `DebugView` доступна только в режиме отладки.)  

![DebugView дерева выражения в отладчике Visual Studio](media/debugging-expression-trees-in-visual-studio/debugview_vb.png)

Так как `DebugView` представляет собой строку, можно использовать [встроенные визуализатор текста](https://docs.microsoft.com/visualstudio/debugger/view-strings-visualizer#open-a-string-visualizer) на его просмотр по нескольким строкам, выбрав **визуализатор текста** щелкните значок лупы рядом с полем `DebugView` Метка.

 ![Применяется к результаты «DebugView» средство визуализации текста](media/debugging-expression-trees-in-visual-studio/string_visualizer_vb.png)

Кроме того, можно установить и использовать [пользовательский визуализатор](https://docs.microsoft.com/visualstudio/debugger/create-custom-visualizers-of-data) для деревьев выражений:

* [Для чтения выражения](https://github.com/agileobjects/ReadableExpressions) ([лицензии MIT](https://github.com/agileobjects/ReadableExpressions/blob/master/LICENSE.md), доступный по адресу [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=vs-publisher-1232914.ReadableExpressionsVisualizers)), отображает дерево выражения в виде C# кода:

  ![Для чтения выражения визуализатора](media/debugging-expression-trees-in-visual-studio/readable_expressions_visualizer.png)

* [Визуализатор дерева выражения](https://github.com/zspitz/ExpressionToString#visual-studio-debugger-visualizer-for-expression-trees) ([лицензии MIT](https://github.com/zspitz/ExpressionToString/blob/master/LICENSE)), который обеспечивает графическое представление дерева выражения, его свойства и связанные объекты; и может преобразовать дерево выражения, с помощью кода Visual Basic:

  ![Визуализатор ExpressionToString](media/debugging-expression-trees-in-visual-studio/expression_to_string_visualizer_vb.png)

### <a name="to-open-a-visualizer-for-an-expression-tree"></a>Открытие визуализатора дерева выражения  
  
1. Щелкните значок лупы рядом с дерева выражения в **подсказок по данным**, **Watch** окне **"Видимые"** окна, или **"Локальные"** окна.  
  
     Отображается список доступных визуализаторы.: 

      ![Открытие визуализаторы из Visual Studio](media/debugging-expression-trees-in-visual-studio/expression_tree_visualizers_vb.png)

2. Щелкните визуализатор, который необходимо использовать.  

## <a name="debugview-syntax"></a>`DebugView` Синтаксис 

Каждый тип выражения отображается в визуализаторе, как описано в следующих разделах.

## <a name="parameterexpressions"></a>ParameterExpressions

В начале имен переменных <xref:System.Linq.Expressions.ParameterExpression> отображается символ "$".

Если параметр не имеет имени, оно назначается автоматически, например `$var1` или `$var2`.

### <a name="examples"></a>Примеры

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer), "num")
    ```

    Свойство `DebugView`

    `$num`

- `Expression`

    ```vb
    Dim numParam As ParameterExpression =
    Expression.Parameter(GetType(Integer))
    ```

    Свойство `DebugView`

    `$var1`

## <a name="constantexpressions"></a>ConstantExpressions
 Для объектов <xref:System.Linq.Expressions.ConstantExpression>, представляющих целочисленные значения, строки и `null`, отображается значение константы.

### <a name="examples"></a>Примеры

- `Expression`

    ```vb
    Dim num as Integer= 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    Свойство `DebugView`

    10

- `Expression`

    ```vb
    Dim num As Double = 10
    Dim expr As ConstantExpression = Expression.Constant(num)
    ```

    Свойство `DebugView`

    10D

## <a name="blockexpression"></a>BlockExpression

Если тип объекта <xref:System.Linq.Expressions.BlockExpression> отличается от типа последнего выражения в блоке, то тип отображается в свойстве `DebugInfo` в угловых скобках (\< и >). В противном случае тип объекта <xref:System.Linq.Expressions.BlockExpression> не отображается.

### <a name="examples"></a>Примеры

- `Expression`

    ```vb
    Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
    ```

    Свойство `DebugView`

    `.Block() {`

    `"test"`

    `}`

- `Expression`

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

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1))
    ```

    Свойство `DebugView`

    `.Lambda #Lambda1<System.Func'1[System.Int32]>() {`

    `1`

    `}`

- `Expression`

    ```vb
    Dim lambda As LambdaExpression =
    Expression.Lambda(Of Func(Of Integer))(Expression.Constant(1), "SampleLambda", Nothing)
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

- `Expression`

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

- `Expression`

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

- `Expression`

    ```vb
    Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1), Expression.Constant(2))
    ```

    Свойство `DebugView`

    `1 #+ 2`

- `Expression`

    ```vb
    Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0), GetType(Integer))
    ```

    Свойство `DebugView`

    `#(System.Int32)10D`

## <a name="see-also"></a>См. также

- [Expression Trees (Visual Basic)](../../../../visual-basic/programming-guide/concepts/expression-trees/index.md) (Деревья выражений (Visual Basic))
- [Отладка в Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)
- [Создание настраиваемых визуализаторов](/visualstudio/debugger/create-custom-visualizers-of-data)
