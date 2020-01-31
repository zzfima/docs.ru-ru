---
title: Метод ICorProfilerCallback::ExceptionCLRCatcherExecute
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherExecute
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherExecute
helpviewer_keywords:
- ExceptionCLRCatcherExecute method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCLRCatcherExecute method [.NET Framework profiling]
ms.assetid: aaac8f98-5cf4-42c7-b04b-556cce367e36
topic_type:
- apiref
ms.openlocfilehash: f14dff33217656c35379a214f007ccb3642ef4b1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866459"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="61ce2-102">Метод ICorProfilerCallback::ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="61ce2-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="61ce2-103">Вызывается, когда блок `catch` для исключения выполняется в самой среде CLR.</span><span class="sxs-lookup"><span data-stu-id="61ce2-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="61ce2-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="61ce2-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61ce2-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="61ce2-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="61ce2-106">Требования</span><span class="sxs-lookup"><span data-stu-id="61ce2-106">Requirements</span></span>  
 <span data-ttu-id="61ce2-107">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61ce2-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61ce2-108">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="61ce2-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="61ce2-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="61ce2-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="61ce2-110">**.NET Framework версии:** 1,1, 1,0</span><span class="sxs-lookup"><span data-stu-id="61ce2-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61ce2-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="61ce2-111">See also</span></span>

- [<span data-ttu-id="61ce2-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="61ce2-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="61ce2-113">Метод ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="61ce2-113">ExceptionCLRCatcherFound Method</span></span>](icorprofilercallback-exceptionclrcatcherfound-method.md)
