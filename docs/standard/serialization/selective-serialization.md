---
title: Выборочная сериализация
ms.date: 08/07/2017
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
ms.openlocfilehash: cc5d7964d5f3268f08721593fefc07e3eff853ca
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159602"
---
# <a name="selective-serialization"></a><span data-ttu-id="84b53-102">Выборочная сериализация</span><span class="sxs-lookup"><span data-stu-id="84b53-102">Selective serialization</span></span>
<span data-ttu-id="84b53-103">Класс часто содержит поля, которые не должны быть сериализованы.</span><span class="sxs-lookup"><span data-stu-id="84b53-103">A class often contains fields that shouldn't be serialized.</span></span> <span data-ttu-id="84b53-104">Например, рассмотрим класс, содержащий идентификатор потока в переменной-члене.</span><span class="sxs-lookup"><span data-stu-id="84b53-104">For example, assume a class stores a thread ID in a member variable.</span></span> <span data-ttu-id="84b53-105">При десериализации класса поток, в котором хранился идентификатор во время сериализации класса, может уже не использоваться, поэтому сериализация такого значения не имеет смысла.</span><span class="sxs-lookup"><span data-stu-id="84b53-105">When the class is deserialized, the thread stored the ID for when the class was serialized might no longer be running; so serializing this value doesn't make sense.</span></span> <span data-ttu-id="84b53-106">Предотвратить сериализацию переменных-членов можно, маркировав их атрибутом [NonSerialized](xref:System.NonSerializedAttribute) следующим образом.</span><span class="sxs-lookup"><span data-stu-id="84b53-106">You can prevent member variables from being serialized by marking them with the [NonSerialized](xref:System.NonSerializedAttribute) attribute as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

<span data-ttu-id="84b53-107">Для объекта, содержащего важные для обеспечения безопасности данные, следует, если это возможно, запретить сериализацию.</span><span class="sxs-lookup"><span data-stu-id="84b53-107">If possible, make an object that could contain security-sensitive data nonserializable.</span></span> <span data-ttu-id="84b53-108">Если же для данного объекта сериализация необходима, примените к соответствующим полям с важной информацией атрибут `NonSerialized`.</span><span class="sxs-lookup"><span data-stu-id="84b53-108">If the object must be serialized, apply the `NonSerialized` attribute to specific fields that store sensitive data.</span></span> <span data-ttu-id="84b53-109">Учтите, что если не исключить эти поля из сериализации, хранимые в них данные предоставляются любому коду с разрешением сериализации.</span><span class="sxs-lookup"><span data-stu-id="84b53-109">If you don't exclude these fields from serialization, be aware that the data they store are exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="84b53-110">Дополнительные сведения о написании безопасного кода сериализации см. в разделе [Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="84b53-110">For more information about writing secure serialization code, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="84b53-111">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="84b53-111">See also</span></span>

- [<span data-ttu-id="84b53-112">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="84b53-112">Binary Serialization</span></span>](binary-serialization.md)
- [<span data-ttu-id="84b53-113">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="84b53-113">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)
- [<span data-ttu-id="84b53-114">Безопасность и сериализация</span><span class="sxs-lookup"><span data-stu-id="84b53-114">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)
