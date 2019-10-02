---
title: Практическое руководство. Идентификация типа значений, допускающего значение NULL (руководство по программированию на C#)
ms.custom: seodec18
description: Узнайте, как определить, что тип значений допускает значение NULL или экземпляр принадлежит типу значений, допускающему значение NULL
ms.date: 09/26/2019
helpviewer_keywords:
- nullable value types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: 15b1ffedf57648955ee5a004514841a5d140292b
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392607"
---
# <a name="how-to-identify-a-nullable-value-type-c-programming-guide"></a>Практическое руководство. Идентификация типа значений, допускающего значение NULL (руководство по программированию на C#)

В следующем примере, показано, как определить, представляет ли экземпляр <xref:System.Type?displayProperty=nameWithType> закрытый универсальный тип значений, допускающий значение NULL, т. е. тип <xref:System.Nullable%601?displayProperty=nameWithType> с указанным параметром типа `T`:

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

Как показано в примере, при помощи оператора [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) можно создать объект <xref:System.Type?displayProperty=nameWithType>.

Если вы хотите определить, принадлежит ли экземпляр к типу значений, допускающему значение NULL, не используйте метод <xref:System.Object.GetType%2A?displayProperty=nameWithType> для получения экземпляра <xref:System.Type> для тестирования с помощью приведенного выше кода. При вызове метода <xref:System.Object.GetType%2A?displayProperty=nameWithType> в экземпляре типа значений, допускающего значение NULL, экземпляр [упаковывается](using-nullable-types.md#boxing-and-unboxing) в <xref:System.Object>. Поскольку упаковка экземпляра типа значений, допускающего значение NULL, значение которого отлично от NULL, эквивалентна упаковке значения базового типа, <xref:System.Object.GetType%2A> возвращает объект <xref:System.Type>, представляющий базовый тип типа значений, допускающего значение NULL:

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

Не используйте оператор [is](../../language-reference/keywords/is.md), чтобы определить, принадлежит ли экземпляр к типу значений, допускающему значение NULL. Как показано в следующем примере, вы не можете отличить типы экземпляров типа значений, допускающего значение NULL, и его базового типа с помощью оператора `is`:

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

Чтобы определить, принадлежит ли экземпляр типу значений, допускающему значение NULL, можно использовать код, представленный в следующем примере:

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]

## <a name="see-also"></a>См. также

- [Типы значений, допускающие значение NULL](index.md)
- [Использование типов значений, допускающих значение NULL](using-nullable-types.md)
- <xref:System.Nullable.GetUnderlyingType%2A>
