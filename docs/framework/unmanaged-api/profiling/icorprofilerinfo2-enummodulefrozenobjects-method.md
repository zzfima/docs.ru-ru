---
title: "Метод ICorProfilerInfo2::EnumModuleFrozenObjects"
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3866d91d28258eaee78e6025175628796a369f88
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2enummodulefrozenobjects-method"></a><span data-ttu-id="b1b72-102">Метод ICorProfilerInfo2::EnumModuleFrozenObjects</span><span class="sxs-lookup"><span data-stu-id="b1b72-102">ICorProfilerInfo2::EnumModuleFrozenObjects Method</span></span>
<span data-ttu-id="b1b72-103">Возвращает перечислитель, позволяющий выполнять итерацию по замороженным объектам в указанном модуле. Этот метод устарел.</span><span class="sxs-lookup"><span data-stu-id="b1b72-103">Gets an enumerator that allows iteration over the frozen objects in the specified module.This method is obsolete.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1b72-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b1b72-104">Syntax</span></span>  
  
```  
HRESULT EnumModuleFrozenObjects(  
    [in] ModuleID moduleID,  
    [out] ICorProfilerObjectEnum** ppEnum);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b1b72-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b1b72-105">Parameters</span></span>  
 `moduleID`  
 <span data-ttu-id="b1b72-106">[in] Идентификатор модуля, содержащего закрепленные объекты для перечисления.</span><span class="sxs-lookup"><span data-stu-id="b1b72-106">[in] The ID of the module that contains the frozen objects to be enumerated.</span></span>  
  
 `ppEnum`  
 <span data-ttu-id="b1b72-107">[out] Указатель на адрес [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) интерфейс, который перечисляет закрепленные объекты.</span><span class="sxs-lookup"><span data-stu-id="b1b72-107">[out] A pointer to the address of an [ICorProfilerObjectEnum](../../../../docs/framework/unmanaged-api/profiling/icorprofilerobjectenum-interface.md) interface, which enumerates the frozen objects.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b1b72-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b1b72-108">Requirements</span></span>  
 <span data-ttu-id="b1b72-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b1b72-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1b72-110">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b1b72-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b1b72-111">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b1b72-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b1b72-112">**Версии платформы .NET framework:** 3.5, 3.0 с пакетом обновления 1, 3.0, 2.0 с пакетом обновления 1, 2.0</span><span class="sxs-lookup"><span data-stu-id="b1b72-112">**.NET Framework Versions:** 3.5, 3.0 SP1, 3.0, 2.0 SP1, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1b72-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b1b72-113">See Also</span></span>  
 [<span data-ttu-id="b1b72-114">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="b1b72-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="b1b72-115">Интерфейс ICorProfilerInfo2</span><span class="sxs-lookup"><span data-stu-id="b1b72-115">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
