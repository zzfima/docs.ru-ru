---
title: "Метод ICorProfilerInfo::BeginInprocDebugging"
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
- ICorProfilerInfo.BeginInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 91306bbea7b099f7e9e408f8bf69625f1d7da68e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="e4a12-102">Метод ICorProfilerInfo::BeginInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="e4a12-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="e4a12-103">Инициализирует внутрипроцессную поддержку отладки.</span><span class="sxs-lookup"><span data-stu-id="e4a12-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="e4a12-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="e4a12-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4a12-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e4a12-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e4a12-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="e4a12-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="e4a12-107">[in] Это значение равно `true` инициализировать поддержку отладки для текущего потока; задайте для него значение `false` инициализировать поддержку отладки для всех потоков.</span><span class="sxs-lookup"><span data-stu-id="e4a12-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="e4a12-108">[out] Указатель на возвращаемое значение, идентифицирующее сеанс отладки.</span><span class="sxs-lookup"><span data-stu-id="e4a12-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4a12-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="e4a12-109">Remarks</span></span>  
 <span data-ttu-id="e4a12-110">Службы отладки среды CLR поддерживается только в процессе отладки в .NET Framework версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="e4a12-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="e4a12-111">Внутрипроцессная отладка позволяла профилировщику использовать проверочную API отладки.</span><span class="sxs-lookup"><span data-stu-id="e4a12-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="e4a12-112">Однако из-за отзывов клиентов внутрипроцессная отладка удалено из платформы .NET Framework версии 2.0 и заменена набором функциональных возможностей, которые лучше подходят для API профилирования.</span><span class="sxs-lookup"><span data-stu-id="e4a12-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4a12-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e4a12-113">Requirements</span></span>  
 <span data-ttu-id="e4a12-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e4a12-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4a12-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e4a12-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e4a12-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4a12-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4a12-117">**Версия платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="e4a12-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4a12-118">См. также</span><span class="sxs-lookup"><span data-stu-id="e4a12-118">See Also</span></span>  
 [<span data-ttu-id="e4a12-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="e4a12-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
