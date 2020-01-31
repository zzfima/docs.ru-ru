---
title: Метод ICorProfilerCallback::COMClassicVTableCreated
ms.date: 03/30/2017
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
ms.openlocfilehash: 808c26f53c4089248420280a43c88a1b3af0dad9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866550"
---
# <a name="icorprofilercallbackcomclassicvtablecreated-method"></a><span data-ttu-id="7628a-102">Метод ICorProfilerCallback::COMClassicVTableCreated</span><span class="sxs-lookup"><span data-stu-id="7628a-102">ICorProfilerCallback::COMClassicVTableCreated Method</span></span>
<span data-ttu-id="7628a-103">Уведомляет профилировщик о том, что для указанного IID и класса был создан объект vtable COM-взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="7628a-103">Notifies the profiler that a COM interop vtable for the specified IID and class has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7628a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7628a-104">Syntax</span></span>  
  
```cpp  
HRESULT COMClassicVTableCreated(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable,  
    [in] ULONG   cSlots);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7628a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7628a-105">Parameters</span></span>

- `wrappedClasId`

  <span data-ttu-id="7628a-106">\[в] идентификатор класса, для которого была создана таблица vtable.</span><span class="sxs-lookup"><span data-stu-id="7628a-106">\[in] The ID of the class for which the vtable has been created.</span></span>

- `implementedIID`

  <span data-ttu-id="7628a-107">\[в] идентификатор интерфейса, реализуемого классом.</span><span class="sxs-lookup"><span data-stu-id="7628a-107">\[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="7628a-108">Это значение может быть равно NULL, если интерфейс является только внутренним.</span><span class="sxs-lookup"><span data-stu-id="7628a-108">This value may be NULL if the interface is internal only.</span></span>

- `pVTable`

  <span data-ttu-id="7628a-109">\[в] указатель на начало таблицы vtable.</span><span class="sxs-lookup"><span data-stu-id="7628a-109">\[in] A pointer to the start of the vtable.</span></span>

- `cSlots`

  <span data-ttu-id="7628a-110">\[в] число слотов в таблице vtable.</span><span class="sxs-lookup"><span data-stu-id="7628a-110">\[in] The number of slots that are in the vtable.</span></span>

## <a name="remarks"></a><span data-ttu-id="7628a-111">Заметки</span><span class="sxs-lookup"><span data-stu-id="7628a-111">Remarks</span></span>  
 <span data-ttu-id="7628a-112">Профилировщик не должен блокировать реализацию этого метода, так как стек может не находиться в состоянии, допускающем сборку мусора, поэтому невозможно включить вытесненную сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="7628a-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="7628a-113">Если профилировщик блокируется здесь и выполняется сборка мусора, среда выполнения блокируется до тех пор, пока этот обратный вызов не вернет значение.</span><span class="sxs-lookup"><span data-stu-id="7628a-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="7628a-114">Реализация этого метода профилировщиком не должна вызывать управляемый код или каким-либо образом приводит к выделению управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="7628a-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7628a-115">Требования</span><span class="sxs-lookup"><span data-stu-id="7628a-115">Requirements</span></span>  
 <span data-ttu-id="7628a-116">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7628a-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7628a-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7628a-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7628a-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7628a-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7628a-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7628a-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7628a-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="7628a-120">See also</span></span>

- [<span data-ttu-id="7628a-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7628a-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7628a-122">Метод COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="7628a-122">COMClassicVTableDestroyed Method</span></span>](icorprofilercallback-comclassicvtabledestroyed-method.md)
