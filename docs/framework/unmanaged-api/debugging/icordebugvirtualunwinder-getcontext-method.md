---
title: "Метод ICorDebugVirtualUnwinder::GetContext"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fe502a76-3068-47e5-a0a0-85ccb72dfac3
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 45a914005e84d33b39d72fce96679e275b921d3c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugvirtualunwindergetcontext-method"></a><span data-ttu-id="f0f6a-102">Метод ICorDebugVirtualUnwinder::GetContext</span><span class="sxs-lookup"><span data-stu-id="f0f6a-102">ICorDebugVirtualUnwinder::GetContext Method</span></span>
<span data-ttu-id="f0f6a-103">Получает текущий контекст этого средства очистки.</span><span class="sxs-lookup"><span data-stu-id="f0f6a-103">Gets the current context of this unwinder.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0f6a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f0f6a-104">Syntax</span></span>  
  
```  
HRESULT GetContext(  
   [in] ULONG32 contextFlags,  
   [in] ULONG32 cbContextBuf,  
   [out] ULONG32* contextSize,  
   [out, size_is(cbContextBuf)] BYTE contextBuf[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f0f6a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f0f6a-105">Parameters</span></span>  
 `contextFlags`  
 <span data-ttu-id="f0f6a-106">[in] Флаги, указывающие, какие части контекста следует возвращать (определенные в заголовке WinNt.h).</span><span class="sxs-lookup"><span data-stu-id="f0f6a-106">[in] Flags that specify which parts of the context to return (defined in WinNT.h).</span></span>  
  
 `cbContextBuf`  
 <span data-ttu-id="f0f6a-107">[in] Количество байтов в `contextBuf`.</span><span class="sxs-lookup"><span data-stu-id="f0f6a-107">[in] The number of bytes in `contextBuf`.</span></span>  
  
 `contextSize`  
 <span data-ttu-id="f0f6a-108">[out] Указатель на число байтов, фактически записанных в `contextBuf`.</span><span class="sxs-lookup"><span data-stu-id="f0f6a-108">[out] A pointer to the number of bytes actually written to `contextBuf`.</span></span>  
  
 `contextBuf`  
 <span data-ttu-id="f0f6a-109">[out] Байтовый массив, содержащий текущий контекст этого средства очистки.</span><span class="sxs-lookup"><span data-stu-id="f0f6a-109">[out] A byte array that contains the current context of this unwinder.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f0f6a-110">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="f0f6a-110">Return Value</span></span>  
 <span data-ttu-id="f0f6a-111">Любое ошибочное значение HRESULT , полученное процессом mscordbi, считается неустранимым и приводит к возврату интерфейсами API ICorDebug значения `CORDBG_E_DATA_TARGET_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="f0f6a-111">Any failing HRESULT value received by mscordbi is considered fatal and will cause ICorDebug APIs to return `CORDBG_E_DATA_TARGET_ERROR`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0f6a-112">Примечания</span><span class="sxs-lookup"><span data-stu-id="f0f6a-112">Remarks</span></span>  
 <span data-ttu-id="f0f6a-113">Задайте начальное значение `contextBuf` аргумент буфер контекста, возвращенный при вызове [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="f0f6a-113">You set the initial value of the `contextBuf` argument to the context buffer returned by calling the [ICorDebugStackWalk::GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugstackwalk-getcontext-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f0f6a-114">Этот метод доступен только в машинном коде .NET.</span><span class="sxs-lookup"><span data-stu-id="f0f6a-114">This method is available with .NET Native only.</span></span>  
  
 <span data-ttu-id="f0f6a-115">Поскольку очистка может восстановить только подмножество регистров, например только неизменяемые регистры, контекст может не соответствовать в точности состоянию регистра во время фактического вызова метода.</span><span class="sxs-lookup"><span data-stu-id="f0f6a-115">Because unwinding may only restore a subset of the registers, such as the non-volatile registers only, the context may not exactly match the register state at the time of the actual method call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0f6a-116">Требования</span><span class="sxs-lookup"><span data-stu-id="f0f6a-116">Requirements</span></span>  
 <span data-ttu-id="f0f6a-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f0f6a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0f6a-118">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0f6a-118">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0f6a-119">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0f6a-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0f6a-120">**Версии платформы .NET framework:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0f6a-120">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f6a-121">См. также</span><span class="sxs-lookup"><span data-stu-id="f0f6a-121">See Also</span></span>  
 [<span data-ttu-id="f0f6a-122">Интерфейс ICorDebugMemoryBuffer</span><span class="sxs-lookup"><span data-stu-id="f0f6a-122">ICorDebugMemoryBuffer Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md)  
 [<span data-ttu-id="f0f6a-123">Интерфейсы отладки</span><span class="sxs-lookup"><span data-stu-id="f0f6a-123">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
