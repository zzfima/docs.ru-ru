---
title: Типы, допускающие значение NULL (Руководство по программированию на C#)
description: Сведения о типах C#, допускающих значение NULL, и их использовании
ms.date: 07/30/2018
helpviewer_keywords:
- nullable types [C#]
- C# language, nullable types
- types [C#], nullable
ms.assetid: e473cb01-28ca-42be-9cea-f717055d72c6
ms.openlocfilehash: 2af0704abcad00c75a5d40bfe2d0523d07ee6a3f
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2018
ms.locfileid: "44205592"
---
# <a name="nullable-types-c-programming-guide"></a>Типы, допускающие значение NULL (Руководство по программированию на C#)

Типы, допускающие значения NULL, являются экземплярами структуры <xref:System.Nullable%601?displayProperty=nameWithType>. Типы, допускающие значение NULL, могут представлять все значения своего базового типа `T`, а также дополнительное значение [NULL](../../language-reference/keywords/null.md). Базовый тип `T` может быть любым [типом значения](../../language-reference/keywords/value-types.md), не допускающим значение NULL. `T` не может быть ссылочным типом.

Например, вы можете назначить значение `null` или любое целое число от <xref:System.Int32.MinValue?displayProperty=nameWithType> до <xref:System.Int32.MaxValue?displayProperty=nameWithType> для структуры `Nullable<int>`, а также [true](../../language-reference/keywords/true-literal.md), [false](../../language-reference/keywords/false-literal.md) или `Nullable<bool>` для `null`.

Тип, допускающий значение NULL, следует использовать, когда нужно представить неопределенное значение его базового типа. У логической переменной может быть только два значения: true (истина) и false (ложь). Значение "не определено" у нее отсутствует. Во многих сценариях программирования, в первую очередь при взаимодействии с базами данных, значение переменной может быть неопределенным или отсутствовать. Например, поле в базе данных может содержать значение true или false, или вообще не содержать никакого значения. В этом случае используйте тип `Nullable<bool>`.

Типы, допускающие значения NULL, имеют следующие характеристики.
  
- Типы, допускающие значение NULL, представляют переменные типа значения, которым может быть присвоено значение `null`. Нельзя создать тип, допускающий значение NULL, на основе ссылочного типа. (Ссылочные типы всегда поддерживают значение `null`.)  
  
- Синтаксис `T?` является сокращением `Nullable<T>`. Эти две формы записи являются взаимозаменяемыми.  
  
- Типу, допускающему значение NULL, можно присвоить значение так же, как и типу базового значения, например `int? x = 10;` или `double? d = 4.108;`. Вы также можете присвоить значение `null`: `int? x = null;`.  
  
- Используйте доступные только для чтения свойства <xref:System.Nullable%601.HasValue%2A?displayProperty=nameWithType> и <xref:System.Nullable%601.Value%2A?displayProperty=nameWithType> для проверки на NULL и получения значения, как показано в следующем примере: `if (x.HasValue) y = x.Value;`  
  
  - Свойство <xref:System.Nullable%601.HasValue%2A> возвращает `true`, если переменная содержит значение, или `false`, если она содержит `null`.
  
  - Свойство <xref:System.Nullable%601.Value%2A> возвращает значение, если <xref:System.Nullable%601.HasValue%2A> возвращает `true`. В противном случае возникает исключение <xref:System.InvalidOperationException>.  
  
- Вы также можете использовать с типом, допускающим значение NULL, операторы `==` и `!=`, как показано в следующем примере: `if (x != null) y = x.Value;`. Если `a` и `b` равны NULL, `a == b` дает значение `true`.  

- Начиная с версии C# 7.0, для проверки и получения значения типа, допускающего значение NULL, можно использовать [сопоставление шаблонов](../../pattern-matching.md#the-is-type-pattern-expression): `if (x is int valueOfX) y = valueOfX;`.
  
- Значение по умолчанию `T?` является экземпляром, свойство <xref:System.Nullable%601.HasValue%2A> которого возвращает `false`.  

- Используйте метод <xref:System.Nullable%601.GetValueOrDefault>, чтобы вернуть либо присвоенное значение, либо значение [по умолчанию](../../language-reference/keywords/default-values-table.md) для типа базового значения, если значение типа, допускающего значение NULL, равно `null`.  

- Используйте метод <xref:System.Nullable%601.GetValueOrDefault(%600)>, чтобы вернуть либо присвоенное значение, либо предоставленное значение по умолчанию, если значение типа, допускающего значение NULL, равно `null`.
  
- Используйте [оператор объединения со значением NULL](../../language-reference/operators/null-coalescing-operator.md), `??`, чтобы присвоить значение базовому типу на основе значения типа, допускающего значение NULL: `int? x = null; int y = x ?? -1;`. В указанном примере, так как `x` равно NULL, итоговое значение `y` будет равно `-1`.

- Если между двумя типами данных определено пользовательское преобразование типов, то это же преобразование можно также использовать с версиями этих типов, допускающими значение null.
  
- Нельзя создавать вложенные типы, допускающие значение NULL. Эта строка компилироваться не будет: `Nullable<Nullable<int>> n;`  

Дополнительные сведения см. в разделах [Использование типов, допускающих значение NULL](using-nullable-types.md) и [Практическое руководство. Идентификация типа, допускающего значение NULL](how-to-identify-a-nullable-type.md).
  
## <a name="see-also"></a>См. также

- <xref:System.Nullable%601?displayProperty=nameWithType>  
- <xref:System.Nullable?displayProperty=nameWithType>  
- [?? Оператор](../../language-reference/operators/null-coalescing-operator.md)  
- [Руководство по программированию на C#](../index.md)  
- [Руководство по языку C#](../../index.md)  
- [Справочник по C#](../../language-reference/index.md)  
- [Типы значения, допускающие значение NULL (Visual Basic)](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
