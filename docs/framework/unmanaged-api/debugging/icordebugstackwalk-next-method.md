---
title: Метод ICorDebugStackWalk::Next
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.Next Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::Next
helpviewer_keywords:
- ICorDebugStackWalk::Next method [.NET Framework debugging]
- Next method, ICorDebugStackWalk interface [.NET Framework debugging]
ms.assetid: 189c36be-028c-4fba-a002-5edfb8fcd07f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 724db50285532c20132fbfd5262df26227db6742
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59130030"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="161c2-102">Метод ICorDebugStackWalk::Next</span><span class="sxs-lookup"><span data-stu-id="161c2-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="161c2-103">Перемещает [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) объекта следующий кадр.</span><span class="sxs-lookup"><span data-stu-id="161c2-103">Moves the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="161c2-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="161c2-104">Syntax</span></span>  
  
```  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="161c2-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="161c2-105">Return Value</span></span>  
 <span data-ttu-id="161c2-106">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="161c2-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="161c2-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="161c2-107">HRESULT</span></span>|<span data-ttu-id="161c2-108">Описание</span><span class="sxs-lookup"><span data-stu-id="161c2-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="161c2-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="161c2-109">S_OK</span></span>|<span data-ttu-id="161c2-110">Среда выполнения успешно развернута на следующий кадр (см. в разделе "Примечания").</span><span class="sxs-lookup"><span data-stu-id="161c2-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="161c2-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="161c2-111">E_FAIL</span></span>|<span data-ttu-id="161c2-112">`ICorDebugStackWalk` Не удалось перевести объект.</span><span class="sxs-lookup"><span data-stu-id="161c2-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="161c2-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="161c2-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="161c2-114">В результате разворачивания достигнут конец стека.</span><span class="sxs-lookup"><span data-stu-id="161c2-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="161c2-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="161c2-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="161c2-116">Указатель кадра уже находится в конце стека; Таким образом может осуществляться без дополнительных кадров.</span><span class="sxs-lookup"><span data-stu-id="161c2-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="161c2-117">Исключения</span><span class="sxs-lookup"><span data-stu-id="161c2-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="161c2-118">Примечания</span><span class="sxs-lookup"><span data-stu-id="161c2-118">Remarks</span></span>  
 <span data-ttu-id="161c2-119">`Next` Метод перемещает `ICorDebugStackWalk` объекта вызывающий кадр только в том случае, если среда выполнения может развернуть текущего кадра.</span><span class="sxs-lookup"><span data-stu-id="161c2-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="161c2-120">В противном случае этот объект перемещается к следующему кадру, который среда выполнения может развернуть.</span><span class="sxs-lookup"><span data-stu-id="161c2-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="161c2-121">Требования</span><span class="sxs-lookup"><span data-stu-id="161c2-121">Requirements</span></span>  
 <span data-ttu-id="161c2-122">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="161c2-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="161c2-123">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="161c2-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="161c2-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="161c2-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="161c2-125">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="161c2-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="161c2-126">См. также</span><span class="sxs-lookup"><span data-stu-id="161c2-126">See also</span></span>

- [<span data-ttu-id="161c2-127">Интерфейс ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="161c2-127">ICorDebugStackWalk Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md)
- [<span data-ttu-id="161c2-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="161c2-128">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="161c2-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="161c2-129">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
