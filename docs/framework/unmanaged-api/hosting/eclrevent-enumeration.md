---
title: Перечисление EClrEvent
ms.date: 03/30/2017
api_name:
- EClrEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EClrEvent
helpviewer_keywords:
- EClrEvent enumeration [.NET Framework hosting]
ms.assetid: 7c36a7c2-75a2-4971-bc23-abf54c812154
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13d564be68d6b49a1616be97710312f33f828d48
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61628663"
---
# <a name="eclrevent-enumeration"></a><span data-ttu-id="008b9-102">Перечисление EClrEvent</span><span class="sxs-lookup"><span data-stu-id="008b9-102">EClrEvent Enumeration</span></span>
<span data-ttu-id="008b9-103">Описывает распространенные события среды выполнения (CLR) языка, для которых узел может регистрировать обратные вызовы.</span><span class="sxs-lookup"><span data-stu-id="008b9-103">Describes the common language runtime (CLR) events for which the host can register callbacks.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="008b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="008b9-104">Syntax</span></span>  
  
```  
typedef enum {  
    Event_ClrDisabled,  
    Event_DomainUnload,  
    Event_MDAFired,  
    Event_StackOverflow  
} EClrEvent;  
```  
  
## <a name="members"></a><span data-ttu-id="008b9-105">Участники</span><span class="sxs-lookup"><span data-stu-id="008b9-105">Members</span></span>  
  
|<span data-ttu-id="008b9-106">Член</span><span class="sxs-lookup"><span data-stu-id="008b9-106">Member</span></span>|<span data-ttu-id="008b9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="008b9-107">Description</span></span>|  
|------------|-----------------|  
|`Event_ClrDisabled`|<span data-ttu-id="008b9-108">Указывает Неустранимая ошибка среды CLR.</span><span class="sxs-lookup"><span data-stu-id="008b9-108">Specifies a fatal CLR error.</span></span>|  
|`Event_DomainUnload`|<span data-ttu-id="008b9-109">Указывает, выгрузку конкретной <xref:System.AppDomain>.</span><span class="sxs-lookup"><span data-stu-id="008b9-109">Specifies the unloading of a particular <xref:System.AppDomain>.</span></span>|  
|`Event_MDAFired`|<span data-ttu-id="008b9-110">Указывает, что сообщение управляемого помощника по отладке (MDA) был создан.</span><span class="sxs-lookup"><span data-stu-id="008b9-110">Specifies that a Managed Debugging Assistant (MDA) message has been generated.</span></span>|  
|`Event_StackOverflow`|<span data-ttu-id="008b9-111">Указывает, что произошла ошибка переполнения стека.</span><span class="sxs-lookup"><span data-stu-id="008b9-111">Specifies that a stack overflow error has occurred.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="008b9-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="008b9-112">Remarks</span></span>  
 <span data-ttu-id="008b9-113">Узел может регистрировать обратные вызовы для любых типов событий, описываемого `EClrEvent` , вызывая методы класса [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="008b9-113">The host can register callbacks for any of the event types described by `EClrEvent` by calling methods of the [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md) interface.</span></span> <span data-ttu-id="008b9-114">Узел получает указатель на этот интерфейс вызовом [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="008b9-114">The host gets a pointer to this interface by calling the [ICLRControl::GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) method.</span></span>  
  
 <span data-ttu-id="008b9-115">`Event_CLRDisabled` И `Event_DomainUnload` события могут вызываться несколько раз и из разных потоков, чтобы сообщить о выгрузке или отключении среды CLR.</span><span class="sxs-lookup"><span data-stu-id="008b9-115">The `Event_CLRDisabled` and `Event_DomainUnload` events can be raised more than once and from different threads to signal an unload or the disabling of the CLR.</span></span>  
  
 <span data-ttu-id="008b9-116">`Event_MDAFired` Событие инициирует создание [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) экземпляр, содержащий сведения о сообщении по отладке управляемого кода.</span><span class="sxs-lookup"><span data-stu-id="008b9-116">The `Event_MDAFired` event raises the creation of an [MDAInfo](../../../../docs/framework/unmanaged-api/hosting/mdainfo-structure.md) instance that contains the details of the MDA message.</span></span> <span data-ttu-id="008b9-117">Дополнительные сведения о помощниках MDA, см. в разделе [Диагностика ошибок посредством управляемых помощников по отладке](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="008b9-117">For more information about MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="008b9-118">Требования</span><span class="sxs-lookup"><span data-stu-id="008b9-118">Requirements</span></span>  
 <span data-ttu-id="008b9-119">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="008b9-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="008b9-120">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="008b9-120">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="008b9-121">**Библиотека:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="008b9-121">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="008b9-122">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="008b9-122">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="008b9-123">См. также</span><span class="sxs-lookup"><span data-stu-id="008b9-123">See also</span></span>

- [<span data-ttu-id="008b9-124">Интерфейс IActionOnCLREvent</span><span class="sxs-lookup"><span data-stu-id="008b9-124">IActionOnCLREvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [<span data-ttu-id="008b9-125">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="008b9-125">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="008b9-126">Размещение перечислений</span><span class="sxs-lookup"><span data-stu-id="008b9-126">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
