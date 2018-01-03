---
title: "Перечисление CorDebugBlockingReason"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorDebugBlockingReason
api_location: mscordbi.dll
api_type: COM
f1_keywords: CorDebugBlockingReason
helpviewer_keywords: CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 84c09de4e0ce6e436c2c814c4cd9990db012d422
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="6fd89-102">Перечисление CorDebugBlockingReason</span><span class="sxs-lookup"><span data-stu-id="6fd89-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="6fd89-103">Указывает возможные причины блокировки потока на данном объекте.</span><span class="sxs-lookup"><span data-stu-id="6fd89-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fd89-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6fd89-104">Syntax</span></span>  
  
```  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="6fd89-105">Участники</span><span class="sxs-lookup"><span data-stu-id="6fd89-105">Members</span></span>  
  
|<span data-ttu-id="6fd89-106">Член</span><span class="sxs-lookup"><span data-stu-id="6fd89-106">Member</span></span>|<span data-ttu-id="6fd89-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="6fd89-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="6fd89-108">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="6fd89-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="6fd89-109">Поток пытается получить критический раздел, связанный с блокировкой монитора на объект.</span><span class="sxs-lookup"><span data-stu-id="6fd89-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="6fd89-110">Как правило, это происходит при вызове одного из <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> или <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> методы.</span><span class="sxs-lookup"><span data-stu-id="6fd89-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="6fd89-111">Поток ожидает события, связанного с блокировкой монитора для объекта.</span><span class="sxs-lookup"><span data-stu-id="6fd89-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="6fd89-112">Как правило, это происходит при вызове одного из <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` методы.</span><span class="sxs-lookup"><span data-stu-id="6fd89-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fd89-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="6fd89-113">Remarks</span></span>  
 <span data-ttu-id="6fd89-114">Когда `BLOCKING_MONITOR_CRITICAL_SECTION` или `BLOCKING_MONITOR_EVENT` член используется в [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) структуры `pBlockingObject` член структуры указывает интерфейс «ICorDebugValue», который представляет объект, который вводится .</span><span class="sxs-lookup"><span data-stu-id="6fd89-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](../../../../docs/framework/unmanaged-api/debugging/cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="6fd89-115">Также оно реализовать [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) интерфейса.</span><span class="sxs-lookup"><span data-stu-id="6fd89-115">It is also guaranteed to implement the [ICorDebugHeapValue3](../../../../docs/framework/unmanaged-api/debugging/icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fd89-116">Требования</span><span class="sxs-lookup"><span data-stu-id="6fd89-116">Requirements</span></span>  
 <span data-ttu-id="6fd89-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fd89-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fd89-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6fd89-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6fd89-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6fd89-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6fd89-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fd89-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fd89-121">См. также</span><span class="sxs-lookup"><span data-stu-id="6fd89-121">See Also</span></span>  
 [<span data-ttu-id="6fd89-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="6fd89-122">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [<span data-ttu-id="6fd89-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="6fd89-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
