---
title: Перечисление CorDebugBlockingReason
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54652727b4684d71068a19eb5eeb2e862f413f25
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215083"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="41ebd-102">Перечисление CorDebugBlockingReason</span><span class="sxs-lookup"><span data-stu-id="41ebd-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="41ebd-103">Указывает возможные причины блокировки потока на данном объекте.</span><span class="sxs-lookup"><span data-stu-id="41ebd-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41ebd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="41ebd-104">Syntax</span></span>  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="41ebd-105">Участники</span><span class="sxs-lookup"><span data-stu-id="41ebd-105">Members</span></span>  
  
|<span data-ttu-id="41ebd-106">Член</span><span class="sxs-lookup"><span data-stu-id="41ebd-106">Member</span></span>|<span data-ttu-id="41ebd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="41ebd-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="41ebd-108">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="41ebd-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="41ebd-109">Поток пытается получить критический раздел, связанный с блокировкой монитора на объект.</span><span class="sxs-lookup"><span data-stu-id="41ebd-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="41ebd-110">Как правило, это происходит при вызове одного из <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> или <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> методы.</span><span class="sxs-lookup"><span data-stu-id="41ebd-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="41ebd-111">Поток ожидает события, связанного с блокировкой монитора для объекта.</span><span class="sxs-lookup"><span data-stu-id="41ebd-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="41ebd-112">Как правило, это происходит при вызове одного из <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` методы.</span><span class="sxs-lookup"><span data-stu-id="41ebd-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="41ebd-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="41ebd-113">Remarks</span></span>  
 <span data-ttu-id="41ebd-114">Когда `BLOCKING_MONITOR_CRITICAL_SECTION` или `BLOCKING_MONITOR_EVENT` элемент используется в [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры, `pBlockingObject` член структуры точек «ICorDebugValue» интерфейс, который представляет объект, который будет введено .</span><span class="sxs-lookup"><span data-stu-id="41ebd-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="41ebd-115">Оно также реализовать [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) интерфейс.</span><span class="sxs-lookup"><span data-stu-id="41ebd-115">It is also guaranteed to implement the [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41ebd-116">Требования</span><span class="sxs-lookup"><span data-stu-id="41ebd-116">Requirements</span></span>  
 <span data-ttu-id="41ebd-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41ebd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41ebd-118">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="41ebd-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="41ebd-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41ebd-119">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="41ebd-120">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="41ebd-120">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="41ebd-121">См. также</span><span class="sxs-lookup"><span data-stu-id="41ebd-121">See also</span></span>

- [<span data-ttu-id="41ebd-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="41ebd-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="41ebd-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="41ebd-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
