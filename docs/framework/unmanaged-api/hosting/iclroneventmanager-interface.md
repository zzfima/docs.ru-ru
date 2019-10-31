---
title: Интерфейс ICLROnEventManager
ms.date: 03/30/2017
api_name:
- ICLROnEventManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager
helpviewer_keywords:
- ICLROnEventManager interface [.NET Framework hosting]
ms.assetid: 9e15a0c1-8ab6-43d0-ae28-6ec7a4edd913
topic_type:
- apiref
ms.openlocfilehash: a1b22e77fe20d5e2d755efcd7a63c8f2bdc781e9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140840"
---
# <a name="iclroneventmanager-interface"></a><span data-ttu-id="a0cc3-102">Интерфейс ICLROnEventManager</span><span class="sxs-lookup"><span data-stu-id="a0cc3-102">ICLROnEventManager Interface</span></span>
<span data-ttu-id="a0cc3-103">Предоставляет методы, позволяющие основному приложению регистрировать и отменять регистрацию обратных вызовов для событий среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-103">Provides methods that allow the host to register and unregister callbacks for common language runtime (CLR) events.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a0cc3-104">Методы</span><span class="sxs-lookup"><span data-stu-id="a0cc3-104">Methods</span></span>  
  
|<span data-ttu-id="a0cc3-105">Метод</span><span class="sxs-lookup"><span data-stu-id="a0cc3-105">Method</span></span>|<span data-ttu-id="a0cc3-106">Описание</span><span class="sxs-lookup"><span data-stu-id="a0cc3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a0cc3-107">Метод RegisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="a0cc3-107">RegisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md)|<span data-ttu-id="a0cc3-108">Регистрирует указатель обратного вызова для указанного события.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-108">Registers a callback pointer for the specified event.</span></span>|  
|[<span data-ttu-id="a0cc3-109">Метод UnregisterActionOnEvent</span><span class="sxs-lookup"><span data-stu-id="a0cc3-109">UnregisterActionOnEvent Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-unregisteractiononevent-method.md)|<span data-ttu-id="a0cc3-110">Отменяет регистрацию ранее зарегистрированного указателя обратного вызова для указанного события.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-110">Unregisters a previously registered callback pointer for the specified event.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a0cc3-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="a0cc3-111">Remarks</span></span>  
 <span data-ttu-id="a0cc3-112">Для регистрации и отмены регистрации обратных вызовов событий узел получает ссылку на `ICLROnEventManager`, вызвав метод [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a0cc3-112">To register and unregister event callbacks, the host gets a reference to `ICLROnEventManager` by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a0cc3-113">События, описанные [еклревент](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) , можно инициировать несколько раз и из разных потоков, чтобы сообщить о выгрузке или отключении среды CLR.</span><span class="sxs-lookup"><span data-stu-id="a0cc3-113">The events described by [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) can be fired more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0cc3-114">Требования</span><span class="sxs-lookup"><span data-stu-id="a0cc3-114">Requirements</span></span>  
 <span data-ttu-id="a0cc3-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0cc3-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0cc3-116">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a0cc3-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a0cc3-117">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a0cc3-117">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a0cc3-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0cc3-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0cc3-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a0cc3-119">See also</span></span>

- [<span data-ttu-id="a0cc3-120">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="a0cc3-120">EClrEvent Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [<span data-ttu-id="a0cc3-121">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="a0cc3-121">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="a0cc3-122">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="a0cc3-122">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a0cc3-123">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="a0cc3-123">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
