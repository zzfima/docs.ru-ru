---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 870a71de2aee2e9b725749157791c49836c6ea00
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636886"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="3773e-102">Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="3773e-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="3773e-103">Возвращает перечислитель для всех методов, которые определены в указанный модуль NGen и в строке данного метода.</span><span class="sxs-lookup"><span data-stu-id="3773e-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="3773e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3773e-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="3773e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3773e-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="3773e-106">[in] Идентификатор модуля NGen.</span><span class="sxs-lookup"><span data-stu-id="3773e-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="3773e-107">[in] Идентификатор модуля, который определяет `inlineeMethodId`.</span><span class="sxs-lookup"><span data-stu-id="3773e-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="3773e-108">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="3773e-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="3773e-109">[in] Идентификатор метода как встроенный.</span><span class="sxs-lookup"><span data-stu-id="3773e-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="3773e-110">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="3773e-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="3773e-111">[out] Флаг, указывающий, является ли `ppEnum` содержит все методы встраивания определенного метода.</span><span class="sxs-lookup"><span data-stu-id="3773e-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="3773e-112">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="3773e-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="3773e-113">[out] Указатель на адрес перечислителя</span><span class="sxs-lookup"><span data-stu-id="3773e-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="3773e-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="3773e-114">Remarks</span></span>

<span data-ttu-id="3773e-115">`inlineeModuleId` и `inlineeMethodId` вместе образуют полный идентификатор для метода, который может быть встроен.</span><span class="sxs-lookup"><span data-stu-id="3773e-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="3773e-116">Предположим, например, модуль `A` определяет метод `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="3773e-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="3773e-117">а также определяет модуль B `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="3773e-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="3773e-118">Позволяет также предполагается, что `Fancy.AddTwice` inlines вызов к `SimpleAdd`.</span><span class="sxs-lookup"><span data-stu-id="3773e-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="3773e-119">Профилировщик может использовать этот перечислитель для поиска, все методы, определенные в модуле B, какие встроенные `Simple.Add`, и результат будет перечислять `AddTwice`.</span><span class="sxs-lookup"><span data-stu-id="3773e-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="3773e-120">`inlineeModuleId` Идентификатор модуля `A`, и `inlineeMethodId` идентификатор `Simple.Add(int a, int b)`.</span><span class="sxs-lookup"><span data-stu-id="3773e-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="3773e-121">Если `incompleteData` имеет значение true, после функции Возвращает перечислитель не содержит все методы встраивания определенного метода.</span><span class="sxs-lookup"><span data-stu-id="3773e-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="3773e-122">Это может произойти, если в одном или более прямой или косвенной зависимости модуля inliners еще не были загружены.</span><span class="sxs-lookup"><span data-stu-id="3773e-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="3773e-123">Если профилировщик должен точные данные, его следует повторить позднее при загрузке дополнительных модулей, предпочтительно при каждой загрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="3773e-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="3773e-124">`EnumNgenModuleMethodsInliningThisMethod` Метод может использоваться для обхода ограничений на встраивание для ReJIT.</span><span class="sxs-lookup"><span data-stu-id="3773e-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="3773e-125">ReJIT позволяет профилировщику измените реализацию метода и затем создать новый код для него в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="3773e-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="3773e-126">Например, мы изменим `Simple.Add` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3773e-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="3773e-127">Однако поскольку `Fancy.AddTwice` имеет уже встроена `Simple.Add`, он продолжает ведут себя так же как и раньше.</span><span class="sxs-lookup"><span data-stu-id="3773e-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="3773e-128">Чтобы обойти это ограничение, вызывающий оператор имеет для поиска всех методов во всех модулях это в процессе настройки `Simple.Add` и использовать `ICorProfilerInfo5::RequestRejit` на каждом из этих методов.</span><span class="sxs-lookup"><span data-stu-id="3773e-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="3773e-129">Если методы, повторная компиляция, они будут иметь новое поведение `Simple.Add` вместо старого поведения.</span><span class="sxs-lookup"><span data-stu-id="3773e-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="3773e-130">Требования</span><span class="sxs-lookup"><span data-stu-id="3773e-130">Requirements</span></span>

<span data-ttu-id="3773e-131">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3773e-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="3773e-132">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3773e-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="3773e-133">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3773e-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3773e-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3773e-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3773e-135">См. также</span><span class="sxs-lookup"><span data-stu-id="3773e-135">See also</span></span>

- [<span data-ttu-id="3773e-136">Интерфейс ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="3773e-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)
