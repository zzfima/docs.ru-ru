---
title: Перечисление CorDebugUserState
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
ms.openlocfilehash: d0394d511197c8d0aaa366ce7b791216a3d226bc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120192"
---
# <a name="cordebuguserstate-enumeration"></a><span data-ttu-id="97a3d-102">Перечисление CorDebugUserState</span><span class="sxs-lookup"><span data-stu-id="97a3d-102">CorDebugUserState Enumeration</span></span>
<span data-ttu-id="97a3d-103">Указывает состояние пользователя потока.</span><span class="sxs-lookup"><span data-stu-id="97a3d-103">Indicates the user state of a thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="97a3d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="97a3d-104">Syntax</span></span>  
  
```cpp  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a><span data-ttu-id="97a3d-105">Члены</span><span class="sxs-lookup"><span data-stu-id="97a3d-105">Members</span></span>  
  
|<span data-ttu-id="97a3d-106">значения</span><span class="sxs-lookup"><span data-stu-id="97a3d-106">Value</span></span>|<span data-ttu-id="97a3d-107">Описание</span><span class="sxs-lookup"><span data-stu-id="97a3d-107">Description</span></span>|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|<span data-ttu-id="97a3d-108">Запрошено завершение потока.</span><span class="sxs-lookup"><span data-stu-id="97a3d-108">A termination of the thread has been requested.</span></span>|  
|`USER_SUSPEND_REQUESTED`|<span data-ttu-id="97a3d-109">Запрошена приостановка потока.</span><span class="sxs-lookup"><span data-stu-id="97a3d-109">A suspension of the thread has been requested.</span></span>|  
|`USER_BACKGROUND`|<span data-ttu-id="97a3d-110">Поток выполняется в фоновом режиме.</span><span class="sxs-lookup"><span data-stu-id="97a3d-110">The thread is running in the background.</span></span>|  
|`USER_UNSTARTED`|<span data-ttu-id="97a3d-111">Поток не начал выполнять.</span><span class="sxs-lookup"><span data-stu-id="97a3d-111">The thread has not started executing.</span></span>|  
|`USER_STOPPED`|<span data-ttu-id="97a3d-112">Поток был завершен.</span><span class="sxs-lookup"><span data-stu-id="97a3d-112">The thread has been terminated.</span></span>|  
|`USER_WAIT_SLEEP_JOIN`|<span data-ttu-id="97a3d-113">Поток ожидает завершения задачи другим потоком.</span><span class="sxs-lookup"><span data-stu-id="97a3d-113">The thread is waiting for another thread to complete a task.</span></span>|  
|`USER_SUSPENDED`|<span data-ttu-id="97a3d-114">Поток был приостановлен.</span><span class="sxs-lookup"><span data-stu-id="97a3d-114">The thread has been suspended.</span></span>|  
|`USER_UNSAFE_POINT`|<span data-ttu-id="97a3d-115">Поток находится в ненадежной точке.</span><span class="sxs-lookup"><span data-stu-id="97a3d-115">The thread is at an unsafe point.</span></span> <span data-ttu-id="97a3d-116">Это значит, что поток находится в точке выполнения, где он может блокировать сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="97a3d-116">That is, the thread is at a point in execution where it may block garbage collection.</span></span><br /><br /> <span data-ttu-id="97a3d-117">События отладки могут быть отправлены из ненадежных точек, но приостановка потока в незащищенной точке, скорее всего, вызовет взаимоблокировку до возобновления потока.</span><span class="sxs-lookup"><span data-stu-id="97a3d-117">Debug events may be dispatched from unsafe points, but suspending a thread at an unsafe point  will very likely cause a deadlock until the thread is resumed.</span></span> <span data-ttu-id="97a3d-118">Надежные и незащищенные точки определяются реализацией JIT и сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="97a3d-118">The safe and unsafe points are determined by the just-in-time (JIT) and garbage collection implementation.</span></span>|  
|`USER_THREADPOOL`|<span data-ttu-id="97a3d-119">Поток из пула потоков.</span><span class="sxs-lookup"><span data-stu-id="97a3d-119">The thread is from the thread pool.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="97a3d-120">Заметки</span><span class="sxs-lookup"><span data-stu-id="97a3d-120">Remarks</span></span>  
 <span data-ttu-id="97a3d-121">Пользовательское состояние потока — это состояние, которое поток имеет при его проверке отладчиком.</span><span class="sxs-lookup"><span data-stu-id="97a3d-121">The user state of a thread is the state that the thread has when the debugger examines it.</span></span> <span data-ttu-id="97a3d-122">Поток может иметь сочетание пользовательских состояний.</span><span class="sxs-lookup"><span data-stu-id="97a3d-122">A thread may have a combination of user states.</span></span>  
  
 <span data-ttu-id="97a3d-123">Чтобы получить состояние пользователя потока, используйте метод [ICorDebugThread:: жетусерстате](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) .</span><span class="sxs-lookup"><span data-stu-id="97a3d-123">Use the [ICorDebugThread::GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) method to retrieve a thread's user state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="97a3d-124">Требования</span><span class="sxs-lookup"><span data-stu-id="97a3d-124">Requirements</span></span>  
 <span data-ttu-id="97a3d-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="97a3d-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="97a3d-126">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="97a3d-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="97a3d-127">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="97a3d-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="97a3d-128">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="97a3d-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97a3d-129">См. также</span><span class="sxs-lookup"><span data-stu-id="97a3d-129">See also</span></span>

- [<span data-ttu-id="97a3d-130">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="97a3d-130">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
