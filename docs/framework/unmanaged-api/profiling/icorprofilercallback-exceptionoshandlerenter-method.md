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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d9167b35556fafb33e61e1dc050488aec2b7fa01
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776011"
---
# <a name="icorprofilercallbackexceptionoshandlerenter-method"></a><span data-ttu-id="e14f6-102">Метод ICorProfilerCallback::ExceptionOSHandlerEnter</span><span class="sxs-lookup"><span data-stu-id="e14f6-102">ICorProfilerCallback::ExceptionOSHandlerEnter Method</span></span>
<span data-ttu-id="e14f6-103">Не реализовано.</span><span class="sxs-lookup"><span data-stu-id="e14f6-103">Not implemented.</span></span> <span data-ttu-id="e14f6-104">Профилировщик, необходимы сведения о неуправляемых исключений необходимо получить эту информацию другим способом.</span><span class="sxs-lookup"><span data-stu-id="e14f6-104">A profiler that needs unmanaged exception information must obtain this information through other means.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e14f6-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e14f6-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionOSHandlerEnter(  
    [in] UINT_PTR __unused);  
```  
  
## <a name="requirements"></a><span data-ttu-id="e14f6-106">Требования</span><span class="sxs-lookup"><span data-stu-id="e14f6-106">Requirements</span></span>  
 <span data-ttu-id="e14f6-107">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e14f6-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e14f6-108">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e14f6-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e14f6-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e14f6-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e14f6-110">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e14f6-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e14f6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="e14f6-111">See also</span></span>

- [<span data-ttu-id="e14f6-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e14f6-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
