---
title: Метод ICorDebugDataTarget::GetThreadContext
ms.date: 03/30/2017
api_name:
- ICorDebugDataTarget.GetThreadContext Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type:
- apiref
ms.openlocfilehash: 278320391615eddaa8ba878ef87f802f30cddb95
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122029"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="11d47-102">Метод ICorDebugDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="11d47-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="11d47-103">Возвращает текущий контекст потока для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="11d47-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11d47-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="11d47-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11d47-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="11d47-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="11d47-106">окне Идентификатор потока, контекст которого должен быть получен.</span><span class="sxs-lookup"><span data-stu-id="11d47-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="11d47-107">Идентификатор определяется операционной системой.</span><span class="sxs-lookup"><span data-stu-id="11d47-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="11d47-108">окне Побитовое сочетание флагов, зависящих от платформы, которые указывают, какие части контекста должны считываться.</span><span class="sxs-lookup"><span data-stu-id="11d47-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="11d47-109">[входной] Размер `pContext`.</span><span class="sxs-lookup"><span data-stu-id="11d47-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="11d47-110">заполняет Буфер, в котором будет храниться контекст потока.</span><span class="sxs-lookup"><span data-stu-id="11d47-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11d47-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="11d47-111">Remarks</span></span>  
 <span data-ttu-id="11d47-112">На платформах Windows `pContext` должен быть структурой `CONTEXT` (определенной в WinNT. h), подходящей для типа компьютера, указанного в методе [ICorDebugDataTarget::-Platform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="11d47-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="11d47-113">`contextFlags` должны иметь те же значения, что и поле `ContextFlags` структуры `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="11d47-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="11d47-114">Структура `CONTEXT` зависит от процессора; Дополнительные сведения см. в файле WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="11d47-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11d47-115">Требования</span><span class="sxs-lookup"><span data-stu-id="11d47-115">Requirements</span></span>  
 <span data-ttu-id="11d47-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11d47-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11d47-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="11d47-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="11d47-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="11d47-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="11d47-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11d47-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11d47-120">См. также</span><span class="sxs-lookup"><span data-stu-id="11d47-120">See also</span></span>

- [<span data-ttu-id="11d47-121">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="11d47-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="11d47-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="11d47-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="11d47-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="11d47-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
