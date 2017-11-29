---
title: "Интерфейс IReferenceIdentity"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IReferenceIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IReferenceIdentity
helpviewer_keywords: IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35c6152836adf02d541bacd149ed9ac053765ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="1c1b5-102">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="1c1b5-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="1c1b5-103">Представляет ссылку на уникальную подпись объекта кода.</span><span class="sxs-lookup"><span data-stu-id="1c1b5-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1c1b5-104">Методы</span><span class="sxs-lookup"><span data-stu-id="1c1b5-104">Methods</span></span>  
  
|<span data-ttu-id="1c1b5-105">Метод</span><span class="sxs-lookup"><span data-stu-id="1c1b5-105">Method</span></span>|<span data-ttu-id="1c1b5-106">Описание</span><span class="sxs-lookup"><span data-stu-id="1c1b5-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="1c1b5-107">Получает указатель интерфейса на новый `IReferenceIdentity` экземпляр, идентичным этому `IReferenceIdentity`, за исключением изменения указанного атрибута.</span><span class="sxs-lookup"><span data-stu-id="1c1b5-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="1c1b5-108">Возвращает указатель интерфейса `IEnumIDENTITY_ATTRIBUTE` экземпляр, содержащий атрибуты, связанные с этим `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="1c1b5-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="1c1b5-109">Возвращает значение атрибута в указанное пространство имен, с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="1c1b5-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="1c1b5-110">Задает атрибут, имеющий указанное пространство имен и именем указанное значение.</span><span class="sxs-lookup"><span data-stu-id="1c1b5-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c1b5-111">Требования</span><span class="sxs-lookup"><span data-stu-id="1c1b5-111">Requirements</span></span>  
 <span data-ttu-id="1c1b5-112">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1c1b5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c1b5-113">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="1c1b5-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="1c1b5-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c1b5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c1b5-115">См. также</span><span class="sxs-lookup"><span data-stu-id="1c1b5-115">See Also</span></span>  
 [<span data-ttu-id="1c1b5-116">Фьюжн-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="1c1b5-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="1c1b5-117">Интерфейс IEnumIDENTITY_ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="1c1b5-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
