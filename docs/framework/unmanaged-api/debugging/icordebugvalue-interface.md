---
title: "ICorDebugValue интерфейс1"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugValue
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugValue
helpviewer_keywords: ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 01c94df1d8e6ddef0110268461a2b28f594201b6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvalue-interface1"></a><span data-ttu-id="4d6b4-102">ICorDebugValue интерфейс1</span><span class="sxs-lookup"><span data-stu-id="4d6b4-102">ICorDebugValue Interface1</span></span>
<span data-ttu-id="4d6b4-103">Представляет значение в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="4d6b4-103">Represents a value in the process being debugged.</span></span> <span data-ttu-id="4d6b4-104">Значение может быть чтения или записи.</span><span class="sxs-lookup"><span data-stu-id="4d6b4-104">The value can be a read or a write value.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4d6b4-105">Методы</span><span class="sxs-lookup"><span data-stu-id="4d6b4-105">Methods</span></span>  
  
|<span data-ttu-id="4d6b4-106">Метод</span><span class="sxs-lookup"><span data-stu-id="4d6b4-106">Method</span></span>|<span data-ttu-id="4d6b4-107">Описание</span><span class="sxs-lookup"><span data-stu-id="4d6b4-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4d6b4-108">Метод CreateBreakpoint</span><span class="sxs-lookup"><span data-stu-id="4d6b4-108">CreateBreakpoint Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|<span data-ttu-id="4d6b4-109">В настоящее время этот метод не реализован.</span><span class="sxs-lookup"><span data-stu-id="4d6b4-109">This method is not currently implemented.</span></span>|  
|[<span data-ttu-id="4d6b4-110">GetAddress-метод</span><span class="sxs-lookup"><span data-stu-id="4d6b4-110">GetAddress Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|<span data-ttu-id="4d6b4-111">Возвращает адрес этого `ICorDebugValue` объект, используемый в отлаживаемом процессе.</span><span class="sxs-lookup"><span data-stu-id="4d6b4-111">Gets the address of this `ICorDebugValue` object, which is in the process of being debugged.</span></span>|  
|[<span data-ttu-id="4d6b4-112">GetSize-метод</span><span class="sxs-lookup"><span data-stu-id="4d6b4-112">GetSize Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|<span data-ttu-id="4d6b4-113">Возвращает размер в байтах этого `ICorDebugValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="4d6b4-113">Gets the size, in bytes, of this `ICorDebugValue` object.</span></span>|  
|[<span data-ttu-id="4d6b4-114">GetType-метод</span><span class="sxs-lookup"><span data-stu-id="4d6b4-114">GetType Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|<span data-ttu-id="4d6b4-115">Возвращает тип-примитив `ICorDebugValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="4d6b4-115">Gets the primitive type of this `ICorDebugValue` object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d6b4-116">Примечания</span><span class="sxs-lookup"><span data-stu-id="4d6b4-116">Remarks</span></span>  
 <span data-ttu-id="4d6b4-117">Как правило владение объектом значение передается при возврате.</span><span class="sxs-lookup"><span data-stu-id="4d6b4-117">In general, ownership of a value object is passed when it is returned.</span></span> <span data-ttu-id="4d6b4-118">Получатель отвечает за удаление ссылки из объекта при его завершении с объектом.</span><span class="sxs-lookup"><span data-stu-id="4d6b4-118">The recipient is responsible for removing a reference from the object when it is finished with the object.</span></span>  
  
 <span data-ttu-id="4d6b4-119">В зависимости от того, где значение было получено путем значение может оказаться недействительным после возобновления процесса.</span><span class="sxs-lookup"><span data-stu-id="4d6b4-119">Depending on where the value was retrieved from, the value may not remain valid after the process is resumed.</span></span> <span data-ttu-id="4d6b4-120">Таким образом, как правило, значения не должны храниться во время вызова из [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="4d6b4-120">So, in general, the value shouldn't be held across a call of the [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4d6b4-121">Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.</span><span class="sxs-lookup"><span data-stu-id="4d6b4-121">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d6b4-122">Требования</span><span class="sxs-lookup"><span data-stu-id="4d6b4-122">Requirements</span></span>  
 <span data-ttu-id="4d6b4-123">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d6b4-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d6b4-124">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4d6b4-124">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4d6b4-125">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4d6b4-125">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4d6b4-126">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d6b4-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d6b4-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4d6b4-127">See Also</span></span>  
    
    
    
    
 [<span data-ttu-id="4d6b4-128">Интерфейс ICorDebugValue3</span><span class="sxs-lookup"><span data-stu-id="4d6b4-128">ICorDebugValue3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [<span data-ttu-id="4d6b4-129">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="4d6b4-129">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
