---
title: Перечисление CLR_DEBUGGING_PROCESS_FLAGS
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8321e5aeba435ca5f1398a9cb827a93ae821d686
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217332"
---
# <a name="clrdebuggingprocessflags-enumeration"></a><span data-ttu-id="9e94e-102">Перечисление CLR_DEBUGGING_PROCESS_FLAGS</span><span class="sxs-lookup"><span data-stu-id="9e94e-102">CLR_DEBUGGING_PROCESS_FLAGS Enumeration</span></span>
<span data-ttu-id="9e94e-103">Предоставляет значения, используемые [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="9e94e-103">Provides values that are used by the [ICLRDebugging::OpenVirtualProcess](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-openvirtualprocess-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e94e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9e94e-104">Syntax</span></span>  
  
```  
typedef enum CLR_DEBUGGING_PROCESS_FLAGS  
{  
   CLR_DEBUGGING_MANAGED_EVENT_PENDING = 1,  
   CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH = 2  
}  CLR_DEBUGGING_PROCESS_FLAGS;  
```  
  
## <a name="members"></a><span data-ttu-id="9e94e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="9e94e-105">Members</span></span>  
  
|<span data-ttu-id="9e94e-106">Член</span><span class="sxs-lookup"><span data-stu-id="9e94e-106">Member</span></span>|<span data-ttu-id="9e94e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="9e94e-107">Description</span></span>|  
|------------|-----------------|  
|`CLR_DEBUGGING_MANAGED_EVENT_PENDING`|<span data-ttu-id="9e94e-108">Эта среда выполнения имеет событие catch вверх управляемого отладчика для отправки.</span><span class="sxs-lookup"><span data-stu-id="9e94e-108">This runtime has a non-catch-up managed debugger event to send.</span></span> <span data-ttu-id="9e94e-109">См. в разделе "Примечания" различие между событиями наверстывания и catch вверх.</span><span class="sxs-lookup"><span data-stu-id="9e94e-109">See the Remarks section for the distinction between catch-up and non-catch-up events.</span></span>|  
|`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH`|<span data-ttu-id="9e94e-110">Управляемое событие, которое находится в состоянии ожидания является <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> запроса.</span><span class="sxs-lookup"><span data-stu-id="9e94e-110">The managed event that is pending is a <xref:System.Diagnostics.Debugger.Launch%2A?displayProperty=nameWithType> request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9e94e-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="9e94e-111">Remarks</span></span>  
 <span data-ttu-id="9e94e-112">Захват событий включают процесса, домена приложения, сборки, модуля и поток создания уведомлений, которые приносят отладчик до текущего состояния после ее присоединения к процессу.</span><span class="sxs-lookup"><span data-stu-id="9e94e-112">Catch-up events include process, application domain, assembly, module, and thread creation notifications that bring the debugger up to the current state after it has attached to a process.</span></span> <span data-ttu-id="9e94e-113">Non-catch вверх событий, которые обозначены `CLR_DEBUGGING_MANAGED_EVENT_PENDING` флаг, включают все другие события отладчика, такие как исключения и управлении отладки уведомления помощник (кода MDA).</span><span class="sxs-lookup"><span data-stu-id="9e94e-113">Non-catch-up events, which are indicated by the `CLR_DEBUGGING_MANAGED_EVENT_PENDING` flag, include all other debugger events, such as exceptions and managed debugging assistant (MDA) notifications.</span></span>  
  
 <span data-ttu-id="9e94e-114">`CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` Флаг позволяет среде выполнения различать неустранимое исключение и запрос на присоединение управляемого отладчика, которое может быть отменено.</span><span class="sxs-lookup"><span data-stu-id="9e94e-114">The `CLR_DEBUGGING_MANAGED_EVENT_DEBUGGER_LAUNCH` flag enables the runtime to differentiate between a terminating exception and a request to attach a managed debugger that can be canceled.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e94e-115">Требования</span><span class="sxs-lookup"><span data-stu-id="9e94e-115">Requirements</span></span>  
 <span data-ttu-id="9e94e-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9e94e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e94e-117">**Заголовок.** Metahost.IDL Metahost.h</span><span class="sxs-lookup"><span data-stu-id="9e94e-117">**Header:** Metahost.idl, Metahost.h</span></span>  
  
 <span data-ttu-id="9e94e-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e94e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e94e-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e94e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e94e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="9e94e-120">See also</span></span>

- [<span data-ttu-id="9e94e-121">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="9e94e-121">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="9e94e-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="9e94e-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
