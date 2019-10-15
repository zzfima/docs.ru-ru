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
ms.openlocfilehash: 99fcf160b3e3b2b238520e3db5ba2e74b270380a
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274132"
---
# <a name="cordebugblockingreason-enumeration"></a><span data-ttu-id="c2aeb-102">Перечисление CorDebugBlockingReason</span><span class="sxs-lookup"><span data-stu-id="c2aeb-102">CorDebugBlockingReason Enumeration</span></span>
<span data-ttu-id="c2aeb-103">Указывает возможные причины блокировки потока на данном объекте.</span><span class="sxs-lookup"><span data-stu-id="c2aeb-103">Specifies the reasons why a thread may become blocked on a given object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2aeb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2aeb-104">Syntax</span></span>  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a><span data-ttu-id="c2aeb-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c2aeb-105">Members</span></span>  
  
|<span data-ttu-id="c2aeb-106">Член</span><span class="sxs-lookup"><span data-stu-id="c2aeb-106">Member</span></span>|<span data-ttu-id="c2aeb-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c2aeb-107">Description</span></span>|  
|------------|-----------------|  
|`BLOCKING_NONE`|<span data-ttu-id="c2aeb-108">Только для внутреннего использования.</span><span class="sxs-lookup"><span data-stu-id="c2aeb-108">Internal use only.</span></span>|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|<span data-ttu-id="c2aeb-109">Поток пытается получить критическую секцию, связанную с блокировкой монитора для объекта.</span><span class="sxs-lookup"><span data-stu-id="c2aeb-109">A thread is trying to acquire the critical section that is associated with the monitor lock on an object.</span></span> <span data-ttu-id="c2aeb-110">Как правило, это происходит при вызове одного из <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> методов <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> или.</span><span class="sxs-lookup"><span data-stu-id="c2aeb-110">Typically, this occurs when you call one of the <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> or <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> methods.</span></span>|  
|`BLOCKING_MONITOR_EVENT`|<span data-ttu-id="c2aeb-111">Поток ожидает события, связанного с блокировкой монитора для объекта.</span><span class="sxs-lookup"><span data-stu-id="c2aeb-111">A thread is waiting on the event that is associated with a monitor lock for an object.</span></span> <span data-ttu-id="c2aeb-112">Как правило, это происходит при вызове одного из <xref:System.Threading.Monitor?displayProperty=nameWithType> `Wait` методов.</span><span class="sxs-lookup"><span data-stu-id="c2aeb-112">Typically, this occurs when you call one of the <xref:System.Threading.Monitor?displayProperty=nameWithType>`Wait` methods.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c2aeb-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2aeb-113">Remarks</span></span>  
 <span data-ttu-id="c2aeb-114">Если элемент `BLOCKING_MONITOR_CRITICAL_SECTION` или `BLOCKING_MONITOR_EVENT` используется в структуре [CorDebugBlockingObject](cordebugblockingobject-structure.md), элемент `pBlockingObject` структуры указывает на интерфейс "ICorDebugValue", представляющий объект, который необходимо указать.</span><span class="sxs-lookup"><span data-stu-id="c2aeb-114">When the `BLOCKING_MONITOR_CRITICAL_SECTION` or `BLOCKING_MONITOR_EVENT` member is used in a [CorDebugBlockingObject](cordebugblockingobject-structure.md) structure, the `pBlockingObject` member of the structure points to an "ICorDebugValue" interface that represents the object that is being entered.</span></span> <span data-ttu-id="c2aeb-115">Также гарантируется реализация интерфейса [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="c2aeb-115">It is also guaranteed to implement the [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2aeb-116">Требования</span><span class="sxs-lookup"><span data-stu-id="c2aeb-116">Requirements</span></span>  
 <span data-ttu-id="c2aeb-117">**Платформ** См. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2aeb-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2aeb-118">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="c2aeb-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c2aeb-119">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="c2aeb-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2aeb-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2aeb-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2aeb-121">См. также</span><span class="sxs-lookup"><span data-stu-id="c2aeb-121">See also</span></span>

- [<span data-ttu-id="c2aeb-122">Перечисления отладки</span><span class="sxs-lookup"><span data-stu-id="c2aeb-122">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="c2aeb-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="c2aeb-123">Debugging</span></span>](index.md)
