---
title: "Интерфейс IActionOnCLREvent"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IActionOnCLREvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IActionOnCLREvent
helpviewer_keywords: IActionOnCLREvent interface [.NET Framework hosting]
ms.assetid: b5f9b41e-7301-429c-911f-21d5422292b3
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 4b51784f07a90faa9eeb29c18a784d4fbc2c4654
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="iactiononclrevent-interface"></a><span data-ttu-id="7f6b7-102">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="7f6b7-102">IActionOnCLREvent Interface</span></span>
<span data-ttu-id="7f6b7-103">Предоставляет [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) метод, который выполняет обратные вызовы для событий, зарегистрированных с помощью вызова [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-103">Provides the [IActionOnCLREvent::OnEvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md) method, which performs callbacks on events that have been registered by using a call to the [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) method.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7f6b7-104">Методы</span><span class="sxs-lookup"><span data-stu-id="7f6b7-104">Methods</span></span>  
  
|<span data-ttu-id="7f6b7-105">Метод</span><span class="sxs-lookup"><span data-stu-id="7f6b7-105">Method</span></span>|<span data-ttu-id="7f6b7-106">Описание:</span><span class="sxs-lookup"><span data-stu-id="7f6b7-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7f6b7-107">Метод OnEvent</span><span class="sxs-lookup"><span data-stu-id="7f6b7-107">OnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-onevent-method.md)|<span data-ttu-id="7f6b7-108">Выполняет обратный вызов для зарегистрированного события.</span><span class="sxs-lookup"><span data-stu-id="7f6b7-108">Performs a callback for a registered event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7f6b7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="7f6b7-109">Requirements</span></span>  
 <span data-ttu-id="7f6b7-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f6b7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f6b7-111">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="7f6b7-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="7f6b7-112">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7f6b7-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="7f6b7-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f6b7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f6b7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="7f6b7-114">See Also</span></span>  
 [<span data-ttu-id="7f6b7-115">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="7f6b7-115">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="7f6b7-116">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="7f6b7-116">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="7f6b7-117">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="7f6b7-117">ICLROnEventManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)  
 [<span data-ttu-id="7f6b7-118">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="7f6b7-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
