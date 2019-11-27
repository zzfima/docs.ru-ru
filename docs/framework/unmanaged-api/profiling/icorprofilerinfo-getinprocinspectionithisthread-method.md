---
title: Метод ICorProfilerInfo::GetInprocInspectionIThisThread
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetInprocInspectionIThisThread
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread
helpviewer_keywords:
- ICorProfilerInfo::GetInprocInspectionIThisThread method [.NET Framework profiling]
- GetInprocInspectionIThisThread method [.NET Framework profiling]
ms.assetid: badddccd-f85c-416e-9f0f-419eab2c9d42
topic_type:
- apiref
ms.openlocfilehash: bcc324d0f5cd14e1de9f02c8e6844a5868b70e8b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74438908"
---
# <a name="icorprofilerinfogetinprocinspectionithisthread-method"></a><span data-ttu-id="0e996-102">Метод ICorProfilerInfo::GetInprocInspectionIThisThread</span><span class="sxs-lookup"><span data-stu-id="0e996-102">ICorProfilerInfo::GetInprocInspectionIThisThread Method</span></span>
<span data-ttu-id="0e996-103">Возвращает объект, для которого можно запросить интерфейс ICorDebugThread.</span><span class="sxs-lookup"><span data-stu-id="0e996-103">Gets an object that can be queried for the ICorDebugThread interface.</span></span> <span data-ttu-id="0e996-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="0e996-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e996-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0e996-105">Syntax</span></span>  
  
```cpp  
HRESULT GetInprocInspectionIThisThread(  
    [out] IUnknown **ppicd);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0e996-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="0e996-106">Parameters</span></span>  
 `ppicd`  
 <span data-ttu-id="0e996-107">[выходной](/cpp/atl/iunknown) объект, который можно запросить для интерфейса `ICorDebugThread`.</span><span class="sxs-lookup"><span data-stu-id="0e996-107">[out](/cpp/atl/iunknown) object that can be queried for the `ICorDebugThread` interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0e996-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="0e996-108">Remarks</span></span>  
 <span data-ttu-id="0e996-109">Службы отладки среды CLR поддерживали ограниченную внутрипроцессную отладку в .NET Framework версии 1,0.</span><span class="sxs-lookup"><span data-stu-id="0e996-109">The common language runtime (CLR) debugging services supported limited in-process debugging in the .NET Framework version 1.0.</span></span> <span data-ttu-id="0e996-110">В процессе отладки с помощью профилировщика можно использовать части проверки для API отладки.</span><span class="sxs-lookup"><span data-stu-id="0e996-110">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="0e996-111">В результате отзывов клиентов внутрипроцессный процесс отладки был удален из .NET Framework в версии 2,0 и заменен набором функциональных возможностей, которые более подробно описаны в API профилирования.</span><span class="sxs-lookup"><span data-stu-id="0e996-111">As a result of customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0e996-112">Требования</span><span class="sxs-lookup"><span data-stu-id="0e996-112">Requirements</span></span>  
 <span data-ttu-id="0e996-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e996-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e996-114">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0e996-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0e996-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0e996-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0e996-116">**Версия .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="0e996-116">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e996-117">См. также:</span><span class="sxs-lookup"><span data-stu-id="0e996-117">See also</span></span>

- [<span data-ttu-id="0e996-118">Интерфейс ICorProfilerInfo</span><span class="sxs-lookup"><span data-stu-id="0e996-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
