---
title: Использование допускающих значение NULL типов (руководство по программированию на C#)
description: Узнайте, как в C# использовать типы, допускающие значение NULL
ms.date: 08/02/2018
helpviewer_keywords:
- nullable types [C#], about nullable types
ms.assetid: 0bacbe72-ce15-4b14-83e1-9c14e6380c28
ms.openlocfilehash: 8ef875aee8c40f60472df52c19d1c1f2c73e95e8
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43515441"
---
# <a name="using-nullable-types-c-programming-guide"></a>Использование допускающих значение NULL типов (руководство по программированию на C#)

Типы, допускающие значение NULL, могут представлять все значения своего базового типа `T`, а также дополнительное значение [NULL](../../language-reference/keywords/null.md). Дополнительные сведения см. в разделе [Типы, допускающие значение NULL](index.md).

Вы можете ссылаться на тип, допускающий значение NULL, в любой из следующих форм: `Nullable<T>` или `T?`. Эти две формы записи являются взаимозаменяемыми.  
  
## <a name="declaration-and-assignment"></a>Назначение и объявление

Поскольку тип значения может быть неявно преобразован в соответствующий тип, допускающий значение NULL, вы назначаете значение такому типу так же, как его базовому типу значения. Вы также можете присвоить значение `null`.  Пример:
  
[!code-csharp[declare and assign](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#1)]

## <a name="examination-of-a-nullable-type-value"></a>Изучение значение типа, допускающего значение NULL

Используйте следующие свойства только для чтения, чтобы изучить экземпляр типа, допускающего значение NULL, со значением NULL и извлечь значение базового типа:  
  
- <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> указывает, имеет ли экземпляр типа, допускающего значение NULL, значение своего базового типа.
  
- <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> возвращает значение базового типа, если <xref:System.Nullable%601.HasValue%2A> имеет значение `true`. Если <xref:System.Nullable%601.HasValue%2A> имеет значение `false`, свойство <xref:System.Nullable%601.Value%2A> выдает исключение <xref:System.InvalidOperationException>.
  
В коде в следующем примере используется свойство `HasValue`, чтобы проверить, содержит ли переменная значение, перед его отображением:
  
[!code-csharp-interactive[use HasValue](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#2)]
  
Вы также можете сравнить тип, допускающий значение NULL, с `null` вместо использования свойства `HasValue`, как показано в следующем примере:  
  
[!code-csharp-interactive[use comparison with null](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#3)]

Начиная с версии C# 7.0 для проверки и получения значения типа, допускающего значение NULL, можно использовать [сопоставление шаблонов](../../pattern-matching.md).

[!code-csharp-interactive[use pattern matching](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#4)]

## <a name="conversion-from-a-nullable-type-to-an-underlying-type"></a>Преобразование из типа, допускающего значение NULL, в базовый тип

Если вам нужно присвоить значение типа, допускающего значение NULL, типу, не допускающему значение NULL, используйте [оператор объединения с NULL`??`](../../language-reference/operators/null-coalescing-operator.md), чтобы указать значение для присваивания, если значение типа, допускающего значение NULL, равно NULL (вы также можете использовать метод <xref:System.Nullable%601.GetValueOrDefault(%600)?displayProperty=nameWithType>):
  
[!code-csharp-interactive[?? operator](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#5)]

Используйте метод <xref:System.Nullable%601.GetValueOrDefault?displayProperty=nameWithType>, если значение, которое будет использоваться, когда значение типа, допускающего значение NULL, равно NULL, должно быть значением по умолчанию базового типа.
  
Вы можете явно привести тип, допускающий значение NULL, к типу, не допускающему значение NULL. Пример:  
  
[!code-csharp[explicit cast](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#6)]

Во время выполнения, если значение типа, допускающего значение NULL, равно NULL, явное приведение вызывает исключение <xref:System.InvalidOperationException>.

Тип, не допускающий значение NULL, неявно преобразуется в соответствующий тип, допускающий значение NULL.
  
## <a name="operators"></a>Операторы

Предопределенные унарные и бинарные операции, а также любые операции, определенные программистом, которые существуют для значащих типов, также можно использовать и с типами, допускающими значение null. Эти операции возвращают значение NULL, если один или оба операнда имеют значение NULL; в противном случае операция использует содержащееся значение для вычисления результата. Пример:  
  
[!code-csharp[operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#7)]
  
Для операторов отношения (`<`, `>`, `<=`, `>=`), если один или оба операнда имеют значение NULL, результатом будет `false`. Тут важно не полагать, что если какая-то операция сравнения (например, `<=`) возвращает `false`, то противоположное сравнение (`>`) обязательно вернет `true`. В следующем примере показано, что 10

- не больше и не равно значению NULL
- и не меньше, чем значение NULL.
  
[!code-csharp-interactive[relational and equality operators](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#8)]
  
В приведенном выше примере видно, что проверка на равенство двух типов, допускающих значение NULL, которые оба равны NULL, всегда даст `true`.

## <a name="boxing-and-unboxing"></a>Упаковка-преобразование и распаковка-преобразование

Тип, допускающий значение NULL, [упакован](../types/boxing-and-unboxing.md) по следующим правилам:

- Если <xref:System.Nullable%601.HasValue%2A> возвращает `false`, создается пустая ссылка.  
- Если <xref:System.Nullable%601.HasValue%2A> возвращает `true`, упаковывается значение базового типа `T`, а не экземпляр <xref:System.Nullable%601>.

Можно распаковать упакованный тип значения в соответствующий тип, допускающий значение NULL, как показано в следующем примере:

[!code-csharp-interactive[boxing and unboxing](../../../../samples/snippets/csharp/programming-guide/nullable-types/NullableTypesUsage.cs#9)]

## <a name="the-bool-type"></a>Тип bool?

Тип `bool?`, допускающий значение NULL, может содержать три разных значения: [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) и [null](../../language-reference/keywords/null.md). Тип `bool?` подобен типу Boolean в SQL. Чтобы убедиться, что результаты операторов `&` и `|` согласуются с трехзначным типом Boolean в SQL, предусмотрены следующие предопределенные операторы:

- `bool? operator &(bool? x, bool? y)`  
- `bool? operator |(bool? x, bool? y)`  
  
Семантика этих операторов определяется по следующей таблице:  
  
|x|y|x&y|x&#124;y|  
|-------|-------|---------|--------------|  
|true|true|true|true|  
|true|False|false|true|  
|true|null|null|true|  
|False|true|False|true|  
|False|False|False|False|  
|False|null|False|null|  
|null|true|null|true|  
|null|False|False|null|  
|null|null|null|null|  

Обратите внимание, что эти два оператора не следуют правилам, описанным в разделе [Операторы](#operators): результат вычисления оператора может быть отличным от NULL, даже если один из операндов имеет значение NULL.
  
## <a name="see-also"></a>См. также

- [Типы, допускающие значения NULL](index.md)  
- [Руководство по программированию на C#](../../programming-guide/index.md)  
- [What exactly does 'lifted' mean?](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/) (Что означает термин "расширенные"?)  
