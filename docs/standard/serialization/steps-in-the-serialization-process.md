---
title: "Этапы процесса сериализации"
ms.date: 08/07/2017
ms.prod: .net
ms.topic: article
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c232a76c8a000fcf4ac6c98d3f5c19e50869a362
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="7a9f4-102">Этапы процесса сериализации</span><span class="sxs-lookup"><span data-stu-id="7a9f4-102">Steps in the serialization process</span></span>
<span data-ttu-id="7a9f4-103">При вызове метода <xref:System.Runtime.Serialization.Formatter.Serialize*> для [модуля форматирования](xref:System.Runtime.Serialization.Formatter) сериализация объекта осуществляется в следующей последовательности:</span><span class="sxs-lookup"><span data-stu-id="7a9f4-103">When the <xref:System.Runtime.Serialization.Formatter.Serialize*> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="7a9f4-104">Выполняется проверка для определения, имеется ли у модуля форматирования суррогатный селектор.</span><span class="sxs-lookup"><span data-stu-id="7a9f4-104">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="7a9f4-105">Если такой селектор обнаружен, выполняется проверка, обрабатывает ли суррогатный селектор объекты указанного типа.</span><span class="sxs-lookup"><span data-stu-id="7a9f4-105">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="7a9f4-106">Если селектор обрабатывает объекты такого типа, для суррогатного селектора вызывается <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="7a9f4-106">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=nameWithType> is called on the surrogate selector.</span></span>

- <span data-ttu-id="7a9f4-107">Если суррогатный селектор отсутствует или не обрабатывает объекты такого типа, объект проверяется на наличие атрибута [Serializable](xref:System.SerializableAttribute).</span><span class="sxs-lookup"><span data-stu-id="7a9f4-107">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="7a9f4-108">Если объект отсутствует, возникает исключение <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="7a9f4-108">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="7a9f4-109">Если объект отмечен правильным атрибутом, проверяется, реализует ли объект интерфейс <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="7a9f4-109">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="7a9f4-110">Если объект такой интерфейс реализует, для него вызывается <xref:System.Runtime.Serialization.ISerializable.GetObjectData*>.</span><span class="sxs-lookup"><span data-stu-id="7a9f4-110">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*> is called on the object.</span></span>
  
- <span data-ttu-id="7a9f4-111">Если объект не реализует интерфейс <xref:System.Runtime.Serialization.ISerializable>, используется политика сериализации по умолчанию, при которой сериализуются все поля, не отмеченные [NonSerialized](xref:System.NonSerializedAttribute).</span><span class="sxs-lookup"><span data-stu-id="7a9f4-111">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="7a9f4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7a9f4-112">See Also</span></span>  
 [<span data-ttu-id="7a9f4-113">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="7a9f4-113">Binary Serialization</span></span>](binary-serialization.md)  
 [<span data-ttu-id="7a9f4-114">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="7a9f4-114">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)