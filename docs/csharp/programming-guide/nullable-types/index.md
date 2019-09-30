---
title: Руководство по программированию на C#. Типы значений, допускающие значение NULL
ms.custom: seodec18
description: Сведения о типах C#, допускающих значение NULL, и их использовании
ms.date: 09/26/2019
helpviewer_keywords:
- nullable value types [C#]
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: b8b52e7fb34adf65d5c76d59811ea6dd0ab16a98
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71396217"
---
# <a name="nullable-value-types-c-programming-guide"></a>Типы значений, допускающие значение NULL (руководство по программированию на C#)

Типы значений, допускающие значение NULL, являются экземплярами структуры <xref:System.Nullable%601?displayProperty=nameWithType>. Типы значений, допускающие значение NULL, могут представлять все значения своего базового типа `T`, а также дополнительное значение [NULL](../../language-reference/keywords/null.md). Базовый тип `T` может быть любым [типом значения](../../language-reference/keywords/value-types.md), не допускающим значение NULL. `T` не может быть ссылочным типом.

> [!NOTE]
> В C# 8.0 вводится функция ссылочных типов, допускающих значение NULL. Дополнительные сведения см. в разделе [Ссылочные типы, допускающие значение NULL](../../nullable-references.md). Типы значений, допускающие значение NULL, доступны начиная с C# 2.

Например, вы можете назначить значение `null` или любое целое число от <xref:System.Int32.MinValue?displayProperty=nameWithType> до <xref:System.Int32.MaxValue?displayProperty=nameWithType> для структуры `Nullable<int>`, а также [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) или `Nullable<bool>` для `null`.

Тип значения, допускающий значение NULL, следует использовать, когда нужно представить неопределенное значение его базового типа. У логической переменной может быть только два значения: `true` и `false`. Значение "не определено" у нее отсутствует. Во многих сценариях программирования, в первую очередь при взаимодействии с базами данных, значение переменной может быть неопределенным или отсутствовать. Например, поле в базе данных может содержать значение true или false, или вообще не содержать никакого значения. В этом случае используйте тип `Nullable<bool>`.

Типы значений, допускающие значение NULL, имеют следующие характеристики.

- Типы значений, допускающие значение NULL, представляют переменные типа значения, которым может быть назначено значение `null`.

- Синтаксис `T?` является сокращением `Nullable<T>`. Эти две формы записи являются взаимозаменяемыми.

- Типу значения, допускающему значение NULL, можно присвоить значение так же, как и типу базового значения, например `int? x = 10;` или `double? d = 4.108;`. Вы также можете присвоить значение `null`: `int? x = null;`.

- Используйте доступные только для чтения свойства <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> и <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> для проверки на NULL и получения значения, как показано в следующем примере: `if (x.HasValue) y = x.Value;`

  - Свойство <xref:System.Nullable%601.HasValue%2A> возвращает `true`, если переменная содержит значение, или `false`, если она содержит `null`.

  - Свойство <xref:System.Nullable%601.Value%2A> возвращает значение, если <xref:System.Nullable%601.HasValue%2A> возвращает `true`. В противном случае возникает исключение <xref:System.InvalidOperationException>.

- Вы также можете использовать с типом значения, допускающим значение NULL, операторы `==` и `!=`, как показано в следующем примере: `if (x != null) y = x.Value;`. Если `a` и `b` равны NULL, `a == b` дает значение `true`.

- Начиная с версии C# 7.0, для проверки и получения значения типа, допускающего значение NULL, можно использовать [сопоставление шаблонов](../../pattern-matching.md#the-is-type-pattern-expression): `if (x is int valueOfX) y = valueOfX;`.

- Значение по умолчанию `T?` является экземпляром, свойство <xref:System.Nullable%601.HasValue%2A> которого возвращает `false`.

- Используйте метод <xref:System.Nullable%601.GetValueOrDefault>, чтобы вернуть либо присвоенное значение, либо значение [по умолчанию](../../language-reference/keywords/default-values-table.md) для типа базового значения, если значение типа, допускающего значение NULL, равно `null`.

- Используйте метод <xref:System.Nullable%601.GetValueOrDefault(%600)>, чтобы вернуть либо присвоенное значение, либо предоставленное значение по умолчанию, если значение типа, допускающего значение NULL, равно `null`.

- Используйте [оператор объединения со значением NULL](../../language-reference/operators/null-coalescing-operator.md), `??`, чтобы присвоить значение переменной базового типа на основе типа значения, допускающего значение NULL: `int? x = null; int y = x ?? -1;`. В указанном примере, так как `x` равно `null`, итоговое значение `y` будет равно `-1`.

- Если между двумя типами данных определено пользовательское преобразование типов, то это же преобразование можно также использовать с соответствующими типами, допускающими значение NULL.

- Нельзя создавать вложенные типы значений, допускающие значение NULL. Эта строка компилироваться не будет: `Nullable<Nullable<int>> n;`

Дополнительные сведения см. в разделах [Использование типов значений, допускающих значение NULL](using-nullable-types.md) и [Практическое руководство. Идентификация типа значения, допускающего значение NULL](how-to-identify-a-nullable-type.md).

## <a name="see-also"></a>См. также

- [Руководство по программированию на C#](../index.md)
- [?? Оператор](../../language-reference/operators/null-coalescing-operator.md)
- [Типы значения, допускающие значение NULL (Visual Basic)](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- <xref:System.Nullable%601?displayProperty=nameWithType>
- <xref:System.Nullable?displayProperty=nameWithType>
