---
title: Этапы процесса сериализации
ms.date: 08/07/2017
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
ms.openlocfilehash: f30dd550437e6bc1030c79865bf2edd2c0efbfa9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "75741048"
---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="f8dc1-102">Этапы процесса сериализации</span><span class="sxs-lookup"><span data-stu-id="f8dc1-102">Steps in the serialization process</span></span>
<span data-ttu-id="f8dc1-103">При вызове метода <xref:System.Runtime.Serialization.Formatter.Serialize%2A> для [модуля форматирования](xref:System.Runtime.Serialization.Formatter) сериализация объекта осуществляется в следующей последовательности:</span><span class="sxs-lookup"><span data-stu-id="f8dc1-103">When the <xref:System.Runtime.Serialization.Formatter.Serialize%2A> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="f8dc1-104">Выполняется проверка для определения, имеется ли у модуля форматирования суррогатный селектор.</span><span class="sxs-lookup"><span data-stu-id="f8dc1-104">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="f8dc1-105">Если такой селектор обнаружен, выполняется проверка, обрабатывает ли суррогатный селектор объекты указанного типа.</span><span class="sxs-lookup"><span data-stu-id="f8dc1-105">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="f8dc1-106">Если селектор обрабатывает объекты такого типа, для суррогатного селектора вызывается <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="f8dc1-106">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A?displayProperty=nameWithType> is called on the surrogate selector.</span></span>

- <span data-ttu-id="f8dc1-107">Если суррогатный селектор отсутствует или не обрабатывает объекты такого типа, объект проверяется на наличие атрибута [Serializable](xref:System.SerializableAttribute).</span><span class="sxs-lookup"><span data-stu-id="f8dc1-107">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="f8dc1-108">Если объект отсутствует, возникает исключение <xref:System.Runtime.Serialization.SerializationException>.</span><span class="sxs-lookup"><span data-stu-id="f8dc1-108">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="f8dc1-109">Если объект отмечен правильным атрибутом, проверяется, реализует ли объект интерфейс <xref:System.Runtime.Serialization.ISerializable>.</span><span class="sxs-lookup"><span data-stu-id="f8dc1-109">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="f8dc1-110">Если объект такой интерфейс реализует, для него вызывается <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A>.</span><span class="sxs-lookup"><span data-stu-id="f8dc1-110">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData%2A> is called on the object.</span></span>
  
- <span data-ttu-id="f8dc1-111">Если объект не реализует интерфейс <xref:System.Runtime.Serialization.ISerializable>, используется политика сериализации по умолчанию, при которой сериализуются все поля, не отмеченные [NonSerialized](xref:System.NonSerializedAttribute).</span><span class="sxs-lookup"><span data-stu-id="f8dc1-111">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="f8dc1-112">См. также:</span><span class="sxs-lookup"><span data-stu-id="f8dc1-112">See also</span></span>

- [<span data-ttu-id="f8dc1-113">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="f8dc1-113">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="f8dc1-114">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="f8dc1-114">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
