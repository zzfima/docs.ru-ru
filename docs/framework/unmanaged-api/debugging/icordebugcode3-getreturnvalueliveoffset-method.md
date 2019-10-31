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
ms.openlocfilehash: 77cda2c3d30b5926da219a38b762295818ca54a1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121195"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="81774-102">Метод ICorDebugCode3::GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="81774-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="81774-103">Для указанного смещения IL получает машинные смещения, в которых должна быть помещена точка останова, чтобы отладчик мог получить возвращаемое значение из функции.</span><span class="sxs-lookup"><span data-stu-id="81774-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81774-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="81774-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,   
    [out] ULONG32 *pFetched,   
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="81774-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="81774-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="81774-106">Смещение IL.</span><span class="sxs-lookup"><span data-stu-id="81774-106">The IL offset.</span></span> <span data-ttu-id="81774-107">Это должен быть сайт вызова функции, иначе вызов функции завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="81774-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="81774-108">Число байтов, доступных для хранения `pOffsets`.</span><span class="sxs-lookup"><span data-stu-id="81774-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="81774-109">Указатель на число фактически возвращенных смещений.</span><span class="sxs-lookup"><span data-stu-id="81774-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="81774-110">Обычно его значение равно 1, но одна инструкция IL может сопоставляться с несколькими инструкциями `CALL` сборки.</span><span class="sxs-lookup"><span data-stu-id="81774-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="81774-111">Массив смещений машинного кода.</span><span class="sxs-lookup"><span data-stu-id="81774-111">An array of native offsets.</span></span> <span data-ttu-id="81774-112">Как правило, `pOffsets` содержит одно смещение, хотя одна инструкция IL может сопоставляться с несколькими сопоставлениями с несколькими `CALL` инструкциями по сборке.</span><span class="sxs-lookup"><span data-stu-id="81774-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81774-113">Заметки</span><span class="sxs-lookup"><span data-stu-id="81774-113">Remarks</span></span>  
 <span data-ttu-id="81774-114">Этот метод используется вместе с методом [ICorDebugILFrame3:: жетретурнвалуефорилоффсет](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) для получения возвращаемого значения метода, возвращающего ссылочный тип.</span><span class="sxs-lookup"><span data-stu-id="81774-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="81774-115">Передача смещения IL на сайт вызова функции в этот метод возвращает одно или несколько исходных смещений.</span><span class="sxs-lookup"><span data-stu-id="81774-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="81774-116">Затем отладчик может установить точки останова для этих собственных смещений в функции.</span><span class="sxs-lookup"><span data-stu-id="81774-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="81774-117">Когда отладчик обращается к одной из точек останова, можно передать то же смещение IL, которое вы передали этому методу методу [ICorDebugILFrame3:: жетретурнвалуефорилоффсет](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) , чтобы получить возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="81774-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="81774-118">Затем отладчик должен очистить все заданные точки останова.</span><span class="sxs-lookup"><span data-stu-id="81774-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="81774-119">Методы `ICorDebugCode3::GetReturnValueLiveOffset` и [ICorDebugILFrame3:: жетретурнвалуефорилоффсет](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) позволяют получать данные о возвращаемых значениях только для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="81774-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="81774-120">Получение сведений о возвращаемом значении из типов значений (то есть все типы, производные от <xref:System.ValueType>) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="81774-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="81774-121">Функция возвращает `HRESULT` значения, показанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="81774-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="81774-122">Значение`HRESULT`</span><span class="sxs-lookup"><span data-stu-id="81774-122">`HRESULT` value</span></span>|<span data-ttu-id="81774-123">Описание</span><span class="sxs-lookup"><span data-stu-id="81774-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="81774-124">Выполнено.</span><span class="sxs-lookup"><span data-stu-id="81774-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="81774-125">Указанный сайт смещения IL не является инструкцией вызова, или функция возвращает `void`.</span><span class="sxs-lookup"><span data-stu-id="81774-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="81774-126">Данное смещение IL является правильным вызовом, но возвращаемый тип не поддерживается для получения возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="81774-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="81774-127">Метод `ICorDebugCode3::GetReturnValueLiveOffset` доступен только в системах на базе x86 и AMD64.</span><span class="sxs-lookup"><span data-stu-id="81774-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81774-128">Требования</span><span class="sxs-lookup"><span data-stu-id="81774-128">Requirements</span></span>  
 <span data-ttu-id="81774-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81774-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81774-130">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="81774-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="81774-131">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81774-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81774-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81774-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81774-133">См. также</span><span class="sxs-lookup"><span data-stu-id="81774-133">See also</span></span>

- [<span data-ttu-id="81774-134">Метод GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="81774-134">GetReturnValueForILOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-getreturnvalueforiloffset-method.md)
- [<span data-ttu-id="81774-135">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="81774-135">ICorDebugCode3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-interface.md)
