---
title: Синтаксис, используемый свойством DebugView (C#)
description: В этой статье описывается специальный синтаксис, используемый свойством DebugView для получения строкового представления деревьев выражений.
author: zspitz
ms.author: wiwagn
ms.date: 05/22/2019
ms.topic: reference
helpviewer_keywords:
- expression trees
- debugview
ms.openlocfilehash: bc3fc579ed8031d818241f41ac728ef7e5be0b99
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690107"
---
# <a name="debugview-syntax"></a>Синтаксис `DebugView`

Свойство `DebugView` (доступно только при отладке) предоставляет строковое представление деревьев выражений. Большая часть синтаксиса достаточно проста для понимания; особые случаи описаны в разделах ниже.

Каждый пример сопровождается комментарием с `DebugView`.

## <a name="parameterexpression"></a>ParameterExpression

В начале имен переменных <xref:System.Linq.Expressions.ParameterExpression?displayProperty=nameWithType> отображается символ `$`.

Если параметр не имеет имени, оно назначается автоматически, например `$var1` или `$var2`.

### <a name="examples"></a>Примеры

```csharp
ParameterExpression numParam =  Expression.Parameter(typeof(int), "num");
/*
    $num
*/

ParameterExpression numParam =  Expression.Parameter(typeof(int));
/*
    $var1
*/
```

## <a name="constantexpression"></a>ConstantExpression

Для объектов <xref:System.Linq.Expressions.ConstantExpression?displayProperty=nameWithType>, представляющих целочисленные значения, строки и `null`, отображается значение константы.

Для числовых типов, имеющих стандартные суффиксы, такие как литералы C#, суффикс добавляется к значению. В следующей таблице показаны суффиксы для различных числовых типов.

| Тип | Ключевое слово | Суффикс |
|--|--|--|
| <xref:System.UInt32?displayProperty=nameWithType> | [uint](../../../language-reference/keywords/uint.md) | U |
| <xref:System.Int64?displayProperty=nameWithType> | [long](../../../language-reference/keywords/long.md) | L |
| <xref:System.UInt64?displayProperty=nameWithType> | [ulong](../../../language-reference/keywords/ulong.md) | UL |
| <xref:System.Double?displayProperty=nameWithType> | [double](../../../language-reference/keywords/double.md) | D |
| <xref:System.Single?displayProperty=nameWithType> | [float](../../../language-reference/keywords/float.md) | C |
| <xref:System.Decimal?displayProperty=nameWithType> | [decimal](../../../language-reference/keywords/decimal.md) | M |

### <a name="examples"></a>Примеры

```csharp
int num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10
*/

double num = 10;
ConstantExpression expr = Expression.Constant(num);
/*
    10D
*/
```

## <a name="blockexpression"></a>BlockExpression

Если тип объекта <xref:System.Linq.Expressions.BlockExpression?displayProperty=nameWithType> отличается от типа последнего выражения в блоке, то тип отображается в угловых скобках (`<` и `>`). В противном случае тип объекта <xref:System.Linq.Expressions.BlockExpression> не отображается.

### <a name="examples"></a>Примеры

```csharp
BlockExpression block = Expression.Block(Expression.Constant("test"));
/*
    .Block() {
        "test"
    }
*/

BlockExpression block =  Expression.Block(typeof(Object), Expression.Constant("test"));
/*
    .Block<System.Object>() {
        "test"
    }
*/
```

## <a name="lambdaexpression"></a>LambdaExpression

Объекты <xref:System.Linq.Expressions.LambdaExpression?displayProperty=nameWithType> отображаются вместе со своими типами делегатов.

Если лямбда-выражение не имеет имени, оно назначается автоматически, например `#Lambda1` или `#Lambda2`.

### <a name="examples"></a>Примеры

```csharp
LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1));
/*
    .Lambda #Lambda1<System.Func'1[System.Int32]>() {
        1
    }
*/

LambdaExpression lambda =  Expression.Lambda<Func<int>>(Expression.Constant(1), "SampleLambda", null);
/*
    .Lambda #SampleLambda<System.Func'1[System.Int32]>() {
        1
    }
*/
```

## <a name="labelexpression"></a>LabelExpression

Если указать значение по умолчанию для объекта <xref:System.Linq.Expressions.LabelExpression?displayProperty=nameWithType>, оно будет отображаться перед объектом <xref:System.Linq.Expressions.LabelTarget?displayProperty=nameWithType>.

Маркер `.Label` указывает начало метки. Маркер `.LabelTarget` задает конечную цель перехода для целевого объекта.

Если метка не имеет имени, оно назначается автоматически, например `#Label1` или `#Label2`.

### <a name="examples"></a>Примеры

```csharp
LabelTarget target = Expression.Label(typeof(int), "SampleLabel");
BlockExpression block = Expression.Block(
    Expression.Goto(target, Expression.Constant(0)),
    Expression.Label(target, Expression.Constant(-1))
);
/*
    .Block() {
        .Goto SampleLabel { 0 };
        .Label
            -1
        .LabelTarget SampleLabel:
    }
*/

LabelTarget target = Expression.Label();
BlockExpression block = Expression.Block(
    Expression.Goto(target),
    Expression.Label(target)
);
/*
    .Block() {
        .Goto #Label1 { };
        .Label
        .LabelTarget #Label1:
    }
*/
```

## <a name="checked-operators"></a>Проверяемые операторы

Проверяемые операторы отображаются с символом `#` перед оператором. Например, проверяемый оператор сложения отображается как `#+`.

### <a name="examples"></a>Примеры

```csharp
Expression expr = Expression.AddChecked( Expression.Constant(1), Expression.Constant(2));
/*
    1 #+ 2
*/

Expression expr = Expression.ConvertChecked( Expression.Constant(10.0), typeof(int));
/*
    #(System.Int32)10D
*/
```
