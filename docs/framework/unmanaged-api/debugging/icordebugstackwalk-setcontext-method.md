---
title: Метод ICorDebugStackWalk::SetContext
ms.date: 03/30/2017
api_name:
- ICorDebugStackWalk.SetContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStackWalk::SetContext
helpviewer_keywords:
- SetContext method [.NET Framework debugging]
- ICorDebugStackWalk::SetContext method [.NET Framework debugging]
ms.assetid: bac0b156-31a3-4e7f-be4d-ab21789c81f1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3bbd215b2fefc662da4867a0a8700ca130c4e14c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57470196"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="0cd1c-102">Метод ICorDebugStackWalk::SetContext</span><span class="sxs-lookup"><span data-stu-id="0cd1c-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="0cd1c-103">Наборы [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) текущего контекста объекта для допустимого контекста потока.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-103">Sets the [ICorDebugStackWalk](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0cd1c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0cd1c-104">Syntax</span></span>  
  
```  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0cd1c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0cd1c-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="0cd1c-106">[in] Объект [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) флаг, указывающий контекста: взят из активного кадра в стеке или получить контекст путем очистки стека.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-106">[in] A [CorDebugSetContextFlag](../../../../docs/framework/unmanaged-api/debugging/cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="0cd1c-107">[in] Выделенный размер `CONTEXT` буфера.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="0cd1c-108">[in] `CONTEXT` Буфера.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0cd1c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0cd1c-109">Return Value</span></span>  
 <span data-ttu-id="0cd1c-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0cd1c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0cd1c-111">HRESULT</span></span>|<span data-ttu-id="0cd1c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0cd1c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0cd1c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0cd1c-113">S_OK</span></span>|<span data-ttu-id="0cd1c-114">`ICorDebugStackWalk` Был успешно задан контекст объекта.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="0cd1c-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0cd1c-115">E_FAIL</span></span>|<span data-ttu-id="0cd1c-116">`ICorDebugStackWalk` Контекст объекта не задано.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="0cd1c-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="0cd1c-117">E_INVALIDARG</span></span>|<span data-ttu-id="0cd1c-118">Контекст имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-118">The context is null.</span></span>|  
|<span data-ttu-id="0cd1c-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="0cd1c-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="0cd1c-120">Буфер контекста слишком мал.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="0cd1c-121">Исключения</span><span class="sxs-lookup"><span data-stu-id="0cd1c-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0cd1c-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="0cd1c-122">Remarks</span></span>  
 <span data-ttu-id="0cd1c-123">Этот метод не изменяет контекст текущего потока.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="0cd1c-124">Установка на недопустимый контекст для текущего контекста может привести к непредсказуемым результатам при обходе стека.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="0cd1c-125">Побитовое точную копию данного контекста можно получить путем вызова [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="0cd1c-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0cd1c-126">Требования</span><span class="sxs-lookup"><span data-stu-id="0cd1c-126">Requirements</span></span>  
 <span data-ttu-id="0cd1c-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0cd1c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0cd1c-128">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0cd1c-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0cd1c-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0cd1c-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0cd1c-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cd1c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0cd1c-131">См. также</span><span class="sxs-lookup"><span data-stu-id="0cd1c-131">See also</span></span>
- [<span data-ttu-id="0cd1c-132">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="0cd1c-132">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="0cd1c-133">Отладка</span><span class="sxs-lookup"><span data-stu-id="0cd1c-133">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
