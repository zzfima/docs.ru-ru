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
ms.openlocfilehash: 34d543dd76de05bdf55d8187cf192455d1387a9f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178944"
---
# <a name="icordebugcode3getreturnvalueliveoffset-method"></a><span data-ttu-id="6baa6-102">Метод ICorDebugCode3::GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="6baa6-102">ICorDebugCode3::GetReturnValueLiveOffset Method</span></span>
<span data-ttu-id="6baa6-103">Для указанного смещения IL получается родная смещения, где должна быть размещена точка разрыва, чтобы отладчик мог получить значение возврата от функции.</span><span class="sxs-lookup"><span data-stu-id="6baa6-103">For a specified IL offset, gets the native offsets where a breakpoint should be placed so that the debugger can obtain the return value from a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6baa6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6baa6-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueLiveOffset(  
    [in] ULONG32 ILoffset,  
    [in] ULONG32 bufferSize,
    [out] ULONG32 *pFetched,
    [out, size_is(buffersize), length_is(*pFetched)] ULong32 pOffsets[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6baa6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6baa6-105">Parameters</span></span>  
 `ILoffset`  
 <span data-ttu-id="6baa6-106">IL смещения.</span><span class="sxs-lookup"><span data-stu-id="6baa6-106">The IL offset.</span></span> <span data-ttu-id="6baa6-107">Это должен быть сайт вызова функции или вызов функции не удастся.</span><span class="sxs-lookup"><span data-stu-id="6baa6-107">It must be a function call site or the function call will fail.</span></span>  
  
 `bufferSize`  
 <span data-ttu-id="6baa6-108">Количество байтов, доступных для хранения. `pOffsets`</span><span class="sxs-lookup"><span data-stu-id="6baa6-108">The number of bytes available to store `pOffsets`.</span></span>  
  
 `pFetched`  
 <span data-ttu-id="6baa6-109">Указатель на количество смещений фактически вернулся.</span><span class="sxs-lookup"><span data-stu-id="6baa6-109">A pointer to the number of offsets actually returned.</span></span> <span data-ttu-id="6baa6-110">Обычно его значение составляет 1, но одна инструкция IL может сопоставить с несколькими `CALL` инструкциями сборки.</span><span class="sxs-lookup"><span data-stu-id="6baa6-110">Usually, its value is 1, but a single IL instruction can map to multiple `CALL` assembly instructions.</span></span>  
  
 `pOffsets`  
 <span data-ttu-id="6baa6-111">Массив родных смещений.</span><span class="sxs-lookup"><span data-stu-id="6baa6-111">An array of native offsets.</span></span> <span data-ttu-id="6baa6-112">Как `pOffsets` правило, содержит одно смещение, хотя одна инструкция IL может сопоставить на нескольких картах несколько `CALL` инструкций сборки.</span><span class="sxs-lookup"><span data-stu-id="6baa6-112">Typically, `pOffsets` contains a single offset, although a single IL instruction can map to multiple map to multiple `CALL` assembly instructions.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6baa6-113">Remarks</span><span class="sxs-lookup"><span data-stu-id="6baa6-113">Remarks</span></span>  
 <span data-ttu-id="6baa6-114">Этот метод используется вместе с методом [ICorDebugILFrame3::GetReturnValueILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) для получения значения возврата метода, возвращающему эталонный тип.</span><span class="sxs-lookup"><span data-stu-id="6baa6-114">This method is used along with the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value of a method that returns a reference type.</span></span> <span data-ttu-id="6baa6-115">Передача смещения IL на сайт вызова функции к этому методу возвращает один или несколько родных смещений.</span><span class="sxs-lookup"><span data-stu-id="6baa6-115">Passing an IL offset to a function call site to this method returns one or more native offsets.</span></span> <span data-ttu-id="6baa6-116">Затем отладчик может устанавливать точки разрыва на этих родных смещениях в функции.</span><span class="sxs-lookup"><span data-stu-id="6baa6-116">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="6baa6-117">Когда отладчик попадает в одну из точек разрыва, вы можете передать тот же IL смещения, что вы перешли к этому методу [ICorDebugILFrame3:GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) метод, чтобы получить значение возврата.</span><span class="sxs-lookup"><span data-stu-id="6baa6-117">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to the [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) method to get the return value.</span></span> <span data-ttu-id="6baa6-118">Затем отладчик должен очистить все установленные моменты разрыва.</span><span class="sxs-lookup"><span data-stu-id="6baa6-118">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="6baa6-119">И `ICorDebugCode3::GetReturnValueLiveOffset` [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) методы позволяют получить информацию о значении возврата только для эталонных типов.</span><span class="sxs-lookup"><span data-stu-id="6baa6-119">The `ICorDebugCode3::GetReturnValueLiveOffset` and [ICorDebugILFrame3::GetReturnValueForILOffset](icordebugilframe3-getreturnvalueforiloffset-method.md) methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="6baa6-120">Извлечение информации о значении возврата из типов <xref:System.ValueType>значений (т.е. все типы, которые вытекают из ) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="6baa6-120">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="6baa6-121">Функция возвращает `HRESULT` значения, указанные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="6baa6-121">The function returns the `HRESULT` values shown in the following table.</span></span>  
  
|<span data-ttu-id="6baa6-122">Значение `HRESULT`</span><span class="sxs-lookup"><span data-stu-id="6baa6-122">`HRESULT` value</span></span>|<span data-ttu-id="6baa6-123">Описание</span><span class="sxs-lookup"><span data-stu-id="6baa6-123">Description</span></span>|  
|---------------------|-----------------|  
|`S_OK`|<span data-ttu-id="6baa6-124">Успешно.</span><span class="sxs-lookup"><span data-stu-id="6baa6-124">Success.</span></span>|  
|`CORDBG_E_INVALID_OPCODE`|<span data-ttu-id="6baa6-125">Данный сайт смещения IL не является `void`инструкцией по вызову или возвращает функцию.</span><span class="sxs-lookup"><span data-stu-id="6baa6-125">The given IL offset site is not a call instruction, or the function returns `void`.</span></span>|  
|`CORDBG_E_UNSUPPORTED`|<span data-ttu-id="6baa6-126">Данное смещение IL является правильным вызовом, но тип возврата не поддерживается для получения значения возврата.</span><span class="sxs-lookup"><span data-stu-id="6baa6-126">The given IL offset is a proper call, but the return type is unsupported for getting a return value.</span></span>|  
  
 <span data-ttu-id="6baa6-127">Метод `ICorDebugCode3::GetReturnValueLiveOffset` доступен только на системах x86 и AMD64.</span><span class="sxs-lookup"><span data-stu-id="6baa6-127">The `ICorDebugCode3::GetReturnValueLiveOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6baa6-128">Требования</span><span class="sxs-lookup"><span data-stu-id="6baa6-128">Requirements</span></span>  
 <span data-ttu-id="6baa6-129">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6baa6-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6baa6-130">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6baa6-130">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6baa6-131">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6baa6-131">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6baa6-132">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6baa6-132">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6baa6-133">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6baa6-133">See also</span></span>

- [<span data-ttu-id="6baa6-134">Метод GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="6baa6-134">GetReturnValueForILOffset Method</span></span>](icordebugilframe3-getreturnvalueforiloffset-method.md)
- [<span data-ttu-id="6baa6-135">Интерфейс ICorDebugCode3</span><span class="sxs-lookup"><span data-stu-id="6baa6-135">ICorDebugCode3 Interface</span></span>](icordebugcode3-interface.md)
