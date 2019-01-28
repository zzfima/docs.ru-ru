---
title: Как выполнить Руководство по программированию на C#. Идентификация типа, допускающего значение NULL
ms.custom: seodec18
description: Узнайте, как определить, что тип допускает значение NULL или экземпляр принадлежит типу, допускающему значение NULL
ms.date: 09/24/2018
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: 33169315f8bef45aba52f0696d4acac031584817
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54582634"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a>Как выполнить Руководство по программированию на C#. Идентификация типа, допускающего значение NULL

В следующем примере, показано, как определить, представляет ли экземпляр <xref:System.Type?displayProperty=nameWithType> закрытый универсальный тип, допускающий значение null, т. е. тип <xref:System.Nullable%601?displayProperty=nameWithType> с указанным параметром типа `T`:

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

Как показано в примере, при помощи оператора [typeof](../../language-reference/keywords/typeof.md) можно создать объект <xref:System.Type?displayProperty=nameWithType>.  
  
Если вы хотите определить, принадлежит ли экземпляр к типу, допускающему значение NULL, не используйте метод <xref:System.Object.GetType%2A?displayProperty=nameWithType> для получения экземпляра <xref:System.Type> для тестирования с помощью приведенного выше кода. При вызове метода <xref:System.Object.GetType%2A?displayProperty=nameWithType> в экземпляре типа, допускающего значение NULL, экземпляр [упаковывается](using-nullable-types.md#boxing-and-unboxing) в <xref:System.Object>. Поскольку упаковка экземпляра типа, допускающего значение NULL, значение которого отлично от NULL, эквивалентна упаковке значения базового типа, <xref:System.Object.GetType%2A> возвращает объект <xref:System.Type>, представляющий базовый тип типа, допускающего значение NULL:

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

Не используйте оператор [is](../../language-reference/keywords/is.md), чтобы определить, принадлежит ли экземпляр к типу, допускающему значение NULL. Как показано в следующем примере, вы не можете отличить типы экземпляров типа, допускающего значение NULL, и его базового типа с помощью оператора `is`:

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

Чтобы определить, принадлежит ли экземпляр типу, допускающему значение NULL, можно использовать код, представленный в следующем примере:

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]
  
## <a name="see-also"></a>См. также

- [Типы, допускающие значения NULL](index.md)
- [Использование типов, допускающих значение NULL](using-nullable-types.md)
- <xref:System.Nullable.GetUnderlyingType%2A>
