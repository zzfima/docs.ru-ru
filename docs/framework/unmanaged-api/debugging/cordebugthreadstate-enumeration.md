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
ms.openlocfilehash: 1ff36e8ef6b7c02eea5b02bc22587bc3889df093
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133692"
---
# <a name="cordebugthreadstate-enumeration"></a><span data-ttu-id="db7f1-102">Перечисление CorDebugThreadState</span><span class="sxs-lookup"><span data-stu-id="db7f1-102">CorDebugThreadState Enumeration</span></span>
<span data-ttu-id="db7f1-103">Указывает состояние потока для отладки.</span><span class="sxs-lookup"><span data-stu-id="db7f1-103">Specifies the state of a thread for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db7f1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="db7f1-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a><span data-ttu-id="db7f1-105">Члены</span><span class="sxs-lookup"><span data-stu-id="db7f1-105">Members</span></span>  
  
|<span data-ttu-id="db7f1-106">Член</span><span class="sxs-lookup"><span data-stu-id="db7f1-106">Member</span></span>|<span data-ttu-id="db7f1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="db7f1-107">Description</span></span>|  
|------------|-----------------|  
|`THREAD_RUN`|<span data-ttu-id="db7f1-108">Поток выполняется свободно, если не происходит событие отладки.</span><span class="sxs-lookup"><span data-stu-id="db7f1-108">The thread runs freely, unless a debug event occurs.</span></span>|  
|`THREAD_SUSPEND`|<span data-ttu-id="db7f1-109">Поток не может быть запущен.</span><span class="sxs-lookup"><span data-stu-id="db7f1-109">The thread cannot run.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db7f1-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="db7f1-110">Remarks</span></span>  
 <span data-ttu-id="db7f1-111">Отладчик использует перечисление `CorDebugThreadState` для управления выполнением потока.</span><span class="sxs-lookup"><span data-stu-id="db7f1-111">The debugger uses the `CorDebugThreadState` enumeration to control a thread's execution.</span></span> <span data-ttu-id="db7f1-112">Состояние потока можно задать с помощью метода [ICorDebugThread:: SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) или [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="db7f1-112">The state of a thread can be set by using the [ICorDebugThread::SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) or [ICorDebugController::SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) method.</span></span>  
  
 <span data-ttu-id="db7f1-113">Обратный вызов, предоставленный [API размещения](../../../../docs/framework/unmanaged-api/hosting/index.md) , позволяет передавать сообщения, поэтому прерывание состояния не требуется.</span><span class="sxs-lookup"><span data-stu-id="db7f1-113">A callback provided to the [hosting API](../../../../docs/framework/unmanaged-api/hosting/index.md) enables message pumping, so an interrupted state is not needed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db7f1-114">Требования</span><span class="sxs-lookup"><span data-stu-id="db7f1-114">Requirements</span></span>  
 <span data-ttu-id="db7f1-115">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db7f1-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db7f1-116">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db7f1-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db7f1-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db7f1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db7f1-118">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db7f1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db7f1-119">См. также</span><span class="sxs-lookup"><span data-stu-id="db7f1-119">See also</span></span>

- [<span data-ttu-id="db7f1-120">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="db7f1-120">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
