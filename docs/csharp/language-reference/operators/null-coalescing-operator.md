---
title: ?? Справочник по C#. Оператор -
ms.custom: seodec18
ms.date: 06/07/2019
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- null-coalescing operator [C#]
- ?? operator [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: 8ca97261b348b7813ab179abbc1f2c5f535966a1
ms.sourcegitcommit: 5ae6affa0b171be3bb5f4729fb68ea4fe799f959
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2019
ms.locfileid: "66816010"
---
# <a name="-operator-c-reference"></a>?? operator (Справочник по C#)

Оператор объединения с NULL `??` возвращает значение своего операнда слева, если его значение не равно `null`. В противном случае он вычисляет операнд справа и возвращает его результат. Оператор `??` не выполняет оценку своего операнда справа, если его операнд слева имеет значение, отличное от NULL.

Оператор объединения с NULL имеет правую ассоциативность, то есть выражение формы

```csharp
a ?? b ?? c
```

вычисляется как

```csharp
a ?? (b ?? c)
```

Оператор `??` может быть полезен в таких случаях:

- В выражениях с [NULL-условными операторами ?. и ?[]](member-access-operators.md#null-conditional-operators--and-) можно использовать оператор объединения с NULL, чтобы задать альтернативное выражение для оценки на случай, если результат выражения с NULL-условной операцией будет равен `null`.

  [!code-csharp-interactive[with null-conditional](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullConditional)]

- При работе с [типами, допускающими значение NULL](../../programming-guide/nullable-types/index.md), и если нужно указать значение базового типа значения, используйте оператор объединения с NULL для указания значения, возвращаемого в том случае, если значение типа, допускающего значение NULL, равно `null`.

  [!code-csharp-interactive[with nullable types](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithNullableTypes)]

  Используйте метод <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>, если значение, которое будет использоваться, когда значение типа, допускающего значение NULL, равно `null`, должно быть значением по умолчанию базового типа.

- Начиная с C# 7.0 можно сократить код проверки аргументов, используя [выражение `throw`](../keywords/throw.md#the-throw-expression) в качестве правого операнда оператора объединения с NULL:

  [!code-csharp[with throw expression](~/samples/csharp/language-reference/operators/NullCoalescingOperator.cs#WithThrowExpression)]

  В предыдущем примере также демонстрируются способы определения свойства с помощью [членов, заданных выражениями](../../programming-guide/statements-expressions-operators/expression-bodied-members.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Оператор объединения с NULL перегружать нельзя.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделе об [операторе объединения со значением NULL](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Операторы ?. и ?[]](member-access-operators.md#null-conditional-operators--and-)
- [Оператор ?](conditional-operator.md)
