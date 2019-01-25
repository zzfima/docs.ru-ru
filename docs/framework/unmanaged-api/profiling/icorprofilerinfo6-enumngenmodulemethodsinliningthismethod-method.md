---
title: ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method
ms.date: 03/30/2017
ms.assetid: b933dfe6-7833-40cb-aad8-40842dc3034f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 07b1c905e587708336ce690bbf3d187b2d21e5b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568157"
---
# <a name="icorprofilerinfo6enumngenmodulemethodsinliningthismethod-method"></a><span data-ttu-id="3c3f5-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span><span class="sxs-lookup"><span data-stu-id="3c3f5-102">ICorProfilerInfo6::EnumNgenModuleMethodsInliningThisMethod Method</span></span>
<span data-ttu-id="3c3f5-103">[Поддерживается в .NET Framework 4.6 и более поздних версиях]</span><span class="sxs-lookup"><span data-stu-id="3c3f5-103">[Supported in the .NET Framework 4.6 and later versions]</span></span>  
  
 <span data-ttu-id="3c3f5-104">Возвращает перечислитель для всех методов, которые определены в указанный модуль NGen и в строке данного метода.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-104">Returns an enumerator to all the methods that          are defined in  a given NGen module and          inline a given method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c3f5-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3c3f5-105">Syntax</span></span>  
  
```  
HRESULT EnumNgenModuleMethodsInliningThisMethod(  
        [in] ModuleID inlinersModuleId,  
        [in] ModuleID inlineeModuleId,  
        [in] mdMethodDef inlineeMethodId,  
        [out] BOOL *incompleteData,  
        [out] ICorProfilerMethodEnum** ppEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3c3f5-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="3c3f5-106">Parameters</span></span>  
 `inlinersModuleId`  
 <span data-ttu-id="3c3f5-107">[in] Идентификатор модуля NGen.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-107">[in] The identifier of an NGen module.</span></span>  
  
 `inlineeModuleId`  
 <span data-ttu-id="3c3f5-108">[in] Идентификатор модуля, который определяет `inlineeMethodId`.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-108">[in] The identifier of a module that defines `inlineeMethodId`.</span></span> <span data-ttu-id="3c3f5-109">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="3c3f5-109">See the Remarks section for more information.</span></span>  
  
 `inlineeMethodId`  
 <span data-ttu-id="3c3f5-110">[in] Идентификатор метода как встроенный.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-110">[in] The identifier of an inlined method.</span></span> <span data-ttu-id="3c3f5-111">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="3c3f5-111">See the Remarks section for more information.</span></span>  
  
 `incompleteData`  
 <span data-ttu-id="3c3f5-112">[out] Флаг, указывающий, является ли `ppEnum` содержит все методы встраивания определенного метода.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-112">[out] A flag that indicates whether `ppEnum` contains all methods inlining a given method.</span></span>  <span data-ttu-id="3c3f5-113">Дополнительные сведения см. в разделе "Примечания".</span><span class="sxs-lookup"><span data-stu-id="3c3f5-113">See the Remarks section for more information.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="3c3f5-114">[out] Указатель на адрес перечислителя</span><span class="sxs-lookup"><span data-stu-id="3c3f5-114">[out] A pointer to the address of an enumerator</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c3f5-115">Примечания</span><span class="sxs-lookup"><span data-stu-id="3c3f5-115">Remarks</span></span>  
 <span data-ttu-id="3c3f5-116">`inlineeModuleId` и `inlineeMethodId` вместе образуют полный идентификатор для метода, который может быть встроен.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-116">`inlineeModuleId` and `inlineeMethodId` together form the full identifier for the method that might be inlined.</span></span> <span data-ttu-id="3c3f5-117">Предположим, например, модуль `A` определяет метод `Simple.Add`:</span><span class="sxs-lookup"><span data-stu-id="3c3f5-117">For example, assume module `A` defines a method `Simple.Add`:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return a + b; }  
```  
  
 <span data-ttu-id="3c3f5-118">и модуль Bdefines `Fancy.AddTwice`:</span><span class="sxs-lookup"><span data-stu-id="3c3f5-118">and module Bdefines `Fancy.AddTwice`:</span></span>  
  
