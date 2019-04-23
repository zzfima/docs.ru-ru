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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3be6f2b9454ed2f74d2cc6792cd9aaa2c25215db
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59104615"
---
# <a name="mdainfo-structure"></a><span data-ttu-id="036aa-102">Структура MDAInfo</span><span class="sxs-lookup"><span data-stu-id="036aa-102">MDAInfo Structure</span></span>
<span data-ttu-id="036aa-103">Предоставляет сведения о `Event_MDAFired` событие, которое инициирует создание помощник по отладке управляемого (кода MDA).</span><span class="sxs-lookup"><span data-stu-id="036aa-103">Provides details about the `Event_MDAFired` event, which triggers the creation of a managed debugging assistant (MDA).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="036aa-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="036aa-104">Syntax</span></span>  
  
```  
typedef struct _MDAInfo {  
    LPCWSTR  lpMDACaption;  
    LPCWSTR  lpMDAMessage  
} MDAInfo;  
```  
  
## <a name="members"></a><span data-ttu-id="036aa-105">Участники</span><span class="sxs-lookup"><span data-stu-id="036aa-105">Members</span></span>  
  
|<span data-ttu-id="036aa-106">Член</span><span class="sxs-lookup"><span data-stu-id="036aa-106">Member</span></span>|<span data-ttu-id="036aa-107">Описание</span><span class="sxs-lookup"><span data-stu-id="036aa-107">Description</span></span>|  
|------------|-----------------|  
|`lpMDACaption`|<span data-ttu-id="036aa-108">Название текущего MDA.</span><span class="sxs-lookup"><span data-stu-id="036aa-108">The title of the current MDA.</span></span> <span data-ttu-id="036aa-109">Заголовок описывает тип ошибки, вызвавшей `Event_MDAFired` событий.</span><span class="sxs-lookup"><span data-stu-id="036aa-109">The title describes the kind of failure that triggered the `Event_MDAFired` event.</span></span>|  
|`lpMDAMessage`|<span data-ttu-id="036aa-110">Выходное сообщение, предоставляемые текущего MDA.</span><span class="sxs-lookup"><span data-stu-id="036aa-110">The output message provided by the current MDA.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="036aa-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="036aa-111">Remarks</span></span>  
 <span data-ttu-id="036aa-112">Средств отладки, в сочетании с общеязыковой среды выполнения (CLR) для выполнения задач, таких как идентификация недопустимых состояний в ядре выполнения среды выполнения или создания дампа Дополнительные сведения о состоянии управляемых помощников по отладке (MDA) модуль.</span><span class="sxs-lookup"><span data-stu-id="036aa-112">Managed debugging assistants (MDAs) are debugging aids that work in conjunction with the common language runtime (CLR) to perform tasks such as identifying invalid conditions in the runtime execution engine or dumping additional information about the state of the engine.</span></span> <span data-ttu-id="036aa-113">Помощники отладки управляемого кода создавать XML-сообщений о событиях, которые в противном случае трудно ловушки.</span><span class="sxs-lookup"><span data-stu-id="036aa-113">MDAs generate XML messages about events that are otherwise difficult to trap.</span></span> <span data-ttu-id="036aa-114">Они особенно полезны для отладки переходов между управляемым и неуправляемым кодом.</span><span class="sxs-lookup"><span data-stu-id="036aa-114">They are especially useful for debugging transitions between managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="036aa-115">При возникновении события, которое инициирует создание MDA, среда выполнения выполняет следующие действия:</span><span class="sxs-lookup"><span data-stu-id="036aa-115">The runtime takes the following steps when an event that triggers the creation of an MDA is fired:</span></span>  
  
-   <span data-ttu-id="036aa-116">Если узел не зарегистрирован [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) экземпляра путем вызова [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) для получения уведомлений об `Event_MDAFired` события, среда выполнения продолжает его по умолчанию, поведение без размещения.</span><span class="sxs-lookup"><span data-stu-id="036aa-116">If the host has not registered an [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) instance by calling [ICLROnEventManager::RegisterActionOnEvent](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-registeractiononevent-method.md) to be notified of an `Event_MDAFired` event, the runtime proceeds with its default, non-hosted behavior.</span></span>  
  
-   <span data-ttu-id="036aa-117">Если узел зарегистрировал обработчик для этого события, среда выполнения проверяет, присоединен ли отладчик к процессу.</span><span class="sxs-lookup"><span data-stu-id="036aa-117">If the host has registered a handler for this event, the runtime checks to see whether a debugger is attached to the process.</span></span> <span data-ttu-id="036aa-118">В противном случае среда выполнения переключается в режим отладчика.</span><span class="sxs-lookup"><span data-stu-id="036aa-118">If it is, the runtime breaks into the debugger.</span></span> <span data-ttu-id="036aa-119">Когда отладчик продолжает, она вызывает главное приложение.</span><span class="sxs-lookup"><span data-stu-id="036aa-119">When the debugger continues, it calls into the host.</span></span> <span data-ttu-id="036aa-120">Если отладчик не присоединен, среда выполнения вызывает `IActionOnCLREvent::OnEvent` и передает указатель на `MDAInfo` экземпляр как `data` параметр.</span><span class="sxs-lookup"><span data-stu-id="036aa-120">If no debugger is attached, the runtime calls `IActionOnCLREvent::OnEvent` and passes a pointer to an `MDAInfo` instance as the `data` parameter.</span></span>  
  
 <span data-ttu-id="036aa-121">Узел можно активировать MDA и получать уведомления при активации MDA.</span><span class="sxs-lookup"><span data-stu-id="036aa-121">The host can choose to activate MDAs and to be notified when an MDA is activated.</span></span> <span data-ttu-id="036aa-122">Это предоставляет узлу возможность переопределить поведение по умолчанию и отменить управляемый поток, который вызвал событие, чтобы предотвратить повреждение состояния процесса.</span><span class="sxs-lookup"><span data-stu-id="036aa-122">This gives the host an opportunity to override default behavior and to abort the managed thread that raised the event, to prevent it from corrupting the process state.</span></span> <span data-ttu-id="036aa-123">Дополнительные сведения об использовании MDA, см. в разделе [Диагностика ошибок посредством управляемых помощников по отладке](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span><span class="sxs-lookup"><span data-stu-id="036aa-123">For more information about using MDAs, see [Diagnosing Errors with Managed Debugging Assistants](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="036aa-124">Требования</span><span class="sxs-lookup"><span data-stu-id="036aa-124">Requirements</span></span>  
 <span data-ttu-id="036aa-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="036aa-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="036aa-126">**Заголовок.** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="036aa-126">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="036aa-127">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="036aa-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="036aa-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="036aa-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="036aa-129">См. также</span><span class="sxs-lookup"><span data-stu-id="036aa-129">See also</span></span>

- [<span data-ttu-id="036aa-130">Структуры размещения</span><span class="sxs-lookup"><span data-stu-id="036aa-130">Hosting Structures</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [<span data-ttu-id="036aa-131">Диагностика ошибок посредством помощников по отладке управляемого кода</span><span class="sxs-lookup"><span data-stu-id="036aa-131">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
