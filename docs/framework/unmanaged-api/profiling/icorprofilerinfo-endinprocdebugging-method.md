---
title: "Метод ICorProfilerInfo::EndInprocDebugging"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.EndInprocDebugging
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::EndInprocDebugging
helpviewer_keywords:
- ICorProfilerInfo::EndInprocDebugging method [.NET Framework profiling]
- EndInprocDebugging method [.NET Framework profiling]
ms.assetid: 35bc1188-9767-4141-8038-60ea015b99ac
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6e87cf210fb2717379e6bdc0b687028d680fe624
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfoendinprocdebugging-method"></a><span data-ttu-id="2036e-102">Метод ICorProfilerInfo::EndInprocDebugging</span><span class="sxs-lookup"><span data-stu-id="2036e-102">ICorProfilerInfo::EndInprocDebugging Method</span></span>
<span data-ttu-id="2036e-103">Завершает работу сеанса в процессе отладки.</span><span class="sxs-lookup"><span data-stu-id="2036e-103">Shuts down an in-process debugging session.</span></span> <span data-ttu-id="2036e-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="2036e-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2036e-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2036e-105">Syntax</span></span>  
  
```  
HRESULT EndInprocDebugging(  
    [in]  DWORD dwProfilerContext);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2036e-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="2036e-106">Parameters</span></span>  
 `dwProfilerContext`  
 <span data-ttu-id="2036e-107">[in] Значение, определяющее сеанс отладки.</span><span class="sxs-lookup"><span data-stu-id="2036e-107">[in] A value that identifies the debugging session.</span></span> <span data-ttu-id="2036e-108">Это значение должно быть таким же, как получено в [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="2036e-108">This value must be the same as that received in the [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2036e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="2036e-109">Remarks</span></span>  
 <span data-ttu-id="2036e-110">Необходимо вызвать [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) и `EndInprocDebugging` в один и тот же метод обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="2036e-110">You must call [ICorProfilerInfo::BeginInprocDebugging](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md) and `EndInprocDebugging` within the same callback method.</span></span>  
  
 <span data-ttu-id="2036e-111">Службы отладки среды CLR поддерживается только в процессе отладки в .NET Framework версий 1.0 и 1.1.</span><span class="sxs-lookup"><span data-stu-id="2036e-111">The CLR debugging services supported limited in-process debugging in the .NET Framework versions 1.0 and 1.1.</span></span> <span data-ttu-id="2036e-112">Внутрипроцессная отладка позволяла профилировщику использовать проверочную API отладки.</span><span class="sxs-lookup"><span data-stu-id="2036e-112">In-process debugging enabled a profiler to use the inspection portions of the debugging API.</span></span> <span data-ttu-id="2036e-113">Однако из-за отзывов клиентов внутрипроцессная отладка удалено из платформы .NET Framework версии 2.0 и заменена набором функциональных возможностей, которые лучше подходят для API профилирования.</span><span class="sxs-lookup"><span data-stu-id="2036e-113">However, due to customer feedback, in-process debugging has been removed from the .NET Framework in version 2.0, and replaced with a set of functionality that is more in line with the profiling API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2036e-114">Требования</span><span class="sxs-lookup"><span data-stu-id="2036e-114">Requirements</span></span>  
 <span data-ttu-id="2036e-115">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2036e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2036e-116">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2036e-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2036e-117">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2036e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2036e-118">**Версия платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="2036e-118">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2036e-119">См. также</span><span class="sxs-lookup"><span data-stu-id="2036e-119">See Also</span></span>  
 [<span data-ttu-id="2036e-120">ICorProfilerInfo-интерфейс</span><span class="sxs-lookup"><span data-stu-id="2036e-120">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
