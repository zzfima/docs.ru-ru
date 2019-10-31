---
title: Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
ms.openlocfilehash: 103fe1b6845edfe0a364db979557db63511f6ee3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130374"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="ab2c3-102">Метод ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod</span><span class="sxs-lookup"><span data-stu-id="ab2c3-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>

<span data-ttu-id="ab2c3-103">Возвращает перечислитель для всех методов, определенных в заданном модуле NGen, и встроенный метод.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-103">Returns an enumerator to all the methods that are defined in a given NGen module and inline a given method.</span></span>

## <a name="syntax"></a><span data-ttu-id="ab2c3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ab2c3-104">Syntax</span></span>

```cpp
HRESULT EnumNgenModuleMethodsInliningThisMethod(
        [in] ModuleID inlinersModuleId,
        [in] ModuleID inlineeModuleId,
        [in] mdMethodDef inlineeMethodId,
        [out] BOOL *incompleteData,
        [out] ICorProfilerMethodEnum** ppEnum
);
```

## <a name="parameters"></a><span data-ttu-id="ab2c3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ab2c3-105">Parameters</span></span>

`inlinersModuleId`\
<span data-ttu-id="ab2c3-106">окне Идентификатор модуля NGen.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-106">[in] The identifier of an NGen module.</span></span>

`inlineeModuleId`\
<span data-ttu-id="ab2c3-107">окне Идентификатор модуля, который определяет `inlineeMethodId`.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-107">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="ab2c3-108">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="ab2c3-108">See the Remarks section for more information.</span></span>

`inlineeMethodId`\
<span data-ttu-id="ab2c3-109">окне Идентификатор встроенного метода.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-109">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="ab2c3-110">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="ab2c3-110">See the Remarks section for more information.</span></span>

`incompleteData`\
<span data-ttu-id="ab2c3-111">заполняет Флаг, указывающий, содержит ли `ppEnum` все методы, выставляемые для данного метода.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-111">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="ab2c3-112">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="ab2c3-112">See the Remarks section for more information.</span></span>

`ppEnum`\
<span data-ttu-id="ab2c3-113">заполняет Указатель на адрес перечислителя</span><span class="sxs-lookup"><span data-stu-id="ab2c3-113">[out] A pointer to the address of an enumerator</span></span>

## <a name="remarks"></a><span data-ttu-id="ab2c3-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="ab2c3-114">Remarks</span></span>

<span data-ttu-id="ab2c3-115">`inlineeModuleId` и `inlineeMethodId` вместе формируют полный идентификатор метода, который может быть встроенным.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-115">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="ab2c3-116">Например, предположим, что модуль `A` определяет метод `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="ab2c3-116">For example, assume module `A` defines a method `Simple.Add`:</span></span>

```csharp
Simple.Add(int a, int b)
{ return a + b; }
```

<span data-ttu-id="ab2c3-117">а модуль B определяет `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="ab2c3-117">and module B defines `Fancy.AddTwice`:</span></span>

```csharp
Fancy.AddTwice(int a, int b)
{ return Simple.Add(a,b) + Simple.Add(a,b); }
```

<span data-ttu-id="ab2c3-118">Также предполагается, что `Fancy.AddTwice` выдает вызов `SimpleAdd`.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-118">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="ab2c3-119">Профилировщик может использовать этот перечислитель для поиска всех методов, определенных в модуле B, которые встроены `Simple.Add`, и результатом будет перечисление `AddTwice`.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-119">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="ab2c3-120">`inlineeModuleId` — это идентификатор `A`модуля, а `inlineeMethodId` — идентификатор `Simple.Add(int a, int b)`.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-120">`inlineeModuleId` is the identifier of module `A`, and `inlineeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>

<span data-ttu-id="ab2c3-121">Если `incompleteData` имеет значение true после возврата функции, перечислитель не содержит все методы, выставляемые в данный метод.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-121">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="ab2c3-122">Это может произойти, если одна или несколько непосредственных или косвенных зависимостей модуля "вкладыши" еще не загружены.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-122">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="ab2c3-123">Если профилировщику требуются точные данные, необходимо повторить попытку позже, когда загрузится больше модулей, лучше при каждой загрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-123">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>

<span data-ttu-id="ab2c3-124">Метод `EnumNgenModuleMethodsInliningThisMethod` можно использовать для обхода ограничений встраивания для ReJIT.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-124">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="ab2c3-125">ReJIT позволяет профилировщику изменить реализацию метода, а затем создать новый код для него в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-125">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="ab2c3-126">Например, можно изменить `Simple.Add` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="ab2c3-126">For example, we could change `Simple.Add` as follows:</span></span>

```csharp
Simple.Add(int a, int b)
{ return 42; }
```

<span data-ttu-id="ab2c3-127">Однако, поскольку `Fancy.AddTwice` уже встроены `Simple.Add`, она по-разному работает так же, как и раньше.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-127">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="ab2c3-128">Чтобы обойти это ограничение, вызывающий объект должен найти все методы во всех модулях, которые встроены `Simple.Add` и использовать `ICorProfilerInfo5::RequestRejit` в каждом из этих методов.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-128">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="ab2c3-129">При повторной компиляции методов они будут иметь новое поведение `Simple.Add`, а не старое поведение.</span><span class="sxs-lookup"><span data-stu-id="ab2c3-129">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>

## <a name="requirements"></a><span data-ttu-id="ab2c3-130">Требования</span><span class="sxs-lookup"><span data-stu-id="ab2c3-130">Requirements</span></span>

<span data-ttu-id="ab2c3-131">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab2c3-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ab2c3-132">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ab2c3-132">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="ab2c3-133">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ab2c3-133">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="ab2c3-134">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab2c3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ab2c3-135">См. также</span><span class="sxs-lookup"><span data-stu-id="ab2c3-135">See also</span></span>

- [<span data-ttu-id="ab2c3-136">Интерфейс ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="ab2c3-136">ICorProfilerInfo6 Interface</span></span>](icorprofilerinfo6-interface.md)
