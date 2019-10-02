---
title: Использование типов значений, допускающих значение NULL. Руководство по программированию на C#
ms.custom: seodec18
description: Узнайте, как в C# использовать типы значений, допускающие значение NULL
ms.date: 09/26/2019
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 65fc3b0ca94f9a41c9375e96000449b52cb7db26
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396165"
---
# <a name="using-nullable-value-types-c-programming-guide"></a>Использование типов значений, допускающих значение NULL (руководство по программированию на C#)

Типы значений, допускающие значение NULL, могут представлять все значения своего базового типа `T`, а также дополнительное значение [NULL](../../language-reference/keywords/null.md). Дополнительные сведения см. в статье [Типы значений, допускающие значение NULL (руководство по программированию на C#)](index.md).

> [!NOTE]
> В C# 8.0 появилась возможность использования ссылочных типов, допускающих значение NULL. Дополнительные сведения см. в статье [Ссылочные типы, допускающие значение NULL](../../nullable-references.md). Типы значений, допускающие значение NULL, доступны начиная с C# 2.

Вы можете ссылаться на тип значения, допускающий значение NULL, в любой из следующих взаимозаменяемых форм: `Nullable<T>` или `T?`. `T` должно быть типом значения.

## <a name="declaration-and-assignment"></a>Назначение и объявление

Так как тип значения можно неявно преобразовать в соответствующий тип значения, допускающий значение NULL, вы назначаете значение такому типу значения так же, как его базовому типу значения. Вы также можете присвоить значение `null`. Например:

[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a>Изучение значение типа, допускающего значение NULL

Используйте следующие свойства только для чтения, чтобы изучить экземпляр типа значения, допускающего значение NULL, со значением NULL и извлечь значение базового типа:

- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> указывает, имеет ли экземпляр типа, допускающего значение NULL, значение своего базового типа.

- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> возвращает значение базового типа, если <xref:System.Nullable%601.HasValue%2A> имеет значение `true`. Если <xref:System.Nullable%601.HasValue%2A> имеет значение `false`, свойство <xref:System.Nullable%601.Value%2A> выдает исключение <xref:System.InvalidOperationException>.

В коде в следующем примере используется свойство `HasValue`, чтобы проверить, содержит ли переменная значение, перед его отображением:

[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]

Вы также можете сравнить переменную типа значения, допускающего значение NULL, с `null` вместо использования свойства `HasValue`, как показано в следующем примере:

[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

Начиная с версии C# 7.0 для проверки и получения значения типа значения, допускающего значение NULL, можно использовать [сопоставление шаблонов](../../pattern-matching.md):

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a>Преобразование из типа значения, допускающего значение NULL, в базовый тип

Если вам нужно присвоить значение типа значения, допускающего значение NULL, типу, не допускающему значение NULL, используйте [оператор объединения с NULL`??`](../../language-reference/operators/null-coalescing-operator.md), чтобы указать значение для присваивания, если значение типа значения, допускающего значение NULL, равно NULL (вы также можете использовать метод <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>):

[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

Используйте метод <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>, если значение, которое будет использоваться, когда значение типа значения, допускающего значение NULL, равно `null`, должно быть значением по умолчанию базового типа.

Вы можете явно привести тип значения, допускающий значение NULL, к типу, не допускающему значение NULL. Например:

[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

Во время выполнения, если значение типа значения, допускающего значение NULL, равно `null`, явное приведение вызывает исключение <xref:System.InvalidOperationException>.

Тип, не допускающий значение NULL, неявно преобразуется в соответствующий тип, допускающий значение NULL.

## <a name="operators"></a>Операторы

Предопределенные унарные и бинарные операторы, а также любые операторы, определенные программистом, которые существуют для типов значений, также можно использовать и с соответствующими типами, допускающими значение NULL. Эти операторы возвращают значение `null`, если один или оба операнда имеют значение `null`. В противном случае оператор использует содержащиеся значения для вычисления результата. Например:

[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]

> [!NOTE]
> Для типа `bool?` предопределенные операторы `&` и `|` не следуют правилам, описанным в этом разделе: результат вычисления оператора может быть отличным от NULL, даже если один из операндов имеет значение `null`. См. подробнее о [логических операторах, поддерживающих значение NULL](../../language-reference/operators/boolean-logical-operators.md#nullable-boolean-logical-operators) в описании [логических операторов](../../language-reference/operators/boolean-logical-operators.md).
  
Для операторов отношения (`<`, `>`, `<=`, `>=`), если один или оба операнда имеют значение `null`, результатом будет `false`. Тут важно не полагать, что если какая-то операция сравнения (например, `<=`) возвращает `false`, то противоположное сравнение (`>`) обязательно вернет `true`. В следующем примере показано, что 10

- не больше и не равно значению `null`,
- не меньше чем `null`.

[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]

В приведенном выше примере видно, что проверка на равенство двух типов значения, допускающих значение NULL, которые оба равны NULL, всегда даст `true`.

Дополнительные сведения см. в разделе о [поднятых операторах](~/_csharplang/spec/expressions.md#lifted-operators) в [спецификации языка C#](~/_csharplang/spec/introduction.md).

## <a name="boxing-and-unboxing"></a>Упаковка-преобразование и распаковка-преобразование

Тип, допускающий значение NULL, [упакован](../types/boxing-and-unboxing.md) по следующим правилам:

- Если <xref:System.Nullable%601.HasValue%2A> возвращает `false`, создается пустая ссылка.
- Если <xref:System.Nullable%601.HasValue%2A> возвращает `true`, упаковывается значение базового типа `T`, а не экземпляр <xref:System.Nullable%601>.

Можно распаковать упакованный тип значения в соответствующий тип, допускающий значение NULL, как показано в следующем примере:

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="see-also"></a>См. также

- [Типы значений, допускающие значение NULL](index.md)
- [What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Что означает термин "расширенные"?)
