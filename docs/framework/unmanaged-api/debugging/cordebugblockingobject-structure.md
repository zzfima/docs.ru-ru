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
ms.openlocfilehash: ed7db321b32657087b791758096c692f25f3d7f5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="ffedf-102">Структура CorDebugBlockingObject</span><span class="sxs-lookup"><span data-stu-id="ffedf-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="ffedf-103">Определяет объект, блокирующий поток и конкретную причину блокировки потока.</span><span class="sxs-lookup"><span data-stu-id="ffedf-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffedf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ffedf-104">Syntax</span></span>  
  
```  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="ffedf-105">Участники</span><span class="sxs-lookup"><span data-stu-id="ffedf-105">Members</span></span>  
  
|<span data-ttu-id="ffedf-106">Член</span><span class="sxs-lookup"><span data-stu-id="ffedf-106">Member</span></span>|<span data-ttu-id="ffedf-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ffedf-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="ffedf-108">Объект, на котором блокирован поток.</span><span class="sxs-lookup"><span data-stu-id="ffedf-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="ffedf-109">Этот объект действителен только в течение текущего синхронизированного состояния.</span><span class="sxs-lookup"><span data-stu-id="ffedf-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="ffedf-110">Если два потока блокируются на одном объекте в одном синхронизированном состоянии, можно ожидать [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) метод, чтобы возвращать то же значение.</span><span class="sxs-lookup"><span data-stu-id="ffedf-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="ffedf-111">Однако интерфейсы могут находиться не эквивалентность указателей.</span><span class="sxs-lookup"><span data-stu-id="ffedf-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="ffedf-112">Количество миллисекунд до операции блокирования будет время ожидания, или значение INFINITE, означающее, что он имеет неограниченное время ожидания. Значение времени ожидания указывает общую длину время операции блокировки, а не осталось времени.</span><span class="sxs-lookup"><span data-stu-id="ffedf-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="ffedf-113">Причина, что поток заблокирован для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="ffedf-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ffedf-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="ffedf-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ffedf-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ffedf-115">Requirements</span></span>  
 <span data-ttu-id="ffedf-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffedf-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffedf-117">**Заголовок:** CorDebug.idl</span><span class="sxs-lookup"><span data-stu-id="ffedf-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="ffedf-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ffedf-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ffedf-119">**Версии платформы .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffedf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffedf-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ffedf-120">See Also</span></span>  
 [<span data-ttu-id="ffedf-121">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="ffedf-121">Debugging Structures</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [<span data-ttu-id="ffedf-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="ffedf-122">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
