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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bb2f6333f306c8a19c8b2f67986b23819b74ee0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966864"
---
# <a name="icordebugvalue-interface"></a><span data-ttu-id="8c699-102">Интерфейс ICorDebugValue</span><span class="sxs-lookup"><span data-stu-id="8c699-102">ICorDebugValue Interface</span></span>
<span data-ttu-id="8c699-103">Представляет значение в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="8c699-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="8c699-104">Значением может быть значение Read или Write.</span><span class="sxs-lookup"><span data-stu-id="8c699-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8c699-105">Методы</span><span class="sxs-lookup"><span data-stu-id="8c699-105">Methods</span></span>  
  
|<span data-ttu-id="8c699-106">Метод</span><span class="sxs-lookup"><span data-stu-id="8c699-106">Method</span></span>|<span data-ttu-id="8c699-107">Описание</span><span class="sxs-lookup"><span data-stu-id="8c699-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8c699-108">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="8c699-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="8c699-109">Этот метод в настоящее время не реализован.</span><span class="sxs-lookup"><span data-stu-id="8c699-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="8c699-110">Метод GetAddress</span><span class="sxs-lookup"><span data-stu-id="8c699-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="8c699-111">Возвращает адрес этого `ICorDebugValue` объекта, который находится в процессе отладки.</span><span class="sxs-lookup"><span data-stu-id="8c699-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="8c699-112">Метод GetSize</span><span class="sxs-lookup"><span data-stu-id="8c699-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="8c699-113">Возвращает размер данного `ICorDebugValue` объекта в байтах.</span><span class="sxs-lookup"><span data-stu-id="8c699-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="8c699-114">Метод GetType</span><span class="sxs-lookup"><span data-stu-id="8c699-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="8c699-115">Возвращает тип примитива этого `ICorDebugValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="8c699-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8c699-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="8c699-116">Remarks</span></span>  
 <span data-ttu-id="8c699-117">В общем случае владение объектом значения передается при его возврате.</span><span class="sxs-lookup"><span data-stu-id="8c699-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="8c699-118">Получатель отвечает за удаление ссылки из объекта после завершения работы с объектом.</span><span class="sxs-lookup"><span data-stu-id="8c699-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="8c699-119">В зависимости от того, откуда было получено значение, оно может остаться недействительным после возобновления процесса.</span><span class="sxs-lookup"><span data-stu-id="8c699-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="8c699-120">Поэтому в общем случае значение не должно удерживаться в вызове метода [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="8c699-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8c699-121">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="8c699-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8c699-122">Требования</span><span class="sxs-lookup"><span data-stu-id="8c699-122">Requirements</span></span>  
 <span data-ttu-id="8c699-123">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8c699-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8c699-124">**Заголовок.** CorDebug. idl, CorDebug. h</span><span class="sxs-lookup"><span data-stu-id="8c699-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8c699-125">**Библиотечная** Коргуидс. lib</span><span class="sxs-lookup"><span data-stu-id="8c699-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8c699-126">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8c699-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8c699-127">См. также</span><span class="sxs-lookup"><span data-stu-id="8c699-127">See also</span></span>

- [<span data-ttu-id="8c699-128">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="8c699-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [<span data-ttu-id="8c699-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="8c699-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
