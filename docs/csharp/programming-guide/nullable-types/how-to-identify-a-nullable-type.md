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
# <a name="how-to-identify-a-nullable-value-type-c-programming-guide"></a><span data-ttu-id="b187e-103">Практическое руководство. Идентификация типа значений, допускающего значение NULL (руководство по программированию на C#)</span><span class="sxs-lookup"><span data-stu-id="b187e-103">How to: identify a nullable value type (C# Programming Guide)</span></span>

<span data-ttu-id="b187e-104">В следующем примере, показано, как определить, представляет ли экземпляр <xref:System.Type?displayProperty=nameWithType> закрытый универсальный тип значений, допускающий значение NULL, т. е. тип <xref:System.Nullable%601?displayProperty=nameWithType> с указанным параметром типа `T`:</span><span class="sxs-lookup"><span data-stu-id="b187e-104">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a closed generic nullable value type, that is, the <xref:System.Nullable%601?displayProperty=nameWithType> type with a specified type parameter `T`:</span></span>

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

<span data-ttu-id="b187e-105">Как показано в примере, при помощи оператора [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) можно создать объект <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b187e-105">As the example shows, you use the [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) operator to create a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="b187e-106">Если вы хотите определить, принадлежит ли экземпляр к типу значений, допускающему значение NULL, не используйте метод <xref:System.Object.GetType%2A?displayProperty=nameWithType> для получения экземпляра <xref:System.Type> для тестирования с помощью приведенного выше кода.</span><span class="sxs-lookup"><span data-stu-id="b187e-106">If you want to determine whether an instance is of a nullable value type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="b187e-107">При вызове метода <xref:System.Object.GetType%2A?displayProperty=nameWithType> в экземпляре типа значений, допускающего значение NULL, экземпляр [упаковывается](using-nullable-types.md#boxing-and-unboxing) в <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="b187e-107">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable value type, the instance is [boxed](using-nullable-types.md#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="b187e-108">Поскольку упаковка экземпляра типа значений, допускающего значение NULL, значение которого отлично от NULL, эквивалентна упаковке значения базового типа, <xref:System.Object.GetType%2A> возвращает объект <xref:System.Type>, представляющий базовый тип типа значений, допускающего значение NULL:</span><span class="sxs-lookup"><span data-stu-id="b187e-108">As boxing of a non-null instance of a nullable value type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> object that represents the underlying type of a nullable value type:</span></span>

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

<span data-ttu-id="b187e-109">Не используйте оператор [is](../../language-reference/keywords/is.md), чтобы определить, принадлежит ли экземпляр к типу значений, допускающему значение NULL.</span><span class="sxs-lookup"><span data-stu-id="b187e-109">Don't use the [is](../../language-reference/keywords/is.md) operator to determine whether an instance is of a nullable value type.</span></span> <span data-ttu-id="b187e-110">Как показано в следующем примере, вы не можете отличить типы экземпляров типа значений, допускающего значение NULL, и его базового типа с помощью оператора `is`:</span><span class="sxs-lookup"><span data-stu-id="b187e-110">As the following example shows, you cannot distinguish types of instances of a nullable value type and its underlying type with using the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

<span data-ttu-id="b187e-111">Чтобы определить, принадлежит ли экземпляр типу значений, допускающему значение NULL, можно использовать код, представленный в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="b187e-111">You can use the code presented in the following example to determine whether an instance is of a nullable value type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]

## <a name="see-also"></a><span data-ttu-id="b187e-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b187e-112">See also</span></span>

- [<span data-ttu-id="b187e-113">Типы значений, допускающие значение NULL</span><span class="sxs-lookup"><span data-stu-id="b187e-113">Nullable value types</span></span>](index.md)
- [<span data-ttu-id="b187e-114">Использование типов значений, допускающих значение NULL</span><span class="sxs-lookup"><span data-stu-id="b187e-114">Using nullable value types</span></span>](using-nullable-types.md)
- <xref:System.Nullable.GetUnderlyingType%2A>
