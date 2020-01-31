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
ms.openlocfilehash: 3eace2d91b3bb6e637a659b8b49a31450ebc2c42
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783719"
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="d678d-102">Метод ICorDebugDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="d678d-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="d678d-103">Возвращает текущий контекст потока для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="d678d-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d678d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d678d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d678d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d678d-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="d678d-106">окне Идентификатор потока, контекст которого должен быть получен.</span><span class="sxs-lookup"><span data-stu-id="d678d-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="d678d-107">Идентификатор определяется операционной системой.</span><span class="sxs-lookup"><span data-stu-id="d678d-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="d678d-108">окне Побитовое сочетание флагов, зависящих от платформы, которые указывают, какие части контекста должны считываться.</span><span class="sxs-lookup"><span data-stu-id="d678d-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="d678d-109">[входной] Размер `pContext`.</span><span class="sxs-lookup"><span data-stu-id="d678d-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="d678d-110">заполняет Буфер, в котором будет храниться контекст потока.</span><span class="sxs-lookup"><span data-stu-id="d678d-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d678d-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="d678d-111">Remarks</span></span>  
 <span data-ttu-id="d678d-112">На платформах Windows `pContext` должен быть структурой `CONTEXT` (определенной в WinNT. h), подходящей для типа компьютера, указанного в методе [ICorDebugDataTarget::-Platform](icordebugdatatarget-getplatform-method.md) .</span><span class="sxs-lookup"><span data-stu-id="d678d-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="d678d-113">`contextFlags` должны иметь те же значения, что и поле `ContextFlags` структуры `CONTEXT`.</span><span class="sxs-lookup"><span data-stu-id="d678d-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="d678d-114">Структура `CONTEXT` зависит от процессора; Дополнительные сведения см. в файле WinNT. h.</span><span class="sxs-lookup"><span data-stu-id="d678d-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d678d-115">Требования</span><span class="sxs-lookup"><span data-stu-id="d678d-115">Requirements</span></span>  
 <span data-ttu-id="d678d-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d678d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d678d-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d678d-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d678d-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d678d-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d678d-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d678d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d678d-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="d678d-120">See also</span></span>

- [<span data-ttu-id="d678d-121">Интерфейс ICorDebugDataTarget</span><span class="sxs-lookup"><span data-stu-id="d678d-121">ICorDebugDataTarget Interface</span></span>](icordebugdatatarget-interface.md)
- [<span data-ttu-id="d678d-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="d678d-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="d678d-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="d678d-123">Debugging</span></span>](index.md)
