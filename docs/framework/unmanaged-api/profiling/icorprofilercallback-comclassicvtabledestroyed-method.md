---
title: Метод ICorProfilerCallback::COMClassicVTableDestroyed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.COMClassicVTableDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed
helpviewer_keywords:
- ICorProfilerCallback::COMClassicVTableDestroyed method [.NET Framework profiling]
- COMClassicVTableDestroyed method [.NET Framework profiling]
ms.assetid: 29da20ca-bf39-4356-8099-d9c3ac3423a9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 63dc9ee81c98a23f01948a142018369eca7210b1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59116762"
---
# <a name="icorprofilercallbackcomclassicvtabledestroyed-method"></a><span data-ttu-id="ad380-102">Метод ICorProfilerCallback::COMClassicVTableDestroyed</span><span class="sxs-lookup"><span data-stu-id="ad380-102">ICorProfilerCallback::COMClassicVTableDestroyed Method</span></span>
<span data-ttu-id="ad380-103">Уведомляет профилировщик об удалении таблицы vtable взаимодействия COM.</span><span class="sxs-lookup"><span data-stu-id="ad380-103">Notifies the profiler that a COM interop vtable is being destroyed.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad380-104">Этот обратный вызов является скорее всего, никогда не возникают, поскольку уничтожения осуществится происходит непосредственно перед завершением работы.</span><span class="sxs-lookup"><span data-stu-id="ad380-104">This callback is likely never to occur, because the destruction of vtables occurs very close to shutdown.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad380-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad380-105">Syntax</span></span>  
  
```  
HRESULT COMClassicVTableDestroyed(  
    [in] ClassID wrappedClassId,  
    [in] REFGUID implementedIID,  
    [in] void    *pVTable);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad380-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="ad380-106">Parameters</span></span>  
 `wrappedClasId`  
 <span data-ttu-id="ad380-107">[in] Идентификатор класса, для которого был создан этот vtable.</span><span class="sxs-lookup"><span data-stu-id="ad380-107">[in] The ID of the class for which this vtable was created.</span></span>  
  
 `implementedIID`  
 <span data-ttu-id="ad380-108">[in] Идентификатор интерфейса, реализуемого классом.</span><span class="sxs-lookup"><span data-stu-id="ad380-108">[in] The ID of the interface implemented by the class.</span></span> <span data-ttu-id="ad380-109">Это значение может быть NULL, если интерфейс предназначен только для внутреннего.</span><span class="sxs-lookup"><span data-stu-id="ad380-109">This value may be NULL if the interface is internal only.</span></span>  
  
 `pVTable`  
 <span data-ttu-id="ad380-110">[in] Указатель на начало таблицы vtable.</span><span class="sxs-lookup"><span data-stu-id="ad380-110">[in] A pointer to the start of the vtable.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ad380-111">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad380-111">Remarks</span></span>  
 <span data-ttu-id="ad380-112">Профилировщик не должен блокироваться при реализации этого метода, поскольку стек может находиться в состоянии, допускающем сбор мусора, и поэтому не удастся включить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="ad380-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="ad380-113">Если здесь профилировщик блокируется и предпринимается попытка сбора мусора, среда выполнения будет блокироваться до этого обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="ad380-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="ad380-114">Реализация этого метода профилировщика не следует вызывать управляемый код или каким-либо образом вызывать распределения управляемой памяти.</span><span class="sxs-lookup"><span data-stu-id="ad380-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad380-115">Требования</span><span class="sxs-lookup"><span data-stu-id="ad380-115">Requirements</span></span>  
 <span data-ttu-id="ad380-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad380-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad380-117">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad380-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad380-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad380-118">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ad380-119">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ad380-119">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad380-120">См. также</span><span class="sxs-lookup"><span data-stu-id="ad380-120">See also</span></span>

- [<span data-ttu-id="ad380-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="ad380-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="ad380-122">Метод COMClassicVTableCreated</span><span class="sxs-lookup"><span data-stu-id="ad380-122">COMClassicVTableCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)
