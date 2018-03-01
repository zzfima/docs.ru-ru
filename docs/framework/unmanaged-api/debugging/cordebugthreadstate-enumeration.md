---
title: "Перечисление CorDebugThreadState"
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
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a5363282f2efed003238014390f50c448c529ce2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="0d716-102">Перечисление CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="0d716-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="0d716-103">Указывает состояние потока для отладки.</span><span class="sxs-lookup"><span data-stu-id="0d716-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d716-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0d716-104">Syntax</span></span>  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="0d716-105">Участники</span><span class="sxs-lookup"><span data-stu-id="0d716-105">Members</span></span>  
  
|<span data-ttu-id="0d716-106">Член</span><span class="sxs-lookup"><span data-stu-id="0d716-106">Member</span></span>|<span data-ttu-id="0d716-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="0d716-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="0d716-108">Поток выполняется свободно, пока не произойдет событие отладки.</span><span class="sxs-lookup"><span data-stu-id="0d716-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="0d716-109">Не удается запустить поток.</span><span class="sxs-lookup"><span data-stu-id="0d716-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0d716-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="0d716-110">Remarks</span></span>  
 <span data-ttu-id="0d716-111">Отладчик использует `CorDebugThreadState` перечисления для контроля потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="0d716-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="0d716-112">Состояние потока можно задать с помощью [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) или [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="0d716-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="0d716-113">Обратный вызов, предоставленный [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md) включает загрузку сообщения, поэтому состояния прерванного не требуется.</span><span class="sxs-lookup"><span data-stu-id="0d716-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d716-114">Требования</span><span class="sxs-lookup"><span data-stu-id="0d716-114">Requirements</span></span>  
 <span data-ttu-id="0d716-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d716-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d716-116">**Заголовок:** CorDebug.idl, CorDegug.h</span><span class="sxs-lookup"><span data-stu-id="0d716-116">**Header:** CorDebug.idl, CorDegug.h</span></span>  
  
 <span data-ttu-id="0d716-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0d716-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0d716-118">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d716-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d716-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0d716-119">See Also</span></span>  
 [<span data-ttu-id="0d716-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="0d716-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
