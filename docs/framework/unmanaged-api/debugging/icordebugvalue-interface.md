---
title: Интерфейс ICorDebugValue
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
ms.openlocfilehash: 77d28d8eef97a934c15ac29725f856f4bf39e6ce
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140156"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="38fde-102">Интерфейс ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="38fde-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="38fde-103">Представляет значение в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="38fde-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="38fde-104">Значением может быть значение Read или Write.</span><span class="sxs-lookup"><span data-stu-id="38fde-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="38fde-105">Методы</span><span class="sxs-lookup"><span data-stu-id="38fde-105">Methods</span></span>  
  
|<span data-ttu-id="38fde-106">Метод</span><span class="sxs-lookup"><span data-stu-id="38fde-106">Method</span></span>|<span data-ttu-id="38fde-107">Описание</span><span class="sxs-lookup"><span data-stu-id="38fde-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="38fde-108">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="38fde-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="38fde-109">Этот метод в настоящее время не реализован.</span><span class="sxs-lookup"><span data-stu-id="38fde-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="38fde-110">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="38fde-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="38fde-111">Возвращает адрес этого `ICorDebugValue` объекта, который находится в процессе отладки.</span><span class="sxs-lookup"><span data-stu-id="38fde-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="38fde-112">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="38fde-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="38fde-113">Возвращает размер данного объекта `ICorDebugValue` в байтах.</span><span class="sxs-lookup"><span data-stu-id="38fde-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="38fde-114">Метод GetType</span><span class="sxs-lookup"><span data-stu-id="38fde-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="38fde-115">Возвращает тип примитива данного объекта `ICorDebugValue`.</span><span class="sxs-lookup"><span data-stu-id="38fde-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="38fde-116">Заметки</span><span class="sxs-lookup"><span data-stu-id="38fde-116">Remarks</span></span>  
 <span data-ttu-id="38fde-117">В общем случае владение объектом значения передается при его возврате.</span><span class="sxs-lookup"><span data-stu-id="38fde-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="38fde-118">Получатель отвечает за удаление ссылки из объекта после завершения работы с объектом.</span><span class="sxs-lookup"><span data-stu-id="38fde-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="38fde-119">В зависимости от того, откуда было получено значение, оно может остаться недействительным после возобновления процесса.</span><span class="sxs-lookup"><span data-stu-id="38fde-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="38fde-120">Поэтому в общем случае значение не должно удерживаться в вызове метода [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="38fde-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38fde-121">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="38fde-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38fde-122">Требования</span><span class="sxs-lookup"><span data-stu-id="38fde-122">Requirements</span></span>  
 <span data-ttu-id="38fde-123">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38fde-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38fde-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38fde-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38fde-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38fde-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38fde-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38fde-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38fde-127">См. также</span><span class="sxs-lookup"><span data-stu-id="38fde-127">See also</span></span>

- [<span data-ttu-id="38fde-128">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="38fde-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="38fde-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="38fde-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
