---
title: Структура MDAInfo
ms.date: 03/30/2017
api_name:
- MDAInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- MDAInfo
helpviewer_keywords:
- MDAInfo structure [.NET Framework hosting]
ms.assetid: fb8c14f7-d461-43d1-8b47-adb6723b9b93
topic_type:
- apiref
ms.openlocfilehash: 9a2f513d40d722f1b0aad823ac7c0d93bda5615f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73123263"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="18ee9-102">Структура MDAInfo</span><span class="sxs-lookup"><span data-stu-id="18ee9-102">MDAInfo Structure</span></span>
<span data-ttu-id="18ee9-103">Предоставляет сведения о событии `Event_MDAFired`, которое активирует создание помощника по отладке управляемого кода (MDA).</span><span class="sxs-lookup"><span data-stu-id="18ee9-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18ee9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="18ee9-104">Syntax</span></span>  
  
```cpp  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="18ee9-105">Члены</span><span class="sxs-lookup"><span data-stu-id="18ee9-105">Members</span></span>  
  
|<span data-ttu-id="18ee9-106">Член</span><span class="sxs-lookup"><span data-stu-id="18ee9-106">Member</span></span>|<span data-ttu-id="18ee9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="18ee9-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="18ee9-108">Заголовок текущего MDA.</span><span class="sxs-lookup"><span data-stu-id="18ee9-108">The title of the current MDA.</span></span> <span data-ttu-id="18ee9-109">Заголовок описывает тип сбоя, вызвавшего событие `Event_MDAFired`.</span><span class="sxs-lookup"><span data-stu-id="18ee9-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="18ee9-110">Выходное сообщение, предоставленное текущим MDA.</span><span class="sxs-lookup"><span data-stu-id="18ee9-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18ee9-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="18ee9-111">Remarks</span></span>  
 <span data-ttu-id="18ee9-112">Управляемые помощники по отладке (MDA) — это вспомогательные средства отладки, которые работают совместно со средой CLR для выполнения таких задач, как определение недопустимых условий в подсистеме выполнения среды выполнения или дамп дополнительных сведений о состоянии ядре.</span><span class="sxs-lookup"><span data-stu-id="18ee9-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="18ee9-113">MDA создают сообщения XML о событиях, которые в противном случае сложны для перехвата.</span><span class="sxs-lookup"><span data-stu-id="18ee9-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="18ee9-114">Они особенно полезны для отладки переходов между управляемым и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="18ee9-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="18ee9-115">При срабатывании события, запускающего создание MDA, среда выполнения выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="18ee9-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
- <span data-ttu-id="18ee9-116">Если узел не зарегистрировал экземпляр [иактиононклревент](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) , вызвав [ICLROnEventManager:: регистерактиононевент](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) , чтобы получать уведомления о событии `Event_MDAFired`, среда выполнения переходит по умолчанию, а не размещенное поведение.</span><span class="sxs-lookup"><span data-stu-id="18ee9-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
- <span data-ttu-id="18ee9-117">Если узел зарегистрировал обработчик для этого события, среда выполнения проверяет, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="18ee9-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="18ee9-118">Если это так, среда выполнения разбивается на отладчик.</span><span class="sxs-lookup"><span data-stu-id="18ee9-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="18ee9-119">Когда отладчик продолжит выполнение, он вызывает узел.</span><span class="sxs-lookup"><span data-stu-id="18ee9-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="18ee9-120">Если отладчик не присоединен, среда выполнения вызывает `IActionOnCLREvent::OnEvent` и передает указатель на экземпляр `MDAInfo` в качестве параметра `data`.</span><span class="sxs-lookup"><span data-stu-id="18ee9-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="18ee9-121">Узел может активировать MDA и получать уведомления при активации MDA.</span><span class="sxs-lookup"><span data-stu-id="18ee9-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="18ee9-122">Это дает узлу возможность переопределить поведение по умолчанию и прервать управляемый поток, вызвавший событие, чтобы предотвратить повреждение состояния процесса.</span><span class="sxs-lookup"><span data-stu-id="18ee9-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="18ee9-123">Дополнительные сведения об использовании MDA см. в разделе [Диагностика ошибок с помощью помощников по отладке управляемого](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)кода.</span><span class="sxs-lookup"><span data-stu-id="18ee9-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18ee9-124">Требования</span><span class="sxs-lookup"><span data-stu-id="18ee9-124">Requirements</span></span>  
 <span data-ttu-id="18ee9-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18ee9-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18ee9-126">**Заголовок:** MSCorEE. idl</span><span class="sxs-lookup"><span data-stu-id="18ee9-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="18ee9-127">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="18ee9-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="18ee9-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18ee9-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18ee9-129">См. также</span><span class="sxs-lookup"><span data-stu-id="18ee9-129">See also</span></span>

- [<span data-ttu-id="18ee9-130">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="18ee9-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="18ee9-131">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="18ee9-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
