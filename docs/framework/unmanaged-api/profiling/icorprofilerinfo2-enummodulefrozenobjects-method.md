---
title: Метод ICorProfilerInfo2::EnumModuleFrozenObjects
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.EnumModuleFrozenObjects
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::EnumModuleFrozenObjects
helpviewer_keywords:
- EnumModuleFrozenObjects method [.NET Framework profiling]
- ICorProfilerInfo2::EnumModuleFrozenObjects method [.NET Framework profiling]
ms.assetid: 920b6483-7064-4d64-8613-fcc38ccf9b1e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74517e034af6a1e4dfb8e4b28c2fec55a3d8de8b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59092842"
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="5bfec-102">Метод ICorProfilerInfo2::EnumModuleFrozenObjects</span><span class="sxs-lookup"><span data-stu-id="5bfec-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="5bfec-103">Получает перечислитель, позволяющий выполнять итерацию зафиксированных объектов в указанном модуле. Этот метод является устаревшим.</span><span class="sxs-lookup"><span data-stu-id="5bfec-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5bfec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5bfec-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5bfec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5bfec-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="5bfec-106">[in] Идентификатор модуля, содержащего зафиксированных объектов, которые необходимо перечислить.</span><span class="sxs-lookup"><span data-stu-id="5bfec-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="5bfec-107">[out] Указатель на адрес [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) интерфейс, который перечисляет зафиксированных объектов.</span><span class="sxs-lookup"><span data-stu-id="5bfec-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5bfec-108">Требования</span><span class="sxs-lookup"><span data-stu-id="5bfec-108">Requirements</span></span>  
 <span data-ttu-id="5bfec-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5bfec-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5bfec-110">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5bfec-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5bfec-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5bfec-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5bfec-112">**Версии платформы .NET framework:** 3.5, 3.0 С ПАКЕТОМ ОБНОВЛЕНИЯ 1, 3.0, 2.0 С ПАКЕТОМ ОБНОВЛЕНИЯ 1, 2.0</span><span class="sxs-lookup"><span data-stu-id="5bfec-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5bfec-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5bfec-113">See also</span></span>

- [<span data-ttu-id="5bfec-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="5bfec-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="5bfec-115">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="5bfec-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
