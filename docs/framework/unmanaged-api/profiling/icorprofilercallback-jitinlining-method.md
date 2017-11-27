---
title: "Метод ICorProfilerCallback::JITInlining"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.JITInlining
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b1e729a17101bbe9c659be729c685909932b5456
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="fb396-102">Метод ICorProfilerCallback::JITInlining</span><span class="sxs-lookup"><span data-stu-id="fb396-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="fb396-103">Уведомляет профилировщик, что время JIT-компилятор намерен вставить функцию в одну строку другой функции.</span><span class="sxs-lookup"><span data-stu-id="fb396-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb396-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fb396-104">Syntax</span></span>  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fb396-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fb396-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="fb396-106">[in] Идентификатор функции, в которую `calleeId` функции будут вставлены.</span><span class="sxs-lookup"><span data-stu-id="fb396-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="fb396-107">[in] Идентификатор функции для вставки.</span><span class="sxs-lookup"><span data-stu-id="fb396-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="fb396-108">[out] `true` на разрешение вставки синхронизации; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="fb396-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fb396-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="fb396-109">Remarks</span></span>  
 <span data-ttu-id="fb396-110">Можно задать профилировщик `pfShouldInline` для `false` для предотвращения `calleeId` функции из, вставляемого в `callerId` функции.</span><span class="sxs-lookup"><span data-stu-id="fb396-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="fb396-111">Кроме того, профилировщик глобально можно отключить встроенные вставки с помощью значения COR_PRF_DISABLE_INLINING [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="fb396-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="fb396-112">Встроенные функции не вызывают событий входа или выхода.</span><span class="sxs-lookup"><span data-stu-id="fb396-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="fb396-113">Таким образом, профилировщик должен установить `pfShouldInline` для `false` чтобы обеспечить точность графа.</span><span class="sxs-lookup"><span data-stu-id="fb396-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="fb396-114">Установка `pfShouldInline` для `false` повлияет на производительность, так как встроенный вставки повышается скорость и сокращает число отдельных событий JIT-компиляции для вставляемого метода.</span><span class="sxs-lookup"><span data-stu-id="fb396-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fb396-115">Требования</span><span class="sxs-lookup"><span data-stu-id="fb396-115">Requirements</span></span>  
 <span data-ttu-id="fb396-116">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb396-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb396-117">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fb396-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fb396-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fb396-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fb396-119">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb396-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb396-120">См. также</span><span class="sxs-lookup"><span data-stu-id="fb396-120">See Also</span></span>  
 [<span data-ttu-id="fb396-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="fb396-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
