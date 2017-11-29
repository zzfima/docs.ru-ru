---
title: "Интерфейс ICLROnEventManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLROnEventManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLROnEventManager
helpviewer_keywords: ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d3f792af3e01d476768961928272cb6166a144f9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="d1231-102">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="d1231-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="d1231-103">Предоставляет методы, позволяющие основному приложению регистрировать и отменять регистрацию обратные вызовы для событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d1231-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d1231-104">Методы</span><span class="sxs-lookup"><span data-stu-id="d1231-104">Methods</span></span>  
  
|<span data-ttu-id="d1231-105">Метод</span><span class="sxs-lookup"><span data-stu-id="d1231-105">Method</span></span>|<span data-ttu-id="d1231-106">Описание</span><span class="sxs-lookup"><span data-stu-id="d1231-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d1231-107">RegisterActionOnEvent-метод</span><span class="sxs-lookup"><span data-stu-id="d1231-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="d1231-108">Регистрирует указатель обратного вызова для указанного события.</span><span class="sxs-lookup"><span data-stu-id="d1231-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="d1231-109">Unregisteractiononevent-метод</span><span class="sxs-lookup"><span data-stu-id="d1231-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="d1231-110">Отменяет регистрацию ранее зарегистрированного обратного вызова указатель для указанного события.</span><span class="sxs-lookup"><span data-stu-id="d1231-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d1231-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="d1231-111">Remarks</span></span>  
 <span data-ttu-id="d1231-112">Для регистрации и отмены регистрации обратных вызовов событий, основное приложение получает ссылку на `ICLROnEventManager` путем вызова [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="d1231-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d1231-113">События, описанные объектом [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) может вызываться несколько раз и из разных потоков, чтобы сообщить о выгрузке или отключении среды CLR.</span><span class="sxs-lookup"><span data-stu-id="d1231-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d1231-114">Требования</span><span class="sxs-lookup"><span data-stu-id="d1231-114">Requirements</span></span>  
 <span data-ttu-id="d1231-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d1231-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d1231-116">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d1231-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d1231-117">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d1231-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d1231-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d1231-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1231-119">См. также</span><span class="sxs-lookup"><span data-stu-id="d1231-119">See Also</span></span>  
 [<span data-ttu-id="d1231-120">EClrEvent-перечисление</span><span class="sxs-lookup"><span data-stu-id="d1231-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)  
 [<span data-ttu-id="d1231-121">IActionOnCLREvent-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d1231-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)  
 [<span data-ttu-id="d1231-122">ICLRControl-интерфейс</span><span class="sxs-lookup"><span data-stu-id="d1231-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="d1231-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="d1231-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
