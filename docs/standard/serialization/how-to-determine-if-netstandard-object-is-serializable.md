---
title: Как определить, если сериализуется объект .NET Standard
description: Показано, как определить, может ли быть сериализован типом .NET Standard во время выполнения.
ms.date: 10/20/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 196e99ab1f1a0baae53c6a1dc295b135e36fbfe0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62018766"
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="d8b6c-103">Как определить, если сериализуется объект .NET Standard</span><span class="sxs-lookup"><span data-stu-id="d8b6c-103">How to determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="d8b6c-104">.NET Standard — это спецификация, определяющая типы и члены, которые должны присутствовать на конкретных реализаций .NET, которые соответствуют этой версии стандарта.</span><span class="sxs-lookup"><span data-stu-id="d8b6c-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="d8b6c-105">Тем не менее .NET Standard не определяет ли тип является сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="d8b6c-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="d8b6c-106">Типы, определенные в библиотеку .NET Standard не отмечены <xref:System.SerializableAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="d8b6c-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="d8b6c-107">Вместо этого конкретных реализаций .NET, например .NET Framework и .NET Core, могут определять, является ли определенный тип сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="d8b6c-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="d8b6c-108">Если вы разработали библиотеку, ориентированном на .NET Standard, библиотека может использоваться любой реализации .NET, которая поддерживает .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="d8b6c-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="d8b6c-109">Это означает, что невозможно заранее известно ли определенный тип является сериализуемым; только необходимо выяснить, является ли сериализуемые во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="d8b6c-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="d8b6c-110">Можно определить, является ли объект сериализуемые во время выполнения, получая значение <xref:System.Type.IsSerializable> свойство <xref:System.Type> , представляющий тип этого объекта.</span><span class="sxs-lookup"><span data-stu-id="d8b6c-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="d8b6c-111">Следующий пример предоставляет одну реализацию.</span><span class="sxs-lookup"><span data-stu-id="d8b6c-111">The following example provides one implementation.</span></span> <span data-ttu-id="d8b6c-112">Он определяет `IsSerializable(Object)` метод расширения, который указывает ли какая-либо <xref:System.Object> экземпляр может быть сериализован.</span><span class="sxs-lookup"><span data-stu-id="d8b6c-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="d8b6c-113">Затем можно передать любой объект в метод, чтобы определить, является ли его можно сериализовать и десериализовать в текущей реализации .NET, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="d8b6c-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

## <a name="see-also"></a><span data-ttu-id="d8b6c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d8b6c-114">See also</span></span>

- [<span data-ttu-id="d8b6c-115">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="d8b6c-115">Binary serialization</span></span>](binary-serialization.md)
- <xref:System.SerializableAttribute?displayProperty=nameWithType>
- <xref:System.Type.IsSerializable?displayProperty=nameWithType>
