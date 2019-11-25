---
title: Syntax used by DebugView property
description: В этой статье описывается специальный синтаксис, используемый свойством DebugView для получения строкового представления деревьев выражений.
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: 98ceba37aa226fab68ae1c1028e2a1139b3b8e7e
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346869"
---
# <a name="debugview-syntax"></a>Синтаксис `DebugView`

Свойство `DebugView` (доступно только при отладке) предоставляет строковое представление деревьев выражений. Большая часть синтаксиса достаточно проста для понимания; особые случаи описаны в разделах ниже.

Each example is followed by a comment block containing the `DebugView`.

## <a name="parameterexpression"></a>ParameterExpression

В начале имен переменных <xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> отображается символ "$".

Если параметр не имеет имени, оно назначается автоматически, например `$var1` или `$var2`.

### <a name="examples"></a>Примеры

```vb
Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer), "num")
'
'    $num
'

Dim numParam As ParameterExpression = Expression.Parameter(GetType(Integer))
'
'    $var1
'
```

## <a name="constantexpressions"></a>ConstantExpressions

Для объектов <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType>, представляющих целочисленные значения, строки и `null`, отображается значение константы.

For some numeric types, a suffix is added to the value:

| Type | Ключевое слово | Суффикс |
|--|--|--|
| <xref:System.UInt32> | [UInteger](../../../language-reference/data-types/uinteger-data-type.md) | U |
| <xref:System.Int64> | [Long](../../../language-reference/data-types/long-data-type.md) | L |
| <xref:System.UInt64> | [ULong](../../../language-reference/data-types/ulong-data-type.md) | UL |
| <xref:System.Double> | [Double](../../../language-reference/data-types/double-data-type.md) | D |
| <xref:System.Single> | [Single](../../../language-reference/data-types/single-data-type.md) | C |
| <xref:System.Decimal> | [Decimal](../../../language-reference/data-types/decimal-data-type.md) | M |

### <a name="examples"></a>Примеры

```vb
Dim num as Integer = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10
'

Dim num As Double = 10
Dim expr As ConstantExpression = Expression.Constant(num)
'
'    10D
'
```

## <a name="blockexpression"></a>BlockExpression

Если тип объекта <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> отличается от типа последнего выражения в блоке, то тип отображается в угловых скобках (`<` и `>`). В противном случае тип объекта <xref:System.Linq.Expressions.BlockExpression> не отображается.

### <a name="examples"></a>Примеры

```vb
Dim block As BlockExpression = Expression.Block(Expression.Constant("test"))
'
'    .Block() {
'        "test"
'    }
'

Dim block As BlockExpression = Expression.Block(
    GetType(Object),
    Expression.Constant("test")
)
'
'    .Block<System.Object>() {
'        "test"
'    }
'
```

## <a name="lambdaexpression"></a>LambdaExpression

Объекты <xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> отображаются вместе со своими типами делегатов.

Если лямбда-выражение не имеет имени, оно назначается автоматически, например `#Lambda1` или `#Lambda2`.

### <a name="examples"></a>Примеры

```vb
Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1)
)
'
'    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
'        1
'    }
'

Dim lambda As LambdaExpression = Expression.Lambda(Of Func(Of Integer))(
    Expression.Constant(1),
    "SampleLambda",
    Nothing
)
'
'    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
'        1
'    }
'
```

## <a name="labelexpression"></a>LabelExpression

Если указать значение по умолчанию для объекта <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType>, оно будет отображаться перед объектом <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType>.

Маркер `.Label` указывает начало метки. Маркер `.LabelTarget` задает конечную цель перехода для целевого объекта.

Если метка не имеет имени, оно назначается автоматически, например `#Label1` или `#Label2`.

### <a name="examples"></a>Примеры

```vb
Dim target As LabelTarget = Expression.Label(GetType(Integer), "SampleLabel")
Dim label1 As BlockExpression = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
)
'
'    .Block() {
'        .Goto SampleLabel { 0 };
'        .Label
'            -1
'        .LabelTarget SampleLabel:
'    }
'

Dim target As LabelTarget = Expression.Label()
Dim block As BlockExpression = Expression.Block(
    Expression.Goto(target),
    Expression.Label(target)
)
'
'    .Block() {
'        .Goto #Label1 { };
'        .Label
'        .LabelTarget #Label1:
'    }
'
```

## <a name="checked-operators"></a>Проверяемые операторы

Проверяемые операторы отображаются с символом `#` перед оператором. Например, проверяемый оператор сложения отображается как `#+`.

### <a name="examples"></a>Примеры

```vb
Dim expr As Expression = Expression.AddChecked(
    Expression.Constant(1),
    Expression.Constant(2)
)
'
'     1 #+ 2
'

Dim expr As Expression = Expression.ConvertChecked(
    Expression.Constant(10.0),
    GetType(Integer)
)
'
'    #(System.Int32)10D
'
```
