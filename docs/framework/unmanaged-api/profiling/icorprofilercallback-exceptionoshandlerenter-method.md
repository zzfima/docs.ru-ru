---
title: Метод ICorProfilerCallback::ExceptionOSHandlerEnter
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionOSHandlerEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionOSHandlerEnter
helpviewer_keywords:
- ExceptionOSHandlerEnter method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionOSHandlerEnter method [.NET Framework profiling]
ms.assetid: 09238b9b-9359-4780-89dc-2f5e4f57920e
topic_type:
- apiref
ms.openlocfilehash: e27fd3147182e8c820fb1d30f172e0517ca4e77e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866485"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="9887a-102">Метод ICorProfilerCallback::ExceptionOSHandlerEnter</span><span class="sxs-lookup"><span data-stu-id="9887a-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="9887a-103">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="9887a-103">Not implemented.</span></span> <span data-ttu-id="9887a-104">Профилировщик, которому требуются сведения о неуправляемом исключении, должен получить эти сведения с помощью других средств.</span><span class="sxs-lookup"><span data-stu-id="9887a-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9887a-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9887a-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="9887a-106">Требования</span><span class="sxs-lookup"><span data-stu-id="9887a-106">Requirements</span></span>  
 <span data-ttu-id="9887a-107">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9887a-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9887a-108">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9887a-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9887a-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9887a-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9887a-110">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9887a-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9887a-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="9887a-111">See also</span></span>

- [<span data-ttu-id="9887a-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="9887a-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
