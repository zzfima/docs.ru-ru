---
title: "Интерфейс IReferenceAppId"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 22ac2d75632b3c670d7c185cbbf5081732dcaffc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="84f7c-102">Интерфейс IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="84f7c-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="84f7c-103">Представляет ссылку на уникальный идентификатор для приложения в текущей области.</span><span class="sxs-lookup"><span data-stu-id="84f7c-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="84f7c-104">Методы</span><span class="sxs-lookup"><span data-stu-id="84f7c-104">Methods</span></span>  
  
|<span data-ttu-id="84f7c-105">Метод</span><span class="sxs-lookup"><span data-stu-id="84f7c-105">Method</span></span>|<span data-ttu-id="84f7c-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="84f7c-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="84f7c-107">Возвращает указатель на строковое представление идентификатора кода для приложения, упоминаемой в этом `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="84f7c-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="84f7c-108">Задает идентификатор кода для приложения, упоминаемой в этом `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="84f7c-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="84f7c-109">Возвращает указатель интерфейса `IEnumReferenceIdentity` содержащий экземпляр `IReferenceIdentity` экземпляры, которые представляют элементы этого `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="84f7c-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="84f7c-110">Получает указатель на строковое представление идентификатора маркера для подписки на это `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="84f7c-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="84f7c-111">Задает идентификатор маркера для подписки на этот `IReferenceAppId` заданным строковым значением.</span><span class="sxs-lookup"><span data-stu-id="84f7c-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="84f7c-112">Требования</span><span class="sxs-lookup"><span data-stu-id="84f7c-112">Requirements</span></span>  
 <span data-ttu-id="84f7c-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="84f7c-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="84f7c-114">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="84f7c-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="84f7c-115">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="84f7c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84f7c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="84f7c-116">See Also</span></span>  
 [<span data-ttu-id="84f7c-117">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="84f7c-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="84f7c-118">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="84f7c-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [<span data-ttu-id="84f7c-119">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="84f7c-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
