---
title: Метод ICorDebugCode3::GetReturnValueLiveOffset
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugCode3.GetReturnValueLiveOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset
helpviewer_keywords:
- ICorDebugCode3::GetReturnValueLiveOffset method [.NET Framework debugging]
- GetReturnValueLiveOffset method [.NET Framework debugging]
ms.assetid: 8c2ff5d8-8c04-4423-b1e1-e1c8764b36d3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03ee275336d3ae71f63d82add694fe1308efbe8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125941"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="5b0d1-102">Метод ICorDebugCode3::GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="5b0d1-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="5b0d1-103">Для указанного смещения на промежуточном Языке получает смещения в машинном коде, где должны размещаться точку останова, чтобы отладчик мог получить возвращаемое значение из функции.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b0d1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5b0d1-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b0d1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5b0d1-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="5b0d1-106">Смещение на промежуточном Языке.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-106">The IL offset.</span></span> <span data-ttu-id="5b0d1-107">Он должен находиться на сайт вызова функции или вызов функции завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="5b0d1-108">Число байтов для хранения `pOffsets`.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="5b0d1-109">Указатель на количество фактически возвращенных смещений.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="5b0d1-110">Как правило, его значение равно 1, но одна инструкция IL может сопоставляться нескольким `CALL` инструкции ассемблера.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="5b0d1-111">Массив смещений в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-111">An array of native offsets.</span></span> <span data-ttu-id="5b0d1-112">Как правило `pOffsets` содержит одно смещение, несмотря на то, что одна инструкция IL может сопоставляться несколькими к нескольким `CALL` инструкции ассемблера.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b0d1-113">Примечания</span><span class="sxs-lookup"><span data-stu-id="5b0d1-113">Remarks</span></span>  
 <span data-ttu-id="5b0d1-114">Этот метод используется вместе с [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) способ получения возвращаемого значения метода, который возвращает ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="5b0d1-115">Передача смещения на сайт вызова функции в этот метод IL возвращает один или несколько смещений в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="5b0d1-116">Отладчик может установить точки останова на этих естественных смещениях функции.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="5b0d1-117">Когда отладчик достигает одной из точек останова, затем можно передать то же смещение IL, которое было передано в этот метод, чтобы [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) способ получения возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="5b0d1-118">Затем он должен очистить все точки останова, он задан.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="5b0d1-119">`ICorDebugCode3::GetReturnValueLiveOffset` И [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) методы позволяют получить сведения о возвращаемом значении только для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="5b0d1-120">Получение сведений о возвращаемое значение из типов значений (то есть всех типов, производных от <xref:System.ValueType>) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="5b0d1-121">Функция возвращает `HRESULT` значений, приведенных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|`HRESULT` <span data-ttu-id="5b0d1-122">value</span><span class="sxs-lookup"><span data-stu-id="5b0d1-122">value</span></span>|<span data-ttu-id="5b0d1-123">Описание</span><span class="sxs-lookup"><span data-stu-id="5b0d1-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="5b0d1-124">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="5b0d1-125">Заданное смещение сайта IL не является инструкцией вызова, или функция возвращает `void`.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="5b0d1-126">Заданное смещение IL является правильным вызовом, но возвращаемый тип не поддерживается для получения возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="5b0d1-127">`ICorDebugCode3::GetReturnValueLiveOffset` Метод доступен только на x86 и системах AMD64.</span><span class="sxs-lookup"><span data-stu-id="5b0d1-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b0d1-128">Требования</span><span class="sxs-lookup"><span data-stu-id="5b0d1-128">Requirements</span></span>  
 <span data-ttu-id="5b0d1-129">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b0d1-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b0d1-130">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b0d1-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b0d1-131">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b0d1-131">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="5b0d1-132">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="5b0d1-132">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="5b0d1-133">См. также</span><span class="sxs-lookup"><span data-stu-id="5b0d1-133">See also</span></span>

- [<span data-ttu-id="5b0d1-134">Метод GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="5b0d1-134">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)
- [<span data-ttu-id="5b0d1-135">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="5b0d1-135">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
