---
title: Интерфейс IActionOnCLREvent
ms.date: 03/30/2017
api_name:
- IActionOnCLREvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IActionOnCLREvent
helpviewer_keywords:
- IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f547d1bafa37c2cbb285a5d55cef8e1a6e29d0a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54688250"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="8a28b-102">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="8a28b-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="8a28b-103">Предоставляет [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) метод, который выполняет обратные вызовы для событий, зарегистрированных с помощью вызова [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8a28b-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a28b-104">Методы</span><span class="sxs-lookup"><span data-stu-id="8a28b-104">Methods</span></span>  
  
|<span data-ttu-id="8a28b-105">Метод</span><span class="sxs-lookup"><span data-stu-id="8a28b-105">Method</span></span>|<span data-ttu-id="8a28b-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="8a28b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a28b-107">Метод OnEvent</span><span class="sxs-lookup"><span data-stu-id="8a28b-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="8a28b-108">Выполняет обратный вызов для зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="8a28b-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a28b-109">Требования</span><span class="sxs-lookup"><span data-stu-id="8a28b-109">Requirements</span></span>  
 <span data-ttu-id="8a28b-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8a28b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a28b-111">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8a28b-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8a28b-112">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8a28b-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8a28b-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a28b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a28b-114">См. также</span><span class="sxs-lookup"><span data-stu-id="8a28b-114">See also</span></span>
- [<span data-ttu-id="8a28b-115">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="8a28b-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="8a28b-116">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="8a28b-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="8a28b-117">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="8a28b-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="8a28b-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="8a28b-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
