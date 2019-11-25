---
title: Справочник по C#. Типы значений, допускающие значение NULL
description: Сведения о типах C#, допускающих значение NULL, и их использовании
ms.date: 11/04/2019
helpviewer_keywords:
- nullable value types [C#]
ms.openlocfilehash: b9400cd76eb0430dbe9c278e835a3cec7f9f131e
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740969"
---
# <a name="nullable-value-types-c-reference"></a>Справочник по C#. Типы значений, допускающие значение NULL

Тип значений, допускающий значение NULL, `T?` может представлять все значения своего [базового типа](../keywords/value-types.md) `T`, а также дополнительное значение [NULL](../keywords/null.md). Например, можно присвоить переменной `bool?` любое из следующих трех значений: `true`, `false` или `null`. Базовый тип значения `T` не может соответствовать типу значения, допускающему значение NULL.

> [!NOTE]
> В C# 8.0 появилась возможность использования ссылочных типов, допускающих значение NULL. Дополнительные сведения см. в статье [Ссылочные типы, допускающие значение NULL](../../nullable-references.md). Типы значений, допускающие значение NULL, доступны начиная с C# 2.

Типы, допускающие значение NULL, представляют собой экземпляры универсальной структуры <xref:System.Nullable%601?displayProperty=nameWithType>. Вы можете ссылаться на тип значения, допускающий значение NULL, с базовым типом `T` в любой из следующих взаимозаменяемых форм: `Nullable<T>` или `T?`.

Тип значения, допускающий значение NULL, следует использовать, когда нужно представить неопределенное значение его базового типа. Например, логическая переменная (или `bool`) может иметь только значения `true` или `false`. Однако в некоторых приложениях значение переменной может быть неопределенным или отсутствовать. Например, поле базы данных может содержать значение `true` или `false` либо вообще никакого значения, то есть `NULL`. В этом сценарии можно использовать тип `bool?`.

## <a name="declaration-and-assignment"></a>Назначение и объявление

Так как тип значения можно неявно преобразовать в соответствующий тип значения, допускающий значение NULL, вы назначаете значение переменной такого типа значения так же, как для базового типа значения. Вы также можете присвоить значение `null`. Например:

[!code-csharp[declare and assign](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#Declaration)]

Значение по умолчанию для типа значения, допускающего значение NULL, представляет `null`, то есть это экземпляр, свойство <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> которого возвращает `false`.

## <a name="examination-of-an-instance-of-a-nullable-value-type"></a>Проверка экземпляра типа значения, допускающего значение NULL

Начиная с версии C# 7.0 можно использовать оператор [`is` с шаблоном типа ](../operators/type-testing-and-cast.md#type-testing-with-pattern-matching) как для проверки экземпляра типа, допускающего значение NULL, для `null`, так и для извлечения значения базового типа:

[!code-csharp-interactive[use pattern matching](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#PatternMatching)]

Вы всегда можете использовать следующие свойства только для чтения, чтобы проверить и получить значение переменной типа, допускающего значение NULL:

- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> указывает, имеет ли экземпляр типа, допускающего значение NULL, значение своего базового типа.

- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> возвращает значение базового типа, если <xref:System.Nullable%601.HasValue%2A> имеет значение `true`. Если <xref:System.Nullable%601.HasValue%2A> имеет значение `false`, свойство <xref:System.Nullable%601.Value%2A> выдает исключение <xref:System.InvalidOperationException>.

В следующем примере используется свойство `HasValue`, чтобы проверить, содержит ли переменная значение, перед его отображением:

[!code-csharp-interactive[use HasValue](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#HasValue)]

Вы также можете сравнить переменную типа значения, допускающего значение NULL, с `null` вместо использования свойства `HasValue`, как показано в следующем примере:

[!code-csharp-interactive[use comparison with null](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#CompareWithNull)]

## <a name="conversion-from-a-nullable-value-type-to-an-underlying-type"></a>Преобразование из типа значения, допускающего значение NULL, в базовый тип

Если необходимо присвоить значение типа, допускающего значение NULL, переменной типа значения, не допускающего значения NULL, может потребоваться указать значение, назначаемое вместо `null`. Для этого используйте [оператор объединения со значением NULL`??`](../operators/null-coalescing-operator.md) (можно также применить метод <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType> для той же цели):

[!code-csharp-interactive[?? operator](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#NullCoalescing)]

Если вы хотите использовать [значение по умолчанию](../keywords/default-values-table.md) базового типа значения вместо `null`, воспользуйтесь методом <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>.

Вы можете явно привести тип значения, допускающий значение NULL, к типу, не допускающему значение NULL, как показано в примере ниже.

[!code-csharp[explicit cast](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#Cast)]

Во время выполнения, если значение типа значения, допускающего значение NULL, равно `null`, явное приведение вызывает исключение <xref:System.InvalidOperationException>.

Тип `T`, не допускающий значение NULL, неявно преобразуется в соответствующий тип, допускающий значение NULL, `T?`.

## <a name="lifted-operators"></a>Операторы с нулификацией

Предопределенные унарные и бинарные операторы или любые перегруженные операторы, поддерживаемые типом значения `T`, также поддерживаются соответствующим типом значения, допускающим значение NULL, `T?`. Эти операторы, также называемые *операторами с нулификацией*, возвращают значение `null`, если один или оба операнда имеют значение `null`. В противном случае оператор использует содержащиеся значения операндов для вычисления результата. Например:

[!code-csharp[lifted operators](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#LiftedOperator)]

> [!NOTE]
> Для типа `bool?` предопределенные операторы `&` и `|` не следуют правилам, описанным в этом разделе: результат вычисления оператора может быть отличным от NULL, даже если один из операндов имеет значение `null`. См. подробнее о [логических операторах, поддерживающих значение NULL](../operators/boolean-logical-operators.md#nullable-boolean-logical-operators) в описании [логических операторов](../operators/boolean-logical-operators.md).

Для [операторов сравнения](../operators/comparison-operators.md) `<`, `>`, `<=` и `>=`, если один или оба операнда равны `null`, результат будет равен `false`. В противном случае сравниваются содержащиеся значения операндов. Тут важно не полагать, что если какая-то операция сравнения (например, `<=`) возвращает `false`, то противоположное сравнение (`>`) обязательно вернет `true`. В следующем примере показано, что 10

- не больше и не равно значению `null`,
- не меньше чем `null`.

[!code-csharp-interactive[relational and equality operators](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#ComparisonOperators)]

В приведенном выше примере видно, что проверка на равенство двух экземпляров типа значения, допускающего значение NULL, которые оба равны `null`, всегда даст `true`.

Если между двумя типами данных определено [пользовательское преобразование](../operators/user-defined-conversion-operators.md) типов, то это же преобразование можно также использовать между соответствующими типами, допускающими значение NULL.

## <a name="boxing-and-unboxing"></a>Упаковка-преобразование и распаковка-преобразование

Экземпляр типа значения, допускающего значение NULL, `T?` [упакован](../../programming-guide/types/boxing-and-unboxing.md) следующим образом:

- Если <xref:System.Nullable%601.HasValue%2A> возвращает `false`, создается пустая ссылка.
- Если <xref:System.Nullable%601.HasValue%2A> возвращает `true`, упаковывается соответствующее значение базового типа `T`, а не экземпляр <xref:System.Nullable%601>.

Можно распаковать упакованный тип значения `T` в соответствующий тип, допускающий значение NULL, `T?`, как показано в следующем примере:

[!code-csharp-interactive[boxing and unboxing](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#Boxing)]

## <a name="how-to-identify-a-nullable-value-type"></a>Идентификация типа значений, допускающего значение NULL

В следующем примере показано, как определить, представляет ли экземпляр <xref:System.Type?displayProperty=nameWithType> сконструированный тип значений, допускающий значение NULL, т. е. тип <xref:System.Nullable%601?displayProperty=nameWithType> с указанным параметром типа `T`:

[!code-csharp-interactive[whether Type is nullable](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsTypeNullable)]

Как показано в примере, при помощи оператора [typeof](../operators/type-testing-and-cast.md#typeof-operator) можно создать экземпляр <xref:System.Type?displayProperty=nameWithType>.

Если вы хотите определить, принадлежит ли экземпляр к типу значений, допускающему значение NULL, не используйте метод <xref:System.Object.GetType%2A?displayProperty=nameWithType> для получения экземпляра <xref:System.Type> для тестирования с помощью приведенного выше кода. При вызове метода <xref:System.Object.GetType%2A?displayProperty=nameWithType> в экземпляре типа значений, допускающего значение NULL, экземпляр [упаковывается](#boxing-and-unboxing) в <xref:System.Object>. Так как упаковка экземпляра типа значений, допускающего значение NULL, значение которого отлично от NULL, эквивалентна упаковке значения базового типа, <xref:System.Object.GetType%2A> возвращается экземпляр <xref:System.Type>, представляющий базовый тип типа значений, допускающего значение NULL:

[!code-csharp-interactive[GetType example](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#GetType)]

Кроме того, не используйте оператор [is](../operators/type-testing-and-cast.md#is-operator), чтобы определить, принадлежит ли экземпляр к типу значений, допускающему значение NULL. Как показано в следующем примере, вы не можете отличить типы экземпляра типа значений, допускающего значение NULL, и его экземпляра базового типа с помощью оператора `is`:

[!code-csharp-interactive[is operator example](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsOperator)]

Чтобы определить, принадлежит ли экземпляр типу значений, допускающему значение NULL, можно использовать код, представленный в следующем примере:

[!code-csharp-interactive[whether an instance is of a nullable type](~/samples/csharp/language-reference/builtin-types/NullableValueTypes.cs#IsInstanceNullable)]

> [!NOTE]
> Методы, описанные в этом разделе, неприменимы в случае [ссылочных типов, допускающих значения NULL](../../nullable-references.md).

## <a name="c-language-specification"></a>Спецификация языка C#

Дополнительные сведения см. в следующих разделах статьи [Спецификация языка C#](~/_csharplang/spec/introduction.md):

- [Типы, допускающие значения NULL](~/_csharplang/spec/types.md#nullable-types)
- [Операторы с нулификацией](~/_csharplang/spec/expressions.md#lifted-operators)
- [Неявные преобразования, допускающие значения NULL](~/_csharplang/spec/conversions.md#implicit-nullable-conversions)
- [Явные преобразования, допускающие значения NULL](~/_csharplang/spec/conversions.md#explicit-nullable-conversions)
- [Операторы преобразования с нулификацией](~/_csharplang/spec/conversions.md#lifted-conversion-operators)

## <a name="see-also"></a>См. также

- [справочник по C#](../index.md)
- [What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Что означает термин "расширенные"?)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
- <xref:System.Nullable.GetUnderlyingType%2A?displayProperty=nameWithType>
- [Ссылочные типы, допускающие значение NULL](../../nullable-references.md)
