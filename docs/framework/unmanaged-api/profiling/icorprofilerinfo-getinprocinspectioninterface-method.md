---
title: "Метод ICorProfilerInfo::GetInprocInspectionInterface"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetInprocInspectionInterface
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetInprocInspectionInterface
helpviewer_keywords:
- GetInprocInspectionInterface method [.NET Framework profiling]
- ICorProfilerInfo::GetInprocInspectionInterface method [.NET Framework profiling]
ms.assetid: 22a92d1d-8849-4af6-8304-ecc53dd1d289
topic_type: apiref
caps.latest.revision: "19"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be114784b0003e5f1540520fdbbef751b369f1da
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetinprocinspectioninterface-method"></a><span data-ttu-id="06acc-102">Метод ICorProfilerInfo::GetInprocInspectionInterface</span><span class="sxs-lookup"><span data-stu-id="06acc-102">ICorProfilerInfo::GetInprocInspectionInterface Method</span></span>
<span data-ttu-id="06acc-103">Возвращает объект, который может запрашиваться для интерфейса «ICorDebugProcess».</span><span class="sxs-lookup"><span data-stu-id="06acc-103">Gets an object that can be queried for an "ICorDebugProcess" interface.</span></span> <span data-ttu-id="06acc-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="06acc-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06acc-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="06acc-105">Syntax</span></span>  
  
```  
HRESULT GetInprocInspectionInterface(  
    [out] IUnknown **ppicd);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="06acc-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="06acc-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="06acc-107">[out](/cpp/atl/iunknown) объекта, который может запрашиваться для `ICorDebugProcess` интерфейса.</span><span class="sxs-lookup"><span data-stu-id="06acc-107">[out](/cpp/atl/iunknown) object that can be queried for an `ICorDebugProcess` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06acc-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="06acc-108">Remarks</span></span>  
 <span data-ttu-id="06acc-109">Общеязыковой среды выполнения (CLR), API отладки поддерживается только в процессе отладки в .NET Framework версии 1.0.</span><span class="sxs-lookup"><span data-stu-id="06acc-109">The common language runtime (CLR) debugging API supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="06acc-110">Внутрипроцессная отладка позволяла профилировщику использовать проверочную API отладки.</span><span class="sxs-lookup"><span data-stu-id="06acc-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="06acc-111">В результате отзывов клиентов внутрипроцессная отладка были удалены из .NET Framework версии 2.0 и заменена набором функциональных возможностей, которые лучше подходят для API профилирования.</span><span class="sxs-lookup"><span data-stu-id="06acc-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06acc-112">Требования</span><span class="sxs-lookup"><span data-stu-id="06acc-112">Requirements</span></span>  
 <span data-ttu-id="06acc-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06acc-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06acc-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="06acc-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="06acc-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06acc-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06acc-116">**Версия платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="06acc-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06acc-117">См. также</span><span class="sxs-lookup"><span data-stu-id="06acc-117">See Also</span></span>  
 [<span data-ttu-id="06acc-118">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="06acc-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
