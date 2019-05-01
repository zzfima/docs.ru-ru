---
title: Метод ICorProfilerInfo::EndInprocDebugging
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.EndInprocDebugging
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bcae66fd30c29a0a3c9bd0b5ffc2047efdf3788d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62049665"
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="354e9-102">Метод ICorProfilerInfo::EndInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="354e9-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="354e9-103">Завершает сеанс отладки в процессе.</span><span class="sxs-lookup"><span data-stu-id="354e9-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="354e9-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="354e9-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="354e9-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="354e9-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
## <a name="parameters"></a><span data-ttu-id="354e9-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="354e9-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="354e9-107">[in] Значение, которое идентифицирует сеанс отладки.</span><span class="sxs-lookup"><span data-stu-id="354e9-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="354e9-108">Это значение должно быть такой же, как получено в [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="354e9-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="354e9-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="354e9-109">Remarks</span></span>  
 <span data-ttu-id="354e9-110">Необходимо вызвать [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) и `EndInprocDebugging` в один и тот же метод обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="354e9-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="354e9-111">Службы отладки среды CLR поддерживается только в процессе отладки в .NET Framework версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="354e9-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="354e9-112">В процессе отладки включить профилировщик для использования для проверки часть API отладки.</span><span class="sxs-lookup"><span data-stu-id="354e9-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="354e9-113">Тем не менее согласно с отзывами пользователей в процессе отладки удален из .NET Framework версии 2.0 и заменены набором функциональных возможностей, которые лучше соответствуют API профилирования.</span><span class="sxs-lookup"><span data-stu-id="354e9-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="354e9-114">Требования</span><span class="sxs-lookup"><span data-stu-id="354e9-114">Requirements</span></span>  
 <span data-ttu-id="354e9-115">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="354e9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="354e9-116">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="354e9-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="354e9-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="354e9-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="354e9-118">**Версии платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="354e9-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="354e9-119">См. также</span><span class="sxs-lookup"><span data-stu-id="354e9-119">See also</span></span>

- [<span data-ttu-id="354e9-120">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="354e9-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
