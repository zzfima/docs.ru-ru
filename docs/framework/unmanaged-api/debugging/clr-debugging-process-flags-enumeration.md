---
title: "Перечисление CLR_DEBUGGING_PROCESS_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CLR_DEBUGGING_PROCESS_FLAGS
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CLR_DEBUGGING_PROCESS_FLAG
helpviewer_keywords:
- CLR_DEBUGGING_PROCESS_FLAGS enumeration [.NET Framework debugging]
ms.assetid: 85b85fde-1f87-490b-ba8d-d604670959c3
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4c6d66f9a11f28ca572e0f1eddc74f3a5197a19d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="clrdebuggingprocessflags-enumeration"></a><span data-ttu-id="efca1-102">Перечисление CLR_DEBUGGING_PROCESS_FLAGS</span><span class="sxs-lookup"><span data-stu-id="efca1-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="efca1-103">Предоставляет значения, которые используются в [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="efca1-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="efca1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="efca1-104">Syntax</span></span>  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="efca1-105">Участники</span><span class="sxs-lookup"><span data-stu-id="efca1-105">Members</span></span>  
  
|<span data-ttu-id="efca1-106">Член</span><span class="sxs-lookup"><span data-stu-id="efca1-106">Member</span></span>|<span data-ttu-id="efca1-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="efca1-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="efca1-108">Эта среда выполнения имеет событие catch вверх отладчика управляемого кода для отправки.</span><span class="sxs-lookup"><span data-stu-id="efca1-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="efca1-109">Различие между событиями, связанной с подключением и catch вверх см.</span><span class="sxs-lookup"><span data-stu-id="efca1-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="efca1-110">Управляемые события, которое находится в состоянии ожидания является <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> запроса.</span><span class="sxs-lookup"><span data-stu-id="efca1-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="efca1-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="efca1-111">Remarks</span></span>  
 <span data-ttu-id="efca1-112">Захват событий включают процесса, домена приложения, сборки, модуля и уведомления создания потока, что позволяет использовать отладчик до текущего состояния после он присоединен к процессу.</span><span class="sxs-lookup"><span data-stu-id="efca1-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="efca1-113">Non-catch вверх событий, которые обозначаются `CLR_DEBUGGING_MANAGED_EVENT_PENDING` флаг, включают все другие события отладчика, такие как исключения и управляемых отладки уведомления помощник (кода MDA).</span><span class="sxs-lookup"><span data-stu-id="efca1-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="efca1-114">`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` Флаг позволяет среде выполнения для различения неустранимое исключение и запрос на присоединение отладчика управляемого кода, может быть отменено.</span><span class="sxs-lookup"><span data-stu-id="efca1-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="efca1-115">Требования</span><span class="sxs-lookup"><span data-stu-id="efca1-115">Requirements</span></span>  
 <span data-ttu-id="efca1-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="efca1-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="efca1-117">**Заголовок:** Metahost.idl, Metahost.h</span><span class="sxs-lookup"><span data-stu-id="efca1-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="efca1-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="efca1-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="efca1-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="efca1-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efca1-120">См. также</span><span class="sxs-lookup"><span data-stu-id="efca1-120">See Also</span></span>  
 [<span data-ttu-id="efca1-121">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="efca1-121">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="efca1-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="efca1-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
