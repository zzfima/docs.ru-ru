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
ms.openlocfilehash: 522ed80f161f114af25e1fa7ad041c8238073d6f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796368"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="bf009-102">Интерфейс IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="bf009-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="bf009-103">Представляет ссылку на уникальный идентификатор приложения в текущей области.</span><span class="sxs-lookup"><span data-stu-id="bf009-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="bf009-104">Методы</span><span class="sxs-lookup"><span data-stu-id="bf009-104">Methods</span></span>  
  
|<span data-ttu-id="bf009-105">Метод</span><span class="sxs-lookup"><span data-stu-id="bf009-105">Method</span></span>|<span data-ttu-id="bf009-106">Описание</span><span class="sxs-lookup"><span data-stu-id="bf009-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="bf009-107">Возвращает указатель на строковое представление идентификатора кода для приложения, на которое ссылается this `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="bf009-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="bf009-108">Задает идентификатор кода для приложения, на которое ссылается this `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="bf009-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="bf009-109">Возвращает указатель интерфейса на `IEnumReferenceIdentity` экземпляр, `IReferenceIdentity` содержащий экземпляры, представляющие члены этого `IReferenceAppId`объекта.</span><span class="sxs-lookup"><span data-stu-id="bf009-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="bf009-110">Возвращает указатель на строковое представление идентификатора маркера для подписки на этот `IReferenceAppId`объект.</span><span class="sxs-lookup"><span data-stu-id="bf009-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="bf009-111">Задает для идентификатора маркера подписки это `IReferenceAppId` значение в указанном строковом значении.</span><span class="sxs-lookup"><span data-stu-id="bf009-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bf009-112">Требования</span><span class="sxs-lookup"><span data-stu-id="bf009-112">Requirements</span></span>  
 <span data-ttu-id="bf009-113">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf009-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf009-114">**Заголовок.** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="bf009-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="bf009-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf009-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf009-116">См. также</span><span class="sxs-lookup"><span data-stu-id="bf009-116">See also</span></span>

- [<span data-ttu-id="bf009-117">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="bf009-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="bf009-118">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="bf009-118">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="bf009-119">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="bf009-119">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
