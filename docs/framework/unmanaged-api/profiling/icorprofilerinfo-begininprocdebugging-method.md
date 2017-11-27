---
title: "Метод ICorProfilerInfo::BeginInprocDebugging"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.BeginInprocDebugging
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::BeginInprocDebugging
helpviewer_keywords:
- BeginInprocDebugging method [.NET Framework profiling]
- ICorProfilerInfo::BeginInprocDebugging method [.NET Framework profiling]
ms.assetid: c5c82c69-99f8-4447-aee0-42cca0a5eb5c
topic_type: apiref
caps.latest.revision: "16"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8c7c0b3c0a20c98b9ca2e5dd5ea51053008e415a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="8e851-102">Метод ICorProfilerInfo::BeginInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="8e851-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="8e851-103">Инициализирует внутрипроцессную поддержку отладки.</span><span class="sxs-lookup"><span data-stu-id="8e851-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="8e851-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="8e851-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8e851-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8e851-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8e851-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="8e851-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="8e851-107">[in] Это значение равно `true` инициализировать поддержку отладки для текущего потока; задайте для него значение `false` инициализировать поддержку отладки для всех потоков.</span><span class="sxs-lookup"><span data-stu-id="8e851-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="8e851-108">[out] Указатель на возвращаемое значение, идентифицирующее сеанс отладки.</span><span class="sxs-lookup"><span data-stu-id="8e851-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8e851-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="8e851-109">Remarks</span></span>  
 <span data-ttu-id="8e851-110">Службы отладки среды CLR поддерживается только в процессе отладки в .NET Framework версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="8e851-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="8e851-111">Внутрипроцессная отладка позволяла профилировщику использовать проверочную API отладки.</span><span class="sxs-lookup"><span data-stu-id="8e851-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="8e851-112">Однако из-за отзывов клиентов внутрипроцессная отладка удалено из платформы .NET Framework версии 2.0 и заменена набором функциональных возможностей, которые лучше подходят для API профилирования.</span><span class="sxs-lookup"><span data-stu-id="8e851-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8e851-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8e851-113">Requirements</span></span>  
 <span data-ttu-id="8e851-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e851-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8e851-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8e851-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8e851-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8e851-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8e851-117">**Версия платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="8e851-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e851-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8e851-118">See Also</span></span>  
 [<span data-ttu-id="8e851-119">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8e851-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
