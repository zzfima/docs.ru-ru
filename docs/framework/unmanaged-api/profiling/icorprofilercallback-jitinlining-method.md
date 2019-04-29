---
title: Метод ICorProfilerCallback::JITInlining
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITInlining
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITInlining
helpviewer_keywords:
- JITInlining method [.NET Framework profiling]
- ICorProfilerCallback::JITInlining method [.NET Framework profiling]
ms.assetid: c2f45801-dd38-4b78-b6b7-64397dc73f83
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60183291fda551e328ee1def03c02240314a71e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598237"
---
# <a name="icorprofilercallbackjitinlining-method"></a><span data-ttu-id="14a35-102">Метод ICorProfilerCallback::JITInlining</span><span class="sxs-lookup"><span data-stu-id="14a35-102">ICorProfilerCallback::JITInlining Method</span></span>
<span data-ttu-id="14a35-103">Уведомляет профилировщик, что компилятор just-in-time (JIT) сейчас вставить функцию в одну строку другой функции.</span><span class="sxs-lookup"><span data-stu-id="14a35-103">Notifies the profiler that the just-in-time (JIT) compiler is about to insert a function in line with another function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14a35-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="14a35-104">Syntax</span></span>  
  
```  
HRESULT JITInlining(  
    [in]  FunctionID callerId,  
    [in]  FunctionID calleeId,  
    [out] BOOL      *pfShouldInline);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14a35-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="14a35-105">Parameters</span></span>  
 `callerId`  
 <span data-ttu-id="14a35-106">[in] Идентификатор функции, в которую `calleeId` функция будет вставлен.</span><span class="sxs-lookup"><span data-stu-id="14a35-106">[in] The ID of the function into which the `calleeId` function will be inserted.</span></span>  
  
 `calleeId`  
 <span data-ttu-id="14a35-107">[in] Идентификатор функции для вставки.</span><span class="sxs-lookup"><span data-stu-id="14a35-107">[in] The ID of the function to be inserted.</span></span>  
  
 `pfShouldInline`  
 <span data-ttu-id="14a35-108">[out] `true` для допускает вставку синхронизации; в противном случае `false`.</span><span class="sxs-lookup"><span data-stu-id="14a35-108">[out] `true` to allow the insertion to occur; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14a35-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="14a35-109">Remarks</span></span>  
 <span data-ttu-id="14a35-110">Профилировщик можно задать `pfShouldInline` для `false` во избежание `calleeId` функции из, вставляемого в `callerId` функции.</span><span class="sxs-lookup"><span data-stu-id="14a35-110">The profiler can set `pfShouldInline` to `false` to prevent the `calleeId` function from being inserted into the `callerId` function.</span></span> <span data-ttu-id="14a35-111">Кроме того, профилировщик глобально можно отключить встроенные вставки с помощью значение COR_PRF_DISABLE_INLINING [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) перечисления.</span><span class="sxs-lookup"><span data-stu-id="14a35-111">Also, the profiler can globally disable inline insertion by using the COR_PRF_DISABLE_INLINING value of the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>  
  
 <span data-ttu-id="14a35-112">Встроенные функции не вызывают событий входа или выхода.</span><span class="sxs-lookup"><span data-stu-id="14a35-112">Functions inserted inline do not raise events for entering or leaving.</span></span> <span data-ttu-id="14a35-113">Таким образом, профилировщик должен установить `pfShouldInline` для `false` чтобы обеспечить точность графа.</span><span class="sxs-lookup"><span data-stu-id="14a35-113">Therefore, the profiler must set `pfShouldInline` to `false` in order to produce an accurate callgraph.</span></span> <span data-ttu-id="14a35-114">Установка `pfShouldInline` для `false` повлияет на производительность, так как встроенный вставки повышается скорость и сокращает количество отдельных событий JIT-компиляции для вставляемого метода.</span><span class="sxs-lookup"><span data-stu-id="14a35-114">Setting `pfShouldInline` to `false` will affect performance, because inline insertion typically increases speed and reduces the number of separate JIT compilation events for the inserted method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="14a35-115">Требования</span><span class="sxs-lookup"><span data-stu-id="14a35-115">Requirements</span></span>  
 <span data-ttu-id="14a35-116">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14a35-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14a35-117">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="14a35-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="14a35-118">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14a35-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14a35-119">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14a35-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a35-120">См. также</span><span class="sxs-lookup"><span data-stu-id="14a35-120">See also</span></span>

- [<span data-ttu-id="14a35-121">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="14a35-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
