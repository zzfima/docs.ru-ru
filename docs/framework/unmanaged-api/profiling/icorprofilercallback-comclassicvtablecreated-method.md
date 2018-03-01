---
title: "Метод ICorProfilerCallback::COMClassicVTableCreated"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.COMClassicVTableCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableCreated
helpviewer_keywords:
- COMClassicVTableCreated method [.NET Framework profiling]
- ICorProfilerCallback::COMClassicVTableCreated method [.NET Framework profiling]
ms.assetid: 6e1834ab-c359-498a-b10b-984ae23cdda4
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 43fb447393e1d34ca53fbb62ecdc456a97452bc4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="c2eba-102">Метод ICorProfilerCallback::COMClassicVTableCreated</span><span class="sxs-lookup"><span data-stu-id="c2eba-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="c2eba-103">Уведомляет профилировщик, что виртуальной таблицы взаимодействия COM для заданного IID и класса был создан.</span><span class="sxs-lookup"><span data-stu-id="c2eba-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2eba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c2eba-104">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c2eba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c2eba-105">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="c2eba-106">[in] Идентификатор класса, для которого создан виртуальной таблице.</span><span class="sxs-lookup"><span data-stu-id="c2eba-106">[in] The ID of the class for which the vtable has been created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="c2eba-107">[in] Идентификатор интерфейса, реализуемого классом.</span><span class="sxs-lookup"><span data-stu-id="c2eba-107">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="c2eba-108">Это значение может быть NULL, если интерфейс является только внутренним.</span><span class="sxs-lookup"><span data-stu-id="c2eba-108">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="c2eba-109">[in] Указатель на начало таблицы vtable.</span><span class="sxs-lookup"><span data-stu-id="c2eba-109">[in] A pointer to the start of the vtable.</span></span>  
  
 `cSlots`  
 <span data-ttu-id="c2eba-110">[in] Число слотов, которые находятся в таблице vtable.</span><span class="sxs-lookup"><span data-stu-id="c2eba-110">[in] The number of slots that are in the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c2eba-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="c2eba-111">Remarks</span></span>  
 <span data-ttu-id="c2eba-112">Профилировщик не должен блокироваться при реализации этого метода, так как стек может находиться в состоянии, допускающем сборку мусора, и поэтому не удастся включить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="c2eba-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="c2eba-113">Если здесь профилировщик блокируется и выполняется сборка мусора, среда выполнения будет блокироваться до возвращает этот обратный вызов.</span><span class="sxs-lookup"><span data-stu-id="c2eba-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="c2eba-114">Реализация этого метода профилировщика не должны вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="c2eba-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c2eba-115">Требования</span><span class="sxs-lookup"><span data-stu-id="c2eba-115">Requirements</span></span>  
 <span data-ttu-id="c2eba-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2eba-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2eba-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c2eba-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c2eba-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c2eba-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c2eba-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2eba-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2eba-120">См. также</span><span class="sxs-lookup"><span data-stu-id="c2eba-120">See Also</span></span>  
 [<span data-ttu-id="c2eba-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c2eba-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c2eba-122">Метод COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="c2eba-122">COMClassicVTableDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)
