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
ms.openlocfilehash: 7a96385ccc6e7f9089365c19bb8f150015bba81c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788532"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="934b9-102">Метод ICorDebugILFrame3::GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="934b9-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="934b9-103">Возвращает объект ICorDebugValue, инкапсулирующий возвращаемое значение функции.</span><span class="sxs-lookup"><span data-stu-id="934b9-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="934b9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="934b9-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,   
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="934b9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="934b9-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="934b9-106">Смещение IL.</span><span class="sxs-lookup"><span data-stu-id="934b9-106">The IL offset.</span></span> <span data-ttu-id="934b9-107">См. раздел примeчаний.</span><span class="sxs-lookup"><span data-stu-id="934b9-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="934b9-108">Указатель на адрес объекта "ICorDebugValue" интерфейса, который предоставляет сведения о возвращаемом значении вызова функции.</span><span class="sxs-lookup"><span data-stu-id="934b9-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="934b9-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="934b9-109">Remarks</span></span>  
 <span data-ttu-id="934b9-110">Этот метод используется вместе с методом [ICorDebugCode3:: жетретурнвалуеливеоффсет](icordebugcode3-getreturnvalueliveoffset-method.md) для получения возвращаемого значения метода.</span><span class="sxs-lookup"><span data-stu-id="934b9-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="934b9-111">Это особенно полезно в случае с методами, возвращаемые значения которых игнорируются, как в следующих двух примерах кода.</span><span class="sxs-lookup"><span data-stu-id="934b9-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="934b9-112">Первый пример вызывает метод <xref:System.Int32.TryParse%2A?displayProperty=nameWithType>, но игнорирует возвращаемое значение метода.</span><span class="sxs-lookup"><span data-stu-id="934b9-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="934b9-113">Во втором примере показана гораздо более распространенная проблема при отладке.</span><span class="sxs-lookup"><span data-stu-id="934b9-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="934b9-114">Так как метод используется в качестве аргумента в вызове метода, его возвращаемое значение доступно только в том случае, если отладчик проходит через вызываемый метод.</span><span class="sxs-lookup"><span data-stu-id="934b9-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="934b9-115">Во многих случаях, особенно если вызванный метод определен во внешней библиотеке, это невозможно.</span><span class="sxs-lookup"><span data-stu-id="934b9-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="934b9-116">Если передать метод [ICorDebugCode3:: жетретурнвалуеливеоффсет](icordebugcode3-getreturnvalueliveoffset-method.md) в качестве смещения Il на сайт вызова функции, он возвращает одно или несколько машинных смещений.</span><span class="sxs-lookup"><span data-stu-id="934b9-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="934b9-117">Затем отладчик может установить точки останова для этих собственных смещений в функции.</span><span class="sxs-lookup"><span data-stu-id="934b9-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="934b9-118">Когда отладчик обращается к одной из точек останова, можно передать то же смещение IL, которое вы передали этому методу для получения возвращаемого значения.</span><span class="sxs-lookup"><span data-stu-id="934b9-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="934b9-119">Затем отладчик должен очистить все заданные точки останова.</span><span class="sxs-lookup"><span data-stu-id="934b9-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="934b9-120">Методы [ICorDebugCode3:: жетретурнвалуеливеоффсет](icordebugcode3-getreturnvalueliveoffset-method.md) и `ICorDebugILFrame3::GetReturnValueForILOffset` позволяют получать сведения о возвращаемых значениях только для ссылочных типов.</span><span class="sxs-lookup"><span data-stu-id="934b9-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="934b9-121">Получение сведений о возвращаемом значении из типов значений (то есть все типы, производные от <xref:System.ValueType>) не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="934b9-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="934b9-122">Смещение IL, заданное параметром `ILOffset`, должно находиться на сайте вызова функции, а отладка должна быть остановлена в точке останова, установленной в машинном смещении, возвращенном методом [ICorDebugCode3:: жетретурнвалуеливеоффсет](icordebugcode3-getreturnvalueliveoffset-method.md) для того же смещения IL.</span><span class="sxs-lookup"><span data-stu-id="934b9-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="934b9-123">Если отлаживаемая программа не остановлена в правильном расположении для указанного смещения IL, API завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="934b9-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="934b9-124">Если вызов функции не возвращает значение, API завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="934b9-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="934b9-125">Метод `ICorDebugILFrame3::GetReturnValueForILOffset` доступен только в системах на базе x86 и AMD64.</span><span class="sxs-lookup"><span data-stu-id="934b9-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="934b9-126">Требования</span><span class="sxs-lookup"><span data-stu-id="934b9-126">Requirements</span></span>  
 <span data-ttu-id="934b9-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="934b9-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="934b9-128">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="934b9-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="934b9-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="934b9-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="934b9-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="934b9-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="934b9-131">См. также:</span><span class="sxs-lookup"><span data-stu-id="934b9-131">See also</span></span>

- [<span data-ttu-id="934b9-132">Метод GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="934b9-132">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="934b9-133">Интерфейс ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="934b9-133">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
