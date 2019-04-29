---
title: Метод ICorDebugILFrame3::GetReturnValueForILOffset
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
api_name:
- ICorDebugILFrame3.GetReturnValueForILOffset
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 06522727-5f64-4391-9331-11386883c352
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ac90473a0bf15173683c45abc8e4a840ea7e733
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61946439"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="b9b4f-102">Метод ICorDebugILFrame3::GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="b9b4f-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="b9b4f-103">Возвращает объект «ICorDebugValue», который инкапсулирует возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9b4f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9b4f-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9b4f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9b4f-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="b9b4f-106">Смещение на промежуточном Языке.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-106">The IL offset.</span></span> <span data-ttu-id="b9b4f-107">См. раздел примeчаний.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="b9b4f-108">Указатель на адрес объекта интерфейса «ICorDebugValue», предоставляющий сведения о возвращаемом значении вызова функции.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b9b4f-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="b9b4f-109">Remarks</span></span>  
 <span data-ttu-id="b9b4f-110">Этот метод используется вместе с [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) способ получения возвращаемого значения метода.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="b9b4f-111">Это особенно полезно при использовании методов, учитываются, возвращаемые значения, как показано в следующих двух примерах кода.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="b9b4f-112">В первом примере вызывается <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> метод, но игнорирует возвращаемое значение метода.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="b9b4f-113">Во втором примере показано гораздо более общие проблемы при отладке.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="b9b4f-114">Поскольку метод используется в качестве аргумента в вызове метода, его возвращаемое значение доступно только в том случае, когда отладчик проходит через вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="b9b4f-115">Во многих случаях особенно в том случае, если вызываемый метод определен во внешней библиотеке, которая не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="b9b4f-116">Если передать [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) метод смещения на сайт вызова функции промежуточном языке, он возвращает один или несколько смещений в машинном коде.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="b9b4f-117">Отладчик может установить точки останова на этих естественных смещениях функции.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="b9b4f-118">Когда отладчик достигает одной из точек останова, затем можно передать то же смещение IL, которое было передано в этот метод для получения возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="b9b4f-119">Затем он должен очистить все точки останова, он задан.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="b9b4f-120">[Метод ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) и `ICorDebugILFrame3::GetReturnValueForILOffset` методы позволяют получить сведения о возвращаемом значении только для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="b9b4f-121">Получение сведений о возвращаемое значение из типов значений (то есть всех типов, производных от <xref:System.ValueType>) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="b9b4f-122">Смещение на промежуточном Языке, определяемое `ILOffset` должно находиться на сайт вызова функции, а отлаживаемый объект должен быть остановлен на точку останова в исходное смещение, возвращенный [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) метод для то же смещение IL.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="b9b4f-123">Если отлаживаемый объект не останавливается на правильное расположение для заданного смещения IL, API завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="b9b4f-124">Если вызов функции не возвращает значение, API завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="b9b4f-125">`ICorDebugILFrame3::GetReturnValueForILOffset` Метод доступен только на x86 и системах AMD64.</span><span class="sxs-lookup"><span data-stu-id="b9b4f-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9b4f-126">Требования</span><span class="sxs-lookup"><span data-stu-id="b9b4f-126">Requirements</span></span>  
 <span data-ttu-id="b9b4f-127">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9b4f-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9b4f-128">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b9b4f-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b9b4f-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b9b4f-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b9b4f-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9b4f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9b4f-131">См. также</span><span class="sxs-lookup"><span data-stu-id="b9b4f-131">See also</span></span>

- [<span data-ttu-id="b9b4f-132">Метод GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="b9b4f-132">GetReturnValueLiveOffset Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="b9b4f-133">Интерфейс ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="b9b4f-133">ICorDebugILFrame3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe3-interface.md)
