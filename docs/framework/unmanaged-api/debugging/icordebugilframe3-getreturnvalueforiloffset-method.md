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
ms.openlocfilehash: 0d1ef6c1369fd399f5b36b24a21c4b5d7f1e80fc
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178818"
---
# <a name="icordebugilframe3getreturnvalueforiloffset-method"></a><span data-ttu-id="3d892-102">Метод ICorDebugILFrame3::GetReturnValueForILOffset</span><span class="sxs-lookup"><span data-stu-id="3d892-102">ICorDebugILFrame3::GetReturnValueForILOffset Method</span></span>
<span data-ttu-id="3d892-103">Получает объект ICorDebugValue, который инкапсулирует значение возврата функции.</span><span class="sxs-lookup"><span data-stu-id="3d892-103">Gets an "ICorDebugValue" object that encapsulates the return value of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d892-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3d892-104">Syntax</span></span>  
  
```cpp
HRESULT GetReturnValueForILOffset(  
    ULONG32 ILoffset,
    [out] ICorDebugValue **ppReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d892-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3d892-105">Parameters</span></span>  
 `ILOffset`  
 <span data-ttu-id="3d892-106">IL смещения.</span><span class="sxs-lookup"><span data-stu-id="3d892-106">The IL offset.</span></span> <span data-ttu-id="3d892-107">См. раздел «Примечания».</span><span class="sxs-lookup"><span data-stu-id="3d892-107">See the Remarks section.</span></span>  
  
 `ppReturnValue`  
 <span data-ttu-id="3d892-108">Указатель на адрес объекта интерфейса "ICorDebugValue", который предоставляет информацию о значении возврата вызова функции.</span><span class="sxs-lookup"><span data-stu-id="3d892-108">A pointer to the address of an "ICorDebugValue" interface object that provides information about the return value of a function call.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3d892-109">Remarks</span><span class="sxs-lookup"><span data-stu-id="3d892-109">Remarks</span></span>  
 <span data-ttu-id="3d892-110">Этот метод используется вместе с [методом ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) для получения значения возврата метода.</span><span class="sxs-lookup"><span data-stu-id="3d892-110">This method is used along with the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method to get the return value of a method.</span></span> <span data-ttu-id="3d892-111">Это особенно полезно в случае методов, значения возврата которых игнорируются, как в следующих двух примерах кода.</span><span class="sxs-lookup"><span data-stu-id="3d892-111">It is particularly useful in the case of methods whose return values are ignored, as in the following two code examples.</span></span> <span data-ttu-id="3d892-112">Первый пример <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> вызывает метод, но игнорирует значение возврата метода.</span><span class="sxs-lookup"><span data-stu-id="3d892-112">The first example calls the <xref:System.Int32.TryParse%2A?displayProperty=nameWithType> method, but ignores the method's return value.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv1.cs#1)]
 [!code-vb[Unmanaged.Debugging.MRV#1](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv1.vb#1)]  
  
 <span data-ttu-id="3d892-113">Второй пример иллюстрирует гораздо более распространенную проблему при отладке.</span><span class="sxs-lookup"><span data-stu-id="3d892-113">The second example illustrates a much more common problem in debugging.</span></span> <span data-ttu-id="3d892-114">Поскольку метод используется в качестве аргумента в вызове метода, его значение возврата доступно только тогда, когда отладчик проходит через вызванный метод.</span><span class="sxs-lookup"><span data-stu-id="3d892-114">Because a method is used as an argument in a method call, its return value is accessible only when the debugger steps through the called method.</span></span> <span data-ttu-id="3d892-115">Во многих случаях, особенно когда вызовный метод определяется во внешней библиотеке, это невозможно.</span><span class="sxs-lookup"><span data-stu-id="3d892-115">In many cases, particularly when the called method is defined in an external library, that is not possible.</span></span>  
  
 [!code-csharp[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/csharp/VS_Snippets_CLR/unmanaged.debugging.mrv/cs/mrv2.cs#2)]
 [!code-vb[Unmanaged.Debugging.MRV#2](../../../../samples/snippets/visualbasic/VS_Snippets_CLR/unmanaged.debugging.mrv/vb/mrv2.vb#2)]  
  
 <span data-ttu-id="3d892-116">Если вы проходите [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) метод IL смещения на сайт вызова функции, он возвращает один или несколько родных смещений.</span><span class="sxs-lookup"><span data-stu-id="3d892-116">If you pass the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method an IL offset to a function call site, it returns one or more native offsets.</span></span> <span data-ttu-id="3d892-117">Затем отладчик может устанавливать точки разрыва на этих родных смещениях в функции.</span><span class="sxs-lookup"><span data-stu-id="3d892-117">The debugger can then set breakpoints on these native offsets in the function.</span></span> <span data-ttu-id="3d892-118">Когда отладчик попадает в одну из точек разрыва, вы можете передать тот же il смещения, что вы прошли к этому методу, чтобы получить значение возврата.</span><span class="sxs-lookup"><span data-stu-id="3d892-118">When the debugger hits one of the breakpoints, you can then pass the same IL offset that you passed to this method to get the return value.</span></span> <span data-ttu-id="3d892-119">Затем отладчик должен очистить все установленные моменты разрыва.</span><span class="sxs-lookup"><span data-stu-id="3d892-119">The debugger should then clear all the breakpoints that it set.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="3d892-120">[ICorDebugCode3::GetReturnValueLiveOffset метод](icordebugcode3-getreturnvalueliveoffset-method.md) `ICorDebugILFrame3::GetReturnValueForILOffset` и методы позволяют получить информацию о значении возврата только для эталонных типов.</span><span class="sxs-lookup"><span data-stu-id="3d892-120">The [ICorDebugCode3::GetReturnValueLiveOffset Method](icordebugcode3-getreturnvalueliveoffset-method.md) and `ICorDebugILFrame3::GetReturnValueForILOffset` methods allow you to get return value information for reference types only.</span></span> <span data-ttu-id="3d892-121">Извлечение информации о значении возврата из типов <xref:System.ValueType>значений (т.е. все типы, которые вытекают из ) не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3d892-121">Retrieving return value information from value types (that is, all types that derive from <xref:System.ValueType>) is not supported.</span></span>  
  
 <span data-ttu-id="3d892-122">Смещение IL, `ILOffset` указанное параметром, должно находиться на сайте вызова функции, а отладка должна быть остановлена в точке разрыва, установленной на родном смещении, возвращенном [Методом ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) для того же смещения IL.</span><span class="sxs-lookup"><span data-stu-id="3d892-122">The IL offset specified by the `ILOffset` parameter should be at a function call site, and the debuggee should be stopped at a breakpoint set at the native offset returned by the [ICorDebugCode3::GetReturnValueLiveOffset](icordebugcode3-getreturnvalueliveoffset-method.md) method for the same IL offset.</span></span> <span data-ttu-id="3d892-123">Если отладка не остановлена в нужном месте для указанного смещения IL, API выйдет из строя.</span><span class="sxs-lookup"><span data-stu-id="3d892-123">If the debuggee is not stopped at the correct location for the specified IL offset, the API will fail.</span></span>  
  
 <span data-ttu-id="3d892-124">Если вызов функции не возвращает значение, API выйдет из строя.</span><span class="sxs-lookup"><span data-stu-id="3d892-124">If the function call doesn't return a value, the API will fail.</span></span>  
  
 <span data-ttu-id="3d892-125">Метод `ICorDebugILFrame3::GetReturnValueForILOffset` доступен только на системах x86 и AMD64.</span><span class="sxs-lookup"><span data-stu-id="3d892-125">The `ICorDebugILFrame3::GetReturnValueForILOffset` method is available only on x86-based and AMD64 systems.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d892-126">Требования</span><span class="sxs-lookup"><span data-stu-id="3d892-126">Requirements</span></span>  
 <span data-ttu-id="3d892-127">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d892-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d892-128">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d892-128">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d892-129">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d892-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d892-130">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d892-130">**.NET Framework Versions:** [!INCLUDE[net_current_v451plus](../../../../includes/net-current-v451plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d892-131">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="3d892-131">See also</span></span>

- [<span data-ttu-id="3d892-132">Метод GetReturnValueLiveOffset</span><span class="sxs-lookup"><span data-stu-id="3d892-132">GetReturnValueLiveOffset Method</span></span>](icordebugcode3-getreturnvalueliveoffset-method.md)
- [<span data-ttu-id="3d892-133">Интерфейс ICorDebugILFrame3</span><span class="sxs-lookup"><span data-stu-id="3d892-133">ICorDebugILFrame3 Interface</span></span>](icordebugilframe3-interface.md)
