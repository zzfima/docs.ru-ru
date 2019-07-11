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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2047929c52dbb7b0d780a4ea0f180bae48a3ce79
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750393"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="6008e-102">Метод ICorDebugDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="6008e-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="6008e-103">Возвращает текущий контекст потока для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="6008e-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6008e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6008e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6008e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6008e-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="6008e-106">[in] Идентификатор потока, является контекст которого требуется получить.</span><span class="sxs-lookup"><span data-stu-id="6008e-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="6008e-107">Идентификатор определяется операционной системой.</span><span class="sxs-lookup"><span data-stu-id="6008e-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="6008e-108">[in] Побитовое сочетание флагов зависят от платформы, которые указывают, какие части контекста следует рассматривать только.</span><span class="sxs-lookup"><span data-stu-id="6008e-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="6008e-109">[входной] Размер `pContext`.</span><span class="sxs-lookup"><span data-stu-id="6008e-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="6008e-110">[out] Буфер, где будет храниться контекст потока.</span><span class="sxs-lookup"><span data-stu-id="6008e-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6008e-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="6008e-111">Remarks</span></span>  
 <span data-ttu-id="6008e-112">На платформах Windows `pContext` должно быть `CONTEXT` структуры (определяется в заголовке WinNT.h), подходящий для типа компьютера, заданного параметром [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="6008e-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="6008e-113">`contextFlags` должен иметь те же значения, что `ContextFlags` поле `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="6008e-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="6008e-114">`CONTEXT` Структуры зависит от процессора; см. Дополнительные сведения см.</span><span class="sxs-lookup"><span data-stu-id="6008e-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6008e-115">Требования</span><span class="sxs-lookup"><span data-stu-id="6008e-115">Requirements</span></span>  
 <span data-ttu-id="6008e-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6008e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6008e-117">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6008e-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6008e-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6008e-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6008e-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6008e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6008e-120">См. также</span><span class="sxs-lookup"><span data-stu-id="6008e-120">See also</span></span>

- [<span data-ttu-id="6008e-121">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="6008e-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)
- [<span data-ttu-id="6008e-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="6008e-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="6008e-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="6008e-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
