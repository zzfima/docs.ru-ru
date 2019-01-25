---
title: Интерфейс1 ICorDebugValue
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 41afc2e4305034340ad408e52ce08372bf8962dd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54507451"
---
# <a name="icordebugvalue-interface1"></a><span data-ttu-id="a900b-102">Интерфейс1 ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="a900b-102">ICorDebugValue Interface1</span></span>
<span data-ttu-id="a900b-103">Представляет значение в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="a900b-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="a900b-104">Значение может быть чтения или записи.</span><span class="sxs-lookup"><span data-stu-id="a900b-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a900b-105">Методы</span><span class="sxs-lookup"><span data-stu-id="a900b-105">Methods</span></span>  
  
|<span data-ttu-id="a900b-106">Метод</span><span class="sxs-lookup"><span data-stu-id="a900b-106">Method</span></span>|<span data-ttu-id="a900b-107">Описание:</span><span class="sxs-lookup"><span data-stu-id="a900b-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a900b-108">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="a900b-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="a900b-109">В настоящее время этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="a900b-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="a900b-110">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="a900b-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="a900b-111">Возвращает адрес это `ICorDebugValue` объект, который находится в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="a900b-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="a900b-112">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="a900b-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="a900b-113">Получает размер в байтах, это `ICorDebugValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="a900b-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="a900b-114">Метод GetType</span><span class="sxs-lookup"><span data-stu-id="a900b-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="a900b-115">Получает тип-примитив это `ICorDebugValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="a900b-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a900b-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="a900b-116">Remarks</span></span>  
 <span data-ttu-id="a900b-117">Как правило владение объектом значение передается при возврате.</span><span class="sxs-lookup"><span data-stu-id="a900b-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="a900b-118">Получатель отвечает за удаление ссылки из объекта при его завершении с объектом.</span><span class="sxs-lookup"><span data-stu-id="a900b-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="a900b-119">В зависимости от того, где значение было получено путем значение может не остаются действительными после возобновления процесса.</span><span class="sxs-lookup"><span data-stu-id="a900b-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="a900b-120">Таким образом, как правило, значение не должно храниться во время вызова из [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="a900b-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a900b-121">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="a900b-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a900b-122">Требования</span><span class="sxs-lookup"><span data-stu-id="a900b-122">Requirements</span></span>  
 <span data-ttu-id="a900b-123">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a900b-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a900b-124">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a900b-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a900b-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a900b-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a900b-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a900b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a900b-127">См. также</span><span class="sxs-lookup"><span data-stu-id="a900b-127">See also</span></span>




- [<span data-ttu-id="a900b-128">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="a900b-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="a900b-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a900b-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
