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
ms.openlocfilehash: 23ad8882ad97e5ceaeb690dfae08a6be55b85f64
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791857"
---
# <a name="icordebugstackwalksetcontext-method"></a><span data-ttu-id="a566c-102">Метод ICorDebugStackWalk::SetContext</span><span class="sxs-lookup"><span data-stu-id="a566c-102">ICorDebugStackWalk::SetContext Method</span></span>
<span data-ttu-id="a566c-103">Задает для текущего контекста объекта [икордебугстакквалк](icordebugstackwalk-interface.md) допустимый контекст для потока.</span><span class="sxs-lookup"><span data-stu-id="a566c-103">Sets the [ICorDebugStackWalk](icordebugstackwalk-interface.md) object’s current context to a valid context for the thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a566c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a566c-104">Syntax</span></span>  
  
```cpp  
HRESULT SetContext([in] CorDebugSetContextFlag flag,  
                   [in] ULONG32 contextSize,  
                   [in, size_is(contextSize)] BYTE context[]);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a566c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a566c-105">Parameters</span></span>  
 `flag`  
 <span data-ttu-id="a566c-106">окне Флаг [кордебугсетконтекстфлаг](cordebugsetcontextflag-enumeration.md) , который указывает, относится ли контекст к активному кадру в стеке или к контексту, полученному путем очистки стека.</span><span class="sxs-lookup"><span data-stu-id="a566c-106">[in] A [CorDebugSetContextFlag](cordebugsetcontextflag-enumeration.md) flag that indicates whether the context is from the active frame on the stack, or a context obtained by unwinding the stack.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="a566c-107">окне Выделенный размер буфера `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="a566c-107">[in] The allocated size of the `CONTEXT` buffer.</span></span>  
  
 `context`  
 <span data-ttu-id="a566c-108">окне Буфер `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="a566c-108">[in] The `CONTEXT` buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a566c-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a566c-109">Return Value</span></span>  
 <span data-ttu-id="a566c-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="a566c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="a566c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a566c-111">HRESULT</span></span>|<span data-ttu-id="a566c-112">Описание</span><span class="sxs-lookup"><span data-stu-id="a566c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a566c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="a566c-113">S_OK</span></span>|<span data-ttu-id="a566c-114">Контекст объекта `ICorDebugStackWalk` был успешно задан.</span><span class="sxs-lookup"><span data-stu-id="a566c-114">The `ICorDebugStackWalk` object's context was successfully set.</span></span>|  
|<span data-ttu-id="a566c-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a566c-115">E_FAIL</span></span>|<span data-ttu-id="a566c-116">Контекст объекта `ICorDebugStackWalk` не задан.</span><span class="sxs-lookup"><span data-stu-id="a566c-116">The `ICorDebugStackWalk` object's context was not set.</span></span>|  
|<span data-ttu-id="a566c-117">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="a566c-117">E_INVALIDARG</span></span>|<span data-ttu-id="a566c-118">Контекст имеет значение null.</span><span class="sxs-lookup"><span data-stu-id="a566c-118">The context is null.</span></span>|  
|<span data-ttu-id="a566c-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span><span class="sxs-lookup"><span data-stu-id="a566c-119">HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)</span></span>|<span data-ttu-id="a566c-120">Буфер контекста слишком мал.</span><span class="sxs-lookup"><span data-stu-id="a566c-120">The context buffer is too small.</span></span>|  
  
## <a name="exceptions"></a><span data-ttu-id="a566c-121">Исключения</span><span class="sxs-lookup"><span data-stu-id="a566c-121">Exceptions</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a566c-122">Заметки</span><span class="sxs-lookup"><span data-stu-id="a566c-122">Remarks</span></span>  
 <span data-ttu-id="a566c-123">Этот метод не изменяет текущий контекст потока.</span><span class="sxs-lookup"><span data-stu-id="a566c-123">This method does not alter the current context of the thread.</span></span>  
  
 <span data-ttu-id="a566c-124">Установка текущего контекста в недопустимый контекст может привести к непредсказуемым результатам обхода стека.</span><span class="sxs-lookup"><span data-stu-id="a566c-124">Setting the current context to an invalid context may cause unpredictable results from the stack walker.</span></span>  
  
 <span data-ttu-id="a566c-125">Вы можете получить точную побитовую копию этого контекста путем немедленного вызова метода [икордебугстакквалк:: oncontext](icordebugstackwalk-getcontext-method.md) .</span><span class="sxs-lookup"><span data-stu-id="a566c-125">You can retrieve an exact bitwise copy of this context by immediately calling the [ICorDebugStackWalk::GetContext](icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a566c-126">Требования</span><span class="sxs-lookup"><span data-stu-id="a566c-126">Requirements</span></span>  
 <span data-ttu-id="a566c-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a566c-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a566c-128">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a566c-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a566c-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a566c-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a566c-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a566c-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a566c-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="a566c-131">See also</span></span>

- [<span data-ttu-id="a566c-132">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="a566c-132">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="a566c-133">Отладка</span><span class="sxs-lookup"><span data-stu-id="a566c-133">Debugging</span></span>](index.md)
