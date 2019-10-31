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
ms.openlocfilehash: 9277fe2c241ce4f502339de826dccd08a2ce8055
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126960"
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="9a0db-102">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="9a0db-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="9a0db-103">Предоставляет метод [иактиононклревент:: oneven](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) , который выполняет обратные вызовы для событий, зарегистрированных с помощью вызова метода [ICLROnEventManager:: регистерактиононевент](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9a0db-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="9a0db-104">Методы</span><span class="sxs-lookup"><span data-stu-id="9a0db-104">Methods</span></span>  
  
|<span data-ttu-id="9a0db-105">Метод</span><span class="sxs-lookup"><span data-stu-id="9a0db-105">Method</span></span>|<span data-ttu-id="9a0db-106">Описание</span><span class="sxs-lookup"><span data-stu-id="9a0db-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="9a0db-107">Метод OnEvent</span><span class="sxs-lookup"><span data-stu-id="9a0db-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="9a0db-108">Выполняет обратный вызов для зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="9a0db-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9a0db-109">Требования</span><span class="sxs-lookup"><span data-stu-id="9a0db-109">Requirements</span></span>  
 <span data-ttu-id="9a0db-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9a0db-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a0db-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="9a0db-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9a0db-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="9a0db-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9a0db-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a0db-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a0db-114">См. также</span><span class="sxs-lookup"><span data-stu-id="9a0db-114">See also</span></span>

- [<span data-ttu-id="9a0db-115">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="9a0db-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="9a0db-116">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="9a0db-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="9a0db-117">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="9a0db-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
- [<span data-ttu-id="9a0db-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="9a0db-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
