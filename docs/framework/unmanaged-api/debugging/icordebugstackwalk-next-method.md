---
title: "Метод ICorDebugStackWalk::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStackWalk.Next Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 781998c9688dc60eec171068b50f432720ee0fdd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="7487e-102">Метод ICorDebugStackWalk::Next</span><span class="sxs-lookup"><span data-stu-id="7487e-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="7487e-103">Перемещает [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) объекта следующий кадр.</span><span class="sxs-lookup"><span data-stu-id="7487e-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7487e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7487e-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="7487e-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="7487e-105">Return Value</span></span>  
 <span data-ttu-id="7487e-106">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="7487e-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="7487e-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7487e-107">HRESULT</span></span>|<span data-ttu-id="7487e-108">Описание</span><span class="sxs-lookup"><span data-stu-id="7487e-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7487e-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="7487e-109">S_OK</span></span>|<span data-ttu-id="7487e-110">Среда выполнения успешно развернута на следующий кадр (см. примечания).</span><span class="sxs-lookup"><span data-stu-id="7487e-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="7487e-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="7487e-111">E_FAIL</span></span>|<span data-ttu-id="7487e-112">`ICorDebugStackWalk` Не удалось перевести объект.</span><span class="sxs-lookup"><span data-stu-id="7487e-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="7487e-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="7487e-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="7487e-114">В результате разворачивания достигнут конец стека.</span><span class="sxs-lookup"><span data-stu-id="7487e-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="7487e-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="7487e-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="7487e-116">Указатель кадра уже находится в конце стека; Таким образом может осуществляться без дополнительных кадров.</span><span class="sxs-lookup"><span data-stu-id="7487e-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="7487e-117">Исключения</span><span class="sxs-lookup"><span data-stu-id="7487e-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7487e-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="7487e-118">Remarks</span></span>  
 <span data-ttu-id="7487e-119">`Next` Усовершенствованные метод `ICorDebugStackWalk` объекта вызывающий кадр только в том случае, если среда выполнения может развернуть текущий кадр.</span><span class="sxs-lookup"><span data-stu-id="7487e-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="7487e-120">В противном случае этот объект перемещается на следующий кадр, который среда выполнения может развернуть.</span><span class="sxs-lookup"><span data-stu-id="7487e-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7487e-121">Требования</span><span class="sxs-lookup"><span data-stu-id="7487e-121">Requirements</span></span>  
 <span data-ttu-id="7487e-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7487e-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7487e-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7487e-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7487e-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7487e-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7487e-125">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7487e-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7487e-126">См. также</span><span class="sxs-lookup"><span data-stu-id="7487e-126">See Also</span></span>  
 [<span data-ttu-id="7487e-127">ICorDebugStackWalk-интерфейс</span><span class="sxs-lookup"><span data-stu-id="7487e-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)  
 [<span data-ttu-id="7487e-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="7487e-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="7487e-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="7487e-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
