---
title: Как определить, является ли объект .NET Standard сериализуемым
description: Показывает, как определить, можно ли сериализовать тип .NET Standard во время выполнения.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
ms.openlocfilehash: 4037dee36aeb619eb2757016904fd877158e57cf
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159901"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="c76b8-103">Как определить, является ли объект .NET Standard сериализуемым</span><span class="sxs-lookup"><span data-stu-id="c76b8-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="c76b8-104">.NET Standard — это спецификация, определяющая типы и члены, которые должны присутствовать в конкретных реализациях .NET, соответствующих этой версии стандарта.</span><span class="sxs-lookup"><span data-stu-id="c76b8-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="c76b8-105">Однако .NET Standard не определяет, является ли тип сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="c76b8-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="c76b8-106">Типы, определенные в библиотеке .NET Standard, не помечены атрибутом <xref:System.SerializableAttribute>.</span><span class="sxs-lookup"><span data-stu-id="c76b8-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="c76b8-107">Вместо этого определенные реализации .NET, такие как .NET Framework и .NET Core, могут быть свободны, чтобы определить, является ли конкретный тип сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="c76b8-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span>

<span data-ttu-id="c76b8-108">Если вы разработали библиотеку, предназначенную для .NET Standard, ваша библиотека может использоваться любой реализацией .NET, поддерживающей .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="c76b8-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="c76b8-109">Это означает, что невозможно заранее определить, является ли конкретный тип сериализуемым. можно определить, является ли он сериализуемым во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="c76b8-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="c76b8-110">Можно определить, является ли объект сериализуемым во время выполнения, извлекая значение свойства <xref:System.Type.IsSerializable> объекта <xref:System.Type>, который представляет тип этого объекта.</span><span class="sxs-lookup"><span data-stu-id="c76b8-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="c76b8-111">В следующем примере показана одна реализация.</span><span class="sxs-lookup"><span data-stu-id="c76b8-111">The following example provides one implementation.</span></span> <span data-ttu-id="c76b8-112">Он определяет метод расширения `IsSerializable(Object)`, который указывает, можно ли сериализовать любой экземпляр <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="c76b8-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="c76b8-113">Затем можно передать любой объект в метод, чтобы определить, может ли он быть сериализован и десериализован в текущей реализации .NET, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="c76b8-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="c76b8-114">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="c76b8-114">See also</span></span>

- [<span data-ttu-id="c76b8-115">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="c76b8-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
