---
title: "Выборочная сериализация"
ms.date: 08/07/2017
ms.prod: .net
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cb4391e0f78534146ee253f88ad2ae94aa1a11f8
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/23/2017
---
# <a name="selective-serialization"></a><span data-ttu-id="d27bf-102">Выборочная сериализация</span><span class="sxs-lookup"><span data-stu-id="d27bf-102">Selective serialization</span></span>
<span data-ttu-id="d27bf-103">Класс часто содержит поля, которые не должны быть сериализованы.</span><span class="sxs-lookup"><span data-stu-id="d27bf-103">A class often contains fields that shouldn't be serialized.</span></span> <span data-ttu-id="d27bf-104">Например, рассмотрим класс, содержащий идентификатор потока в переменной-члене.</span><span class="sxs-lookup"><span data-stu-id="d27bf-104">For example, assume a class stores a thread ID in a member variable.</span></span> <span data-ttu-id="d27bf-105">При десериализации класса поток, в котором хранился идентификатор во время сериализации класса, может уже не использоваться, поэтому сериализация такого значения не имеет смысла.</span><span class="sxs-lookup"><span data-stu-id="d27bf-105">When the class is deserialized, the thread stored the ID for when the class was serialized might no longer be running; so serializing this value doesn't make sense.</span></span> <span data-ttu-id="d27bf-106">Предотвратить сериализацию переменных-членов можно, маркировав их атрибутом [NonSerialized](xref:System.NonSerializedAttribute) следующим образом.</span><span class="sxs-lookup"><span data-stu-id="d27bf-106">You can prevent member variables from being serialized by marking them with the [NonSerialized](xref:System.NonSerializedAttribute) attribute as follows.</span></span>  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

<span data-ttu-id="d27bf-107">Для объекта, содержащего важные для обеспечения безопасности данные, следует, если это возможно, запретить сериализацию.</span><span class="sxs-lookup"><span data-stu-id="d27bf-107">If possible, make an object that could contain security-sensitive data nonserializable.</span></span> <span data-ttu-id="d27bf-108">Если же для данного объекта сериализация необходима, примените к соответствующим полям с важной информацией атрибут `NonSerialized`.</span><span class="sxs-lookup"><span data-stu-id="d27bf-108">If the object must be serialized, apply the `NonSerialized` attribute to specific fields that store sensitive data.</span></span> <span data-ttu-id="d27bf-109">Учтите, что если не исключить эти поля из сериализации, хранимые в них данные предоставляются любому коду с разрешением сериализации.</span><span class="sxs-lookup"><span data-stu-id="d27bf-109">If you don't exclude these fields from serialization, be aware that the data they store are exposed to any code that has permission to serialize.</span></span> <span data-ttu-id="d27bf-110">Дополнительные сведения о написании безопасного кода сериализации см. в разделе [Безопасность и сериализация](../../../docs/framework/misc/security-and-serialization.md).</span><span class="sxs-lookup"><span data-stu-id="d27bf-110">For more information about writing secure serialization code, see [Security and Serialization](../../../docs/framework/misc/security-and-serialization.md).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="d27bf-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d27bf-111">See also</span></span>  
 [<span data-ttu-id="d27bf-112">Двоичная сериализация</span><span class="sxs-lookup"><span data-stu-id="d27bf-112">Binary Serialization</span></span>](binary-serialization.md)  
 [<span data-ttu-id="d27bf-113">Сериализация XML и SOAP</span><span class="sxs-lookup"><span data-stu-id="d27bf-113">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)  
 [<span data-ttu-id="d27bf-114">Безопасность и сериализация</span><span class="sxs-lookup"><span data-stu-id="d27bf-114">Security and Serialization</span></span>](../../../docs/framework/misc/security-and-serialization.md)