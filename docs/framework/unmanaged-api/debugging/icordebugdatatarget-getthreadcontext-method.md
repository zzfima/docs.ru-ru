---
title: "Метод ICorDebugDataTarget::GetThreadContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugDataTarget.GetThreadContext Method
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugDataTarget::GetThreadContext
helpviewer_keywords:
- ICorDebugDataTarget::GetThreadContext method [.NET Framework debugging]
- GetThreadContext method, ICorDebugDataTarget interface [.NET Framework debugging]
ms.assetid: c8954268-1821-4b23-b665-dbb55f2af31b
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 543956bb42d7477456426d7327f14b059b23d759
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugdatatargetgetthreadcontext-method"></a><span data-ttu-id="dd72f-102">Метод ICorDebugDataTarget::GetThreadContext</span><span class="sxs-lookup"><span data-stu-id="dd72f-102">ICorDebugDataTarget::GetThreadContext Method</span></span>
<span data-ttu-id="dd72f-103">Возвращает текущий контекст потока для указанного потока.</span><span class="sxs-lookup"><span data-stu-id="dd72f-103">Returns the current thread context for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd72f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd72f-104">Syntax</span></span>  
  
```  
HRESULT GetThreadContext(  
       [in] DWORD dwThreadID,  
       [in] ULONG32 contextFlags,  
       [in] ULONG32 contextSize,  
       [out, size_is(contextSize)] BYTE * pContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="dd72f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd72f-105">Parameters</span></span>  
 `dwThreadID`  
 <span data-ttu-id="dd72f-106">[in] Идентификатор потока, контекст которого требуется получить.</span><span class="sxs-lookup"><span data-stu-id="dd72f-106">[in] The identifier of the thread whose context is to be retrieved.</span></span> <span data-ttu-id="dd72f-107">Идентификатор определяется операционной системой.</span><span class="sxs-lookup"><span data-stu-id="dd72f-107">The identifier is defined by the operating system.</span></span>  
  
 `contextFlags`  
 <span data-ttu-id="dd72f-108">[in] Побитовое сочетание флагов зависят от платформы, которые указывают, какие части контекста следует прочесть.</span><span class="sxs-lookup"><span data-stu-id="dd72f-108">[in] A bitwise combination of platform-dependent flags that indicate which portions of the context should be read.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="dd72f-109">[входной] Размер `pContext`.</span><span class="sxs-lookup"><span data-stu-id="dd72f-109">[in] The size of `pContext`.</span></span>  
  
 `pContext`  
 <span data-ttu-id="dd72f-110">[out] Буфер, в которой будет храниться контекст потока.</span><span class="sxs-lookup"><span data-stu-id="dd72f-110">[out] The buffer where the thread context will be stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="dd72f-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="dd72f-111">Remarks</span></span>  
 <span data-ttu-id="dd72f-112">На платформах Windows `pContext` должно быть `CONTEXT` структуры (определенный в заголовке WinNT.h), соответствующий тип компьютера, указанный в [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="dd72f-112">On Windows platforms, `pContext` must be a `CONTEXT` structure (defined in WinNT.h) that is appropriate for the machine type specified by the [ICorDebugDataTarget::GetPlatform](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-getplatform-method.md) method.</span></span> <span data-ttu-id="dd72f-113">`contextFlags`должен иметь те же значения, что `ContextFlags` поле `CONTEXT` структуры.</span><span class="sxs-lookup"><span data-stu-id="dd72f-113">`contextFlags` must have the same values as the `ContextFlags` field of the `CONTEXT` structure.</span></span> <span data-ttu-id="dd72f-114">`CONTEXT` Структуры зависит от процессора; Дополнительные сведения о файле WinNT.h.</span><span class="sxs-lookup"><span data-stu-id="dd72f-114">The `CONTEXT` structure is processor-specific; refer to the WinNT.h file for details.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd72f-115">Требования</span><span class="sxs-lookup"><span data-stu-id="dd72f-115">Requirements</span></span>  
 <span data-ttu-id="dd72f-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd72f-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd72f-117">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd72f-117">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd72f-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd72f-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd72f-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd72f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd72f-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dd72f-120">See Also</span></span>  
 [<span data-ttu-id="dd72f-121">ICorDebugDataTarget-интерфейс</span><span class="sxs-lookup"><span data-stu-id="dd72f-121">ICorDebugDataTarget Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugdatatarget-interface.md)  
 [<span data-ttu-id="dd72f-122">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="dd72f-122">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="dd72f-123">Отладка</span><span class="sxs-lookup"><span data-stu-id="dd72f-123">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
