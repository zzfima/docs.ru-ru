---
title: Интерфейс IReferenceAppId
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 25733e459423500352595d6be0eee26ef75ca7e2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59157200"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="d8575-102">Интерфейс IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="d8575-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="d8575-103">Представляет ссылку на уникальный идентификатор для приложения в текущей области.</span><span class="sxs-lookup"><span data-stu-id="d8575-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d8575-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d8575-104">Methods</span></span>  
  
|<span data-ttu-id="d8575-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d8575-105">Method</span></span>|<span data-ttu-id="d8575-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d8575-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="d8575-107">Возвращает указатель на строковое представление идентификатора кода для приложения, который ссылается этот `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="d8575-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="d8575-108">Задает идентификатор кода для приложения, который ссылается этот `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="d8575-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="d8575-109">Получает указатель интерфейса на `IEnumReferenceIdentity` содержащий экземпляр `IReferenceIdentity` экземпляры, представляющие элементов этой `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="d8575-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="d8575-110">Получает указатель на строковое представление идентификатора маркера для подписки на это `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="d8575-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="d8575-111">Задает идентификатор токена для подписки на это `IReferenceAppId` к указанному строковому значению.</span><span class="sxs-lookup"><span data-stu-id="d8575-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d8575-112">Требования</span><span class="sxs-lookup"><span data-stu-id="d8575-112">Requirements</span></span>  
 <span data-ttu-id="d8575-113">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d8575-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d8575-114">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="d8575-114">**Header:** Isolation.h</span></span>  
  
 **<span data-ttu-id="d8575-115">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="d8575-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8575-116">См. также</span><span class="sxs-lookup"><span data-stu-id="d8575-116">See also</span></span>

- [<span data-ttu-id="d8575-117">Fusion-интерфейсы</span><span class="sxs-lookup"><span data-stu-id="d8575-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="d8575-118">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="d8575-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [<span data-ttu-id="d8575-119">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="d8575-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
