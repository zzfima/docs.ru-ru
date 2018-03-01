---
title: "Метод ICorProfilerInfo::GetInprocInspectionInterface"
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
- ICorProfilerInfo.GetInprocInspectionInterface
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9088389df33b079fe2275f5c7e642a055fa8ee51
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="abee7-102">Метод ICorProfilerInfo::GetInprocInspectionInterface</span><span class="sxs-lookup"><span data-stu-id="abee7-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="abee7-103">Возвращает объект, который может запрашиваться для интерфейса «ICorDebugProcess».</span><span class="sxs-lookup"><span data-stu-id="abee7-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="abee7-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="abee7-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="abee7-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="abee7-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="abee7-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="abee7-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="abee7-107">[out](/cpp/atl/iunknown) объекта, который может запрашиваться для `ICorDebugProcess` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="abee7-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="abee7-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="abee7-108">Remarks</span></span>  
 <span data-ttu-id="abee7-109">Общеязыковой среды выполнения (CLR), API отладки поддерживается только в процессе отладки в .NET Framework версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="abee7-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="abee7-110">Внутрипроцессная отладка позволяла профилировщику использовать проверочную API отладки.</span><span class="sxs-lookup"><span data-stu-id="abee7-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="abee7-111">В результате отзывов клиентов внутрипроцессная отладка были удалены из .NET Framework версии 2.0 и заменена набором функциональных возможностей, которые лучше подходят для API профилирования.</span><span class="sxs-lookup"><span data-stu-id="abee7-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="abee7-112">Требования</span><span class="sxs-lookup"><span data-stu-id="abee7-112">Requirements</span></span>  
 <span data-ttu-id="abee7-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="abee7-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="abee7-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="abee7-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="abee7-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="abee7-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="abee7-116">**Версия платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="abee7-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="abee7-117">См. также</span><span class="sxs-lookup"><span data-stu-id="abee7-117">See Also</span></span>  
 [<span data-ttu-id="abee7-118">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="abee7-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
