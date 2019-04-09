---
title: Метод ICorProfilerInfo::BeginInprocDebugging
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f12442eb5596ff3dca49cf24e27040f3e92d3a7c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072614"
---
# <a name="icorprofilerinfobegininprocdebugging-method"></a><span data-ttu-id="d7533-102">Метод ICorProfilerInfo::BeginInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="d7533-102">ICorProfilerInfo::BeginInprocDebugging Method</span></span>
<span data-ttu-id="d7533-103">Инициализирует внутрипроцессную поддержку отладки.</span><span class="sxs-lookup"><span data-stu-id="d7533-103">Initializes in-process debugging support.</span></span> <span data-ttu-id="d7533-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="d7533-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7533-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d7533-105">Syntax</span></span>  
  
```  
HRESULT BeginInprocDebugging(  
    [in]  BOOL   fThisThreadOnly,  
    [out] DWORD *pdwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d7533-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="d7533-106">Parameters</span></span>  
 `fThisThreadOnly`  
 <span data-ttu-id="d7533-107">[in] Это значение равно `true` инициализировать поддержку отладки для всех потоков; ему присвоено `false` инициализировать поддержку отладки для всех потоков.</span><span class="sxs-lookup"><span data-stu-id="d7533-107">[in] Set this value to `true` to initialize debugging support for only the current thread; set it to `false` to initialize debugging support for all threads.</span></span>  
  
 `pdwProfilerContext`  
 <span data-ttu-id="d7533-108">[out] Указатель на возвращаемое значение, идентифицирующее сеанс отладки.</span><span class="sxs-lookup"><span data-stu-id="d7533-108">[out] The pointer to a returned value that identifies the debugging session.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d7533-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="d7533-109">Remarks</span></span>  
 <span data-ttu-id="d7533-110">Службы отладки среды CLR поддерживается только в процессе отладки в .NET Framework версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="d7533-110">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="d7533-111">В процессе отладки включить профилировщик для использования для проверки часть API отладки.</span><span class="sxs-lookup"><span data-stu-id="d7533-111">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="d7533-112">Тем не менее согласно с отзывами пользователей в процессе отладки удален из .NET Framework версии 2.0 и заменены набором функциональных возможностей, которые лучше соответствуют API профилирования.</span><span class="sxs-lookup"><span data-stu-id="d7533-112">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d7533-113">Требования</span><span class="sxs-lookup"><span data-stu-id="d7533-113">Requirements</span></span>  
 <span data-ttu-id="d7533-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d7533-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d7533-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d7533-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d7533-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d7533-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d7533-117">**Версии платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="d7533-117">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7533-118">См. также</span><span class="sxs-lookup"><span data-stu-id="d7533-118">See also</span></span>

- [<span data-ttu-id="d7533-119">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="d7533-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
