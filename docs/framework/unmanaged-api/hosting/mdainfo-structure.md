---
title: "Структура MDAInfo"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: MDAInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: MDAInfo
helpviewer_keywords: MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 53a999028f2677599598caf55e62f10721f61fe3
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="mdainfo-structure"></a><span data-ttu-id="75006-102">Структура MDAInfo</span><span class="sxs-lookup"><span data-stu-id="75006-102">MDAInfo Structure</span></span>
<span data-ttu-id="75006-103">Предоставляет подробные сведения о `Event_MDAFired` событие, которое инициирует создание управляемого помощника по отладке (MDA).</span><span class="sxs-lookup"><span data-stu-id="75006-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="75006-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="75006-104">Syntax</span></span>  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="75006-105">Участники</span><span class="sxs-lookup"><span data-stu-id="75006-105">Members</span></span>  
  
|<span data-ttu-id="75006-106">Член</span><span class="sxs-lookup"><span data-stu-id="75006-106">Member</span></span>|<span data-ttu-id="75006-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="75006-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="75006-108">Название текущего MDA.</span><span class="sxs-lookup"><span data-stu-id="75006-108">The title of the current MDA.</span></span> <span data-ttu-id="75006-109">Заголовок описывает тип ошибки, вызвавшей `Event_MDAFired` событий.</span><span class="sxs-lookup"><span data-stu-id="75006-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="75006-110">Выходное сообщение, предоставленные текущим MDA.</span><span class="sxs-lookup"><span data-stu-id="75006-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="75006-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="75006-111">Remarks</span></span>  
 <span data-ttu-id="75006-112">Создание дампов дополнительной информации о состоянии или средств отладки, в сочетании с общеязыковой среды выполнения (CLR) для выполнения задач, таких как идентификация недопустимых состояний в ядре выполнения среды выполнения управляемых помощников по отладке (MDA) модуль.</span><span class="sxs-lookup"><span data-stu-id="75006-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="75006-113">Помощники отладки управляемого кода создавать XML-сообщения о событиях, которые в противном случае сложно для перехвата исключения.</span><span class="sxs-lookup"><span data-stu-id="75006-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="75006-114">Они особенно полезны для отладки переходов между управляемым и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="75006-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="75006-115">При возникновении события, которое вызывает создание MDA, среда выполнения выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="75006-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
-   <span data-ttu-id="75006-116">Если узел не зарегистрировал [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) экземпляр путем вызова [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) получать уведомления об `Event_MDAFired` события, среда выполнения выполняет его по умолчанию поведение без размещения.</span><span class="sxs-lookup"><span data-stu-id="75006-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
-   <span data-ttu-id="75006-117">Если узел зарегистрировал обработчик этого события, среда выполнения проверяет, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="75006-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="75006-118">Если это так, среда выполнения переключается в режим отладчика.</span><span class="sxs-lookup"><span data-stu-id="75006-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="75006-119">Когда отладчик продолжает выполнение, она вызывает в узле.</span><span class="sxs-lookup"><span data-stu-id="75006-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="75006-120">Если отладчик не присоединен, среда выполнения вызывает `IActionOnCLREvent::OnEvent` и передает указатель на `MDAInfo` экземпляр как `data` параметр.</span><span class="sxs-lookup"><span data-stu-id="75006-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="75006-121">Узел можно активировать MDA и получать уведомления при активации MDA.</span><span class="sxs-lookup"><span data-stu-id="75006-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="75006-122">Это дает возможность для переопределения поведения по умолчанию и прекращения управляемого потока, вызвавшего событие, для предотвращения повреждения состояния процесса узла.</span><span class="sxs-lookup"><span data-stu-id="75006-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="75006-123">Дополнительные сведения об использовании MDA см. в разделе [Диагностика ошибок посредством управляемых помощников по отладке](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="75006-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="75006-124">Требования</span><span class="sxs-lookup"><span data-stu-id="75006-124">Requirements</span></span>  
 <span data-ttu-id="75006-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75006-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75006-126">**Заголовок:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="75006-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="75006-127">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="75006-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="75006-128">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="75006-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75006-129">См. также</span><span class="sxs-lookup"><span data-stu-id="75006-129">See Also</span></span>  
 [<span data-ttu-id="75006-130">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="75006-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [<span data-ttu-id="75006-131">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="75006-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
