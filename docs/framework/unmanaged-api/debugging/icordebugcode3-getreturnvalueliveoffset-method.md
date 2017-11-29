---
title: "Метод ICorDebugCode3::GetReturnValueLiveOffset"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICorDebugCode3.GetReturnValueLiveOffset
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4516f2244b72bd4f254c5090b09d6d90579f1ae6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="d462e-102">Метод ICorDebugCode3::GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="d462e-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="d462e-103">Для заданного смещения IL возвращает собственные смещения, где разместить точку останова, чтобы отладчик можно получить возвращаемое значение из функции.</span><span class="sxs-lookup"><span data-stu-id="d462e-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d462e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d462e-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d462e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="d462e-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="d462e-106">Смещение на промежуточном Языке.</span><span class="sxs-lookup"><span data-stu-id="d462e-106">The IL offset.</span></span> <span data-ttu-id="d462e-107">Он должен быть место вызова функции или функции вызов завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="d462e-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="d462e-108">Число байтов, доступных для хранения `pOffsets`.</span><span class="sxs-lookup"><span data-stu-id="d462e-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="d462e-109">Указатель на число фактически извлеченных смещений.</span><span class="sxs-lookup"><span data-stu-id="d462e-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="d462e-110">Обычно его значение равно 1, но одной инструкции IL можно сопоставить с несколькими `CALL` инструкции ассемблера.</span><span class="sxs-lookup"><span data-stu-id="d462e-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="d462e-111">Массив из машинного кода.</span><span class="sxs-lookup"><span data-stu-id="d462e-111">An array of native offsets.</span></span> <span data-ttu-id="d462e-112">Как правило `pOffsets` содержит один смещение, несмотря на то, что можно сопоставить несколько карты к нескольким одной инструкции IL `CALL` инструкции ассемблера.</span><span class="sxs-lookup"><span data-stu-id="d462e-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d462e-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="d462e-113">Remarks</span></span>  
 <span data-ttu-id="d462e-114">Этот метод используется вместе с [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) метод для получения возвращаемого значения метода, который возвращает ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="d462e-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="d462e-115">Передача IL смещение к место вызова функции в этот метод возвращает один или несколько собственные смещения.</span><span class="sxs-lookup"><span data-stu-id="d462e-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="d462e-116">Затем отладчик можно установить точки останова на этих смещениях машинного кода в функцию.</span><span class="sxs-lookup"><span data-stu-id="d462e-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="d462e-117">Если отладчик обнаруживает одной из точек останова, затем можно передать одинаковое смещение IL, который передан в этот метод, чтобы [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) метод для получения возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="d462e-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="d462e-118">Отладчик должен выполнить очистку все точки останова, которые оно задано.</span><span class="sxs-lookup"><span data-stu-id="d462e-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="d462e-119">`ICorDebugCode3::GetReturnValueLiveOffset` И [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) методы позволяют получить сведения о возвращаемых значениях только для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="d462e-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="d462e-120">Получение сведений о возвращаемое значение от типов значений (то есть, все типы, производные от <xref:System.ValueType>) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="d462e-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="d462e-121">Функция возвращает `HRESULT` значений, приведенных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d462e-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="d462e-122">Значение `HRESULT`</span><span class="sxs-lookup"><span data-stu-id="d462e-122">`HRESULT` value</span></span>|<span data-ttu-id="d462e-123">Описание</span><span class="sxs-lookup"><span data-stu-id="d462e-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="d462e-124">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="d462e-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="d462e-125">Данного сайта смещении IL не инструкцию вызова или возвращаемого функцией `void`.</span><span class="sxs-lookup"><span data-stu-id="d462e-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="d462e-126">С указанным смещением IL-код — это правильный вызов, но тип возвращаемого значения не поддерживается для получения возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="d462e-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="d462e-127">`ICorDebugCode3::GetReturnValueLiveOffset` Метод доступен только для x86 86 и AMD64 систем.</span><span class="sxs-lookup"><span data-stu-id="d462e-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d462e-128">Требования</span><span class="sxs-lookup"><span data-stu-id="d462e-128">Requirements</span></span>  
 <span data-ttu-id="d462e-129">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d462e-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d462e-130">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d462e-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d462e-131">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d462e-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d462e-132">**Версии платформы .NET framework:**[!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d462e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d462e-133">См. также</span><span class="sxs-lookup"><span data-stu-id="d462e-133">See Also</span></span>  
 [<span data-ttu-id="d462e-134">Метод GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="d462e-134">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)  
 [<span data-ttu-id="d462e-135">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="d462e-135">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
