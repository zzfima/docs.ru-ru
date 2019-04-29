---
title: Структура CorDebugBlockingObject
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 12a114ea65aca544d653704cdfb01ed15d19c581
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61609273"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="c60a5-102">Структура CorDebugBlockingObject</span><span class="sxs-lookup"><span data-stu-id="c60a5-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="c60a5-103">Определяет объект, блокирующий поток и особых причин, что поток блокируется.</span><span class="sxs-lookup"><span data-stu-id="c60a5-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c60a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c60a5-104">Syntax</span></span>  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="c60a5-105">Участники</span><span class="sxs-lookup"><span data-stu-id="c60a5-105">Members</span></span>  
  
|<span data-ttu-id="c60a5-106">Член</span><span class="sxs-lookup"><span data-stu-id="c60a5-106">Member</span></span>|<span data-ttu-id="c60a5-107">Описание</span><span class="sxs-lookup"><span data-stu-id="c60a5-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="c60a5-108">Объект, на котором блокирован поток.</span><span class="sxs-lookup"><span data-stu-id="c60a5-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="c60a5-109">Этот объект действителен только в течение текущего синхронизированного состояния.</span><span class="sxs-lookup"><span data-stu-id="c60a5-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="c60a5-110">Если два потока блокируются на один и тот же объект в этом же состоянии, можно ожидать [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) метод, чтобы возвращать то же значение.</span><span class="sxs-lookup"><span data-stu-id="c60a5-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="c60a5-111">Однако интерфейсы могут или не может быть указателем эквивалент.</span><span class="sxs-lookup"><span data-stu-id="c60a5-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="c60a5-112">Количество миллисекунд до операции блокирования будет время ожидания, или значение INFINITE, означающее, что он будет время ожидания не истекает. Значение времени ожидания указывает общую длину времени блокирующие операции, не осталось времени.</span><span class="sxs-lookup"><span data-stu-id="c60a5-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="c60a5-113">Причина, что поток блокируется на этот объект.</span><span class="sxs-lookup"><span data-stu-id="c60a5-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c60a5-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="c60a5-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c60a5-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c60a5-115">Requirements</span></span>  
 <span data-ttu-id="c60a5-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c60a5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c60a5-117">**Заголовок.** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="c60a5-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="c60a5-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c60a5-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c60a5-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c60a5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c60a5-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c60a5-120">See also</span></span>

- [<span data-ttu-id="c60a5-121">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="c60a5-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [<span data-ttu-id="c60a5-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="c60a5-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