```csharp  
Fancy.AddTwice(int a, int b)   
{ return Simple.Add(a,b) + Simple.Add(a,b); }  
```  
  
 <span data-ttu-id="3c3f5-119">Позволяет также предполагается, что `Fancy.AddTwice` inlines вызов к `SimpleAdd`.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-119">Lets also assume that `Fancy.AddTwice` inlines the call to `SimpleAdd`.</span></span> <span data-ttu-id="3c3f5-120">Профилировщик может использовать этот перечислитель для поиска, все методы, определенные в модуле B, какие встроенные `Simple.Add`, и результат будет перечислять `AddTwice`.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-120">A profiler could use this enumerator to find all methods defined in module B which inline `Simple.Add`, and the result would enumerate `AddTwice`.</span></span>  <span data-ttu-id="3c3f5-121">`inlineeModuleId` Идентификатор модуля `A`, и `inlineeeMethodId` идентификатор `Simple.Add(int a, int b)`.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-121">`inlineeModuleId` is the identifier of module `A`,   and `inlineeeMethodId` is the identifier of `Simple.Add(int a, int b)`.</span></span>  
  
 <span data-ttu-id="3c3f5-122">Если `incompleteData` имеет значение true, после функции Возвращает перечислитель не содержит все методы встраивания определенного метода.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-122">If `incompleteData` is true after the function returns, the enumerator does not contain all methods inlining a given method.</span></span> <span data-ttu-id="3c3f5-123">Это может произойти, если в одном или более прямой или косвенной зависимости модуля inliners еще не были загружены.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-123">This can happen when one or more direct or indirect dependencies of inliners module haven't been loaded yet.</span></span> <span data-ttu-id="3c3f5-124">Если профилировщик должен точные данные, его следует повторить позднее при загрузке дополнительных модулей, предпочтительно при каждой загрузке модуля.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-124">If a profiler needs accurate data, it should retry later when more modules are loaded, preferably on each module load.</span></span>  
  
 <span data-ttu-id="3c3f5-125">`EnumNgenModuleMethodsInliningThisMethod` Метод может использоваться для обхода ограничений на встраивание для ReJIT.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-125">The `EnumNgenModuleMethodsInliningThisMethod` method can be used to work around limitations on inlining for ReJIT.</span></span> <span data-ttu-id="3c3f5-126">ReJIT позволяет профилировщику измените реализацию метода и затем создать новый код для него в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-126">ReJIT lets a profiler change the implementation of a method and then create new code for it on the fly.</span></span> <span data-ttu-id="3c3f5-127">Например, мы изменим `Simple.Add` следующим образом:</span><span class="sxs-lookup"><span data-stu-id="3c3f5-127">For example, we could change `Simple.Add` as follows:</span></span>  
  
```csharp  
Simple.Add(int a, int b)   
{ return 42; }  
```  
  
 <span data-ttu-id="3c3f5-128">Однако поскольку `Fancy.AddTwice` имеет уже встроена `Simple.Add`, он продолжает ведут себя так же как и раньше.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-128">However because `Fancy.AddTwice` has already inlined `Simple.Add`, it continues to have the same behavior as before.</span></span> <span data-ttu-id="3c3f5-129">Чтобы обойти это ограничение, вызывающий оператор имеет для поиска всех методов во всех модулях это в процессе настройки `Simple.Add` и использовать `ICorProfilerInfo5::RequestRejit` на каждом из этих методов.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-129">To work around that limitation, the caller has to search for all methods in all modules that inline `Simple.Add` and use `ICorProfilerInfo5::RequestRejit` on each of those methods.</span></span> <span data-ttu-id="3c3f5-130">Если методы, повторная компиляция, они будут иметь новое поведение `Simple.Add` вместо старого поведения.</span><span class="sxs-lookup"><span data-stu-id="3c3f5-130">When the methods are re-compiled, they will have the new behavior of `Simple.Add` instead of the old behavior.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c3f5-131">Требования</span><span class="sxs-lookup"><span data-stu-id="3c3f5-131">Requirements</span></span>  
 <span data-ttu-id="3c3f5-132">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c3f5-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c3f5-133">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3c3f5-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3c3f5-134">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c3f5-134">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c3f5-135">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c3f5-135">**.NET Framework Versions:** [!INCLUDE[net_current_v46plus](../../../../includes/net-current-v46plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c3f5-136">См. также</span><span class="sxs-lookup"><span data-stu-id="3c3f5-136">See also</span></span>
- [<span data-ttu-id="3c3f5-137">Интерфейс ICorProfilerInfo6</span><span class="sxs-lookup"><span data-stu-id="3c3f5-137">ICorProfilerInfo6 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo6-interface.md)
