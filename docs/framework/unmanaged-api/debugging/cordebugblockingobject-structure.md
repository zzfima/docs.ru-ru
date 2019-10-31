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
ms.openlocfilehash: 21f90e06b3b02ebc6c97610b6edc35697601f0ac
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132286"
---
# <a name="cordebugblockingobject-structure"></a><span data-ttu-id="d4575-102">Структура CorDebugBlockingObject</span><span class="sxs-lookup"><span data-stu-id="d4575-102">CorDebugBlockingObject Structure</span></span>
<span data-ttu-id="d4575-103">Определяет объект, который блокирует поток и конкретную причину блокировки потока.</span><span class="sxs-lookup"><span data-stu-id="d4575-103">Defines an object that is blocking a thread and the specific reason that the thread is blocked.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4575-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d4575-104">Syntax</span></span>  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a><span data-ttu-id="d4575-105">Члены</span><span class="sxs-lookup"><span data-stu-id="d4575-105">Members</span></span>  
  
|<span data-ttu-id="d4575-106">Член</span><span class="sxs-lookup"><span data-stu-id="d4575-106">Member</span></span>|<span data-ttu-id="d4575-107">Описание</span><span class="sxs-lookup"><span data-stu-id="d4575-107">Description</span></span>|  
|------------|-----------------|  
|`pBlockingObject`|<span data-ttu-id="d4575-108">Объект, для которого блокируется поток.</span><span class="sxs-lookup"><span data-stu-id="d4575-108">The object on which the thread is blocking.</span></span> <span data-ttu-id="d4575-109">Этот объект допустим только в течение текущего синхронизированного состояния.</span><span class="sxs-lookup"><span data-stu-id="d4575-109">This object is valid only for the duration of the current synchronized state.</span></span> <span data-ttu-id="d4575-110">Если два потока блокируют один и тот же объект в одном и том же синхронизированном состоянии, то, возможно, предполагается, что метод [ICorDebugValue::](icordebugvalue-getaddress-method.md) GetObject возвратит одно и то же значение.</span><span class="sxs-lookup"><span data-stu-id="d4575-110">If two threads are blocking on the same object within the same synchronized state, you may expect the [ICorDebugValue::GetAddress](icordebugvalue-getaddress-method.md) method to return the same value.</span></span> <span data-ttu-id="d4575-111">Однако интерфейсы могут и не быть эквивалентными указателями.</span><span class="sxs-lookup"><span data-stu-id="d4575-111">However, the interfaces may or may not be pointer equivalent.</span></span>|  
|`dwTimeout`|<span data-ttu-id="d4575-112">Время ожидания (в миллисекундах), по истечении которого операция блокирования истечет или бесконечное значение, которое указывает, что время ожидания не истечет. Значение времени ожидания указывает общий период времени для блокирующей операции, а не оставшееся время.</span><span class="sxs-lookup"><span data-stu-id="d4575-112">The number of milliseconds before the blocking operation will time out, or the value INFINITE, which indicates that it will not time out. The time-out value specifies the total length of time for the blocking operation, not the time that is still remaining.</span></span>|  
|`blockingReason`|<span data-ttu-id="d4575-113">Причина, по которой поток блокируется для этого объекта.</span><span class="sxs-lookup"><span data-stu-id="d4575-113">The reason that the thread is blocked on this object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d4575-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="d4575-114">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d4575-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d4575-115">Requirements</span></span>  
 <span data-ttu-id="d4575-116">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d4575-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d4575-117">**Заголовок:** CorDebug. idl</span><span class="sxs-lookup"><span data-stu-id="d4575-117">**Header:** CorDebug.idl</span></span>  
  
 <span data-ttu-id="d4575-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d4575-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d4575-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d4575-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4575-120">См. также</span><span class="sxs-lookup"><span data-stu-id="d4575-120">See also</span></span>

- [<span data-ttu-id="d4575-121">Структуры отладки</span><span class="sxs-lookup"><span data-stu-id="d4575-121">Debugging Structures</span></span>](debugging-structures.md)
- [<span data-ttu-id="d4575-122">Отладка</span><span class="sxs-lookup"><span data-stu-id="d4575-122">Debugging</span></span>](index.md)
