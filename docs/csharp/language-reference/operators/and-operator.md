---
title: Оператор &amp; (справочник по C#)
ms.date: 10/29/2018
f1_keywords:
- '&_CSharpKeyword'
helpviewer_keywords:
- bitwise AND operator [C#]
- ampersand operator (&) [C#]
- '& operator [C#]'
- AND operator (&) [C#]
ms.assetid: afa346d5-90ec-4b1f-a2c8-3881f018741d
ms.openlocfilehash: a8f76ded0ef9f8e8099838a903d90f1695324991
ms.sourcegitcommit: b5cd9d5d3b75a5537fc9ad8a3f085f0bb1845ee0
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2018
ms.locfileid: "43510982"
---
# <a name="amp-operator-c-reference"></a>Оператор &amp; (справочник по C#)

Оператор `&` поддерживается в двух формах: унарный оператор address-of или бинарный логический оператор.

## <a name="unary-address-of-operator"></a>Унарный оператор address-of

Унарный оператор `&` возвращает адрес полученного операнда. Дополнительные сведения см. в статье [Практическое руководство. Получение адреса переменной](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-address-of-a-variable.md).

Для оператора получения адреса `&` требуется [небезопасный](../keywords/unsafe.md) контекст.

## <a name="integer-logical-bitwise-and-operator"></a>Целочисленная побитовая логическая операция И

Для целочисленных типов оператор `&` выполняет побитовую логическую операцию И для всех своих операндов.

[!code-csharp-interactive[integer logical bitwise AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#IntegerOperands)]

> [!NOTE]
> В предыдущем примере используются двоичные литералы, [впервые появившиеся в C# 7.0](../../whats-new/csharp-7.md#numeric-literal-syntax-improvements) и [улучшенные в C# 7.2](../../whats-new/csharp-7-2.md#leading-underscores-in-numeric-literals).

Так как операции с целочисленными типами обычно разрешены для типов перечисления, оператор `&` также поддерживает операнды [enum](../keywords/enum.md).

## <a name="boolean-logical-and-operator"></a>Логический оператор И

Для операндов типа [bool](../keywords/bool.md) оператор `&` вычисляет логическое И всех своих операндов. Результат операции `x & y` принимает значение `true`, если оба оператора `x` и `y` имеют значение `true`. В противном случае результат будет `false`.

Оператор `&` вычисляет оба операнда, даже если первый операнд имеет значение `false` и результат должен принять значение `false`, независимо от значения второго операнда. В следующем примере продемонстрировано такое поведение.

[!code-csharp-interactive[bool logical AND](~/samples/snippets/csharp/language-reference/operators/AndOperatorExamples.cs#BooleanOperands)]

[Условный оператор И](conditional-and-operator.md) `&&` также вычисляет логическое И своих операндов, но он вычисляет второй операнд только в том случае, если первый операнд имеет значение `true`.

Для логических операндов, допускающих значение NULL, поведение оператора `&` согласуется с троичной логикой SQL. Дополнительные сведения см. в разделе [Тип bool?](../../programming-guide/nullable-types/using-nullable-types.md#the-bool-type) статьи [Использование допускающих значение NULL типов](../../programming-guide/nullable-types/using-nullable-types.md).

## <a name="operator-overloadability"></a>Возможность перегрузки оператора

Определяемые пользователем типы могут вызвать [перегрузку](../keywords/operator.md) бинарного оператора `&`. При перегрузке бинарного оператора `&` неявно перегружается и соответствующий [Оператор присваивания И](and-assignment-operator.md) `&=`.

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в разделах [Оператор address-of](~/_csharplang/spec/unsafe-code.md#the-address-of-operator) и [Логические операторы](~/_csharplang/spec/expressions.md#logical-operators) в [Спецификации языка C#](../language-specification/index.md).

## <a name="see-also"></a>См. также

- [Справочник по C#](../index.md)
- [Руководство по программированию на C#](../../programming-guide/index.md)
- [Операторы в C#](index.md)
- [Типы указателей](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [Оператор |](or-operator.md)
- [Оператор ^](xor-operator.md)
- [Оператор ~](bitwise-complement-operator.md)
- [Оператор &&](conditional-and-operator.md)
