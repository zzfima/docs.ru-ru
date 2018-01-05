---
title: "Как: определить, является ли сериализуемый объект .NET Standard"
description: "Показано, как определить, можно ли сериализовать .NET стандартного типа во время выполнения."
ms.custom: 
ms.date: 10/20/2017
ms.prod: .net
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- serializing objects
- objects, serializing steps
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 7c44e350ad4e561f03bf6c598172058a0a9ca41e
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-determine-if-a-net-standard-object-is-serializable"></a><span data-ttu-id="e8f49-103">Как: определить, является ли сериализуемый объект .NET Standard</span><span class="sxs-lookup"><span data-stu-id="e8f49-103">How to: Determine if a .NET Standard object is serializable</span></span>

<span data-ttu-id="e8f49-104">В стандарте .NET является спецификация, определяющая типы и члены, которые должны присутствовать на определенных реализаций .NET, которые соответствуют этой версии стандарта.</span><span class="sxs-lookup"><span data-stu-id="e8f49-104">The .NET Standard is a specification that defines the types and members that must be present on specific .NET implementations that conform to that version of the standard.</span></span> <span data-ttu-id="e8f49-105">Однако .NET Standard не определяет ли тип является сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="e8f49-105">However, the .NET Standard does not define whether a type is serializable.</span></span> <span data-ttu-id="e8f49-106">Типы, определенные в стандартной библиотеке .NET не отмечены ни <xref:System.SerializableAttribute> атрибута.</span><span class="sxs-lookup"><span data-stu-id="e8f49-106">The types defined in the .NET Standard Library are not marked with the <xref:System.SerializableAttribute> attribute.</span></span> <span data-ttu-id="e8f49-107">Вместо этого определенных реализаций .NET, такие как .NET Framework и .NET Core, могут определить, является ли определенный тип сериализуемым.</span><span class="sxs-lookup"><span data-stu-id="e8f49-107">Instead, specific .NET implementations, such as the .NET Framework and .NET Core, are free to determine whether a particular type is serializable.</span></span> 

<span data-ttu-id="e8f49-108">Если вы разработали библиотеку, ориентированном .NET Standard, библиотеки могут использоваться реализацией .NET, которая поддерживает .NET Standard.</span><span class="sxs-lookup"><span data-stu-id="e8f49-108">If you've developed a library that targets the .NET Standard, your library can be consumed by any .NET implementation that supports the .NET Standard.</span></span> <span data-ttu-id="e8f49-109">Это означает, что вы не может заранее знаете ли определенный тип является сериализуемым; может только определить, является ли он поддерживает сериализацию во время выполнения.</span><span class="sxs-lookup"><span data-stu-id="e8f49-109">This means that you cannot know in advance whether a particular type is serializable; you can only determine whether it is serializable at run time.</span></span>

<span data-ttu-id="e8f49-110">Можно определить, является ли объект сериализуемые во время выполнения, получая значение <xref:System.Type.IsSerializable> свойство <xref:System.Type> , представляющий тип этого объекта.</span><span class="sxs-lookup"><span data-stu-id="e8f49-110">You can determine whether an object is serializable at runtime by retrieving the value of the <xref:System.Type.IsSerializable> property of a <xref:System.Type> object that represents that object's type.</span></span> <span data-ttu-id="e8f49-111">Следующий пример предоставляет одну реализацию.</span><span class="sxs-lookup"><span data-stu-id="e8f49-111">The following example provides one implementation.</span></span> <span data-ttu-id="e8f49-112">Он определяет `IsSerializable(Object)` метод расширения, который указывает ли какая-либо <xref:System.Object> экземпляр может быть сериализован.</span><span class="sxs-lookup"><span data-stu-id="e8f49-112">It defines an `IsSerializable(Object)` extension method that indicates whether any <xref:System.Object> instance can be serialized.</span></span>

[!code-csharp[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#2)]
[!code-vb[is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/library.vb#2)]

<span data-ttu-id="e8f49-113">Затем можно передать любой объект в метод, чтобы определить ли его можно сериализовать и десериализовать в текущей реализации .NET, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="e8f49-113">You can then pass any object to the method to determine whether it can be serialized and deserialized on the current .NET implementation, as the following example shows:</span></span>

[!code-csharp[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/csharp/program.cs#1)]
[!code-vb[test-is-a-type-serializable](~/samples/snippets/standard/serialization/is-serializable/vb/program.vb#1)]

# <a name="see-also"></a><span data-ttu-id="e8f49-114">См. также</span><span class="sxs-lookup"><span data-stu-id="e8f49-114">See also</span></span>

<span data-ttu-id="e8f49-115">[Двоичная сериализация](binary-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="e8f49-115">[Binary serialization](binary-serialization.md) </span></span>  
<span data-ttu-id="e8f49-116"><xref:System.SerializableAttribute?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="e8f49-116"><xref:System.SerializableAttribute?displayProperty=fullName></span></span>    
<xref:System.Type.IsSerializable?displayProperty=nameWithType>   
