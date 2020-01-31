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
ms.openlocfilehash: b76d17337408653d130ee0cb8594e759bdade37c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791869"
---
# <a name="icordebugstackwalknext-method"></a><span data-ttu-id="a7eed-102">Метод ICorDebugStackWalk::Next</span><span class="sxs-lookup"><span data-stu-id="a7eed-102">ICorDebugStackWalk::Next Method</span></span>
<span data-ttu-id="a7eed-103">Перемещает объект [икордебугстакквалк](icordebugstackwalk-interface.md) в следующий кадр.</span><span class="sxs-lookup"><span data-stu-id="a7eed-103">Moves the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object to the next frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7eed-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a7eed-104">Syntax</span></span>  
  
```cpp  
HRESULT Next();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a7eed-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a7eed-105">Return Value</span></span>  
 <span data-ttu-id="a7eed-106">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="a7eed-106">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a7eed-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7eed-107">HRESULT</span></span>|<span data-ttu-id="a7eed-108">Описание</span><span class="sxs-lookup"><span data-stu-id="a7eed-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7eed-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7eed-109">S_OK</span></span>|<span data-ttu-id="a7eed-110">Среда выполнения успешно развернута до следующего кадра (см. примечания).</span><span class="sxs-lookup"><span data-stu-id="a7eed-110">The runtime successfully unwound to the next frame (see Remarks).</span></span>|  
|<span data-ttu-id="a7eed-111">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a7eed-111">E_FAIL</span></span>|<span data-ttu-id="a7eed-112">Объект `ICorDebugStackWalk` не может быть расширен.</span><span class="sxs-lookup"><span data-stu-id="a7eed-112">The `ICorDebugStackWalk` object could not be advanced.</span></span>|  
|<span data-ttu-id="a7eed-113">CORDBG_S_AT_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="a7eed-113">CORDBG_S_AT_END_OF_STACK</span></span>|<span data-ttu-id="a7eed-114">В результате этого очистки достигнут конец стека.</span><span class="sxs-lookup"><span data-stu-id="a7eed-114">The end of the stack was reached as a result of this unwind.</span></span>|  
|<span data-ttu-id="a7eed-115">CORDBG_E_PAST_END_OF_STACK</span><span class="sxs-lookup"><span data-stu-id="a7eed-115">CORDBG_E_PAST_END_OF_STACK</span></span>|<span data-ttu-id="a7eed-116">Указатель фрейма уже находится в конце стека; Поэтому доступ к дополнительным кадрам невозможен.</span><span class="sxs-lookup"><span data-stu-id="a7eed-116">The frame pointer is already at the end of the stack; therefore, no additional frames can be accessed.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a7eed-117">Исключения</span><span class="sxs-lookup"><span data-stu-id="a7eed-117">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7eed-118">Заметки</span><span class="sxs-lookup"><span data-stu-id="a7eed-118">Remarks</span></span>  
 <span data-ttu-id="a7eed-119">Метод `Next` перемещает объект `ICorDebugStackWalk` в вызывающий кадр только в том случае, если среда выполнения может очистить текущий кадр.</span><span class="sxs-lookup"><span data-stu-id="a7eed-119">The `Next` method advances the `ICorDebugStackWalk` object to the calling frame only if the runtime can unwind the current frame.</span></span> <span data-ttu-id="a7eed-120">В противном случае объект переходит к следующему кадру, который среда выполнения может очистить.</span><span class="sxs-lookup"><span data-stu-id="a7eed-120">Otherwise, the object advances to the next frame that the runtime is able to unwind.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7eed-121">Требования</span><span class="sxs-lookup"><span data-stu-id="a7eed-121">Requirements</span></span>  
 <span data-ttu-id="a7eed-122">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7eed-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7eed-123">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7eed-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7eed-124">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7eed-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7eed-125">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7eed-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7eed-126">См. также:</span><span class="sxs-lookup"><span data-stu-id="a7eed-126">See also</span></span>

- [<span data-ttu-id="a7eed-127">Интерфейс ICorDebugStackWalk</span><span class="sxs-lookup"><span data-stu-id="a7eed-127">ICorDebugStackWalk Interface</span></span>](icordebugstackwalk-interface.md)
- [<span data-ttu-id="a7eed-128">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a7eed-128">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a7eed-129">Отладка</span><span class="sxs-lookup"><span data-stu-id="a7eed-129">Debugging</span></span>](index.md)
