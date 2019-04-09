---
title: Перечисление CorDebugThreadState
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: efb7f5b8e63742471123a0e0a38cebe605f3696f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092452"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="4068e-102">Перечисление CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="4068e-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="4068e-103">Указывает состояние потока для отладки.</span><span class="sxs-lookup"><span data-stu-id="4068e-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4068e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4068e-104">Syntax</span></span>  
  
```  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="4068e-105">Участники</span><span class="sxs-lookup"><span data-stu-id="4068e-105">Members</span></span>  
  
|<span data-ttu-id="4068e-106">Член</span><span class="sxs-lookup"><span data-stu-id="4068e-106">Member</span></span>|<span data-ttu-id="4068e-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4068e-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="4068e-108">Поток выполняется свободно, пока не произойдет событие отладки.</span><span class="sxs-lookup"><span data-stu-id="4068e-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="4068e-109">Не удается запустить поток.</span><span class="sxs-lookup"><span data-stu-id="4068e-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4068e-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="4068e-110">Remarks</span></span>  
 <span data-ttu-id="4068e-111">Отладчик использует `CorDebugThreadState` перечисления для контроля потока выполнения.</span><span class="sxs-lookup"><span data-stu-id="4068e-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="4068e-112">Состояние потока, можно задать с помощью [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) или [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4068e-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="4068e-113">Обратный вызов, предоставленный [интерфейс API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md) позволяет выдачи сообщений, поэтому состояния прерванного не требуется.</span><span class="sxs-lookup"><span data-stu-id="4068e-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4068e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="4068e-114">Requirements</span></span>  
 <span data-ttu-id="4068e-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4068e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4068e-116">**Заголовок.** CorDebug.idl, CorDegug.h</span><span class="sxs-lookup"><span data-stu-id="4068e-116">**Header:** CorDebug.idl, CorDegug.h</span></span>  
  
 <span data-ttu-id="4068e-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4068e-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="4068e-118">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4068e-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4068e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="4068e-119">See also</span></span>

- [<span data-ttu-id="4068e-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="4068e-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
