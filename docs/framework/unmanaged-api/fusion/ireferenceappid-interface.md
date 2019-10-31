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
ms.openlocfilehash: 6f20fb2e9e026253fb02b47dfcd63cf655acc4ee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131649"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="e8fa2-102">Интерфейс IReferenceAppId</span><span class="sxs-lookup"><span data-stu-id="e8fa2-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="e8fa2-103">Представляет ссылку на уникальный идентификатор приложения в текущей области.</span><span class="sxs-lookup"><span data-stu-id="e8fa2-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e8fa2-104">Методы</span><span class="sxs-lookup"><span data-stu-id="e8fa2-104">Methods</span></span>  
  
|<span data-ttu-id="e8fa2-105">Метод</span><span class="sxs-lookup"><span data-stu-id="e8fa2-105">Method</span></span>|<span data-ttu-id="e8fa2-106">Описание</span><span class="sxs-lookup"><span data-stu-id="e8fa2-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="e8fa2-107">Возвращает указатель на строковое представление идентификатора кода для приложения, на которое ссылается эта `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="e8fa2-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="e8fa2-108">Задает идентификатор кода для приложения, на которое ссылается эта `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="e8fa2-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="e8fa2-109">Возвращает указатель интерфейса на экземпляр `IEnumReferenceIdentity`, содержащий экземпляры `IReferenceIdentity`, представляющие члены этого `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="e8fa2-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="e8fa2-110">Возвращает указатель на строковое представление идентификатора маркера для подписки на этот `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="e8fa2-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="e8fa2-111">Устанавливает идентификатор маркера для подписки на этот `IReferenceAppId` указанное строковое значение.</span><span class="sxs-lookup"><span data-stu-id="e8fa2-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e8fa2-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e8fa2-112">Requirements</span></span>  
 <span data-ttu-id="e8fa2-113">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8fa2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8fa2-114">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="e8fa2-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e8fa2-115">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8fa2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8fa2-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e8fa2-116">See also</span></span>

- [<span data-ttu-id="e8fa2-117">Интерфейсы Fusion</span><span class="sxs-lookup"><span data-stu-id="e8fa2-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="e8fa2-118">Интерфейс IEnumReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="e8fa2-118">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="e8fa2-119">Интерфейс IReferenceIdentity</span><span class="sxs-lookup"><span data-stu-id="e8fa2-119">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
