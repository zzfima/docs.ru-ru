---
title: Метод ICorProfilerCallback::ExceptionCLRCatcherFound
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCLRCatcherFound
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCLRCatcherFound method [.NET Framework profiling]
- ExceptionCLRCatcherFound method [.NET Framework profiling]
ms.assetid: 73fe8b4b-8f9a-4ba5-a10c-b26521396a66
topic_type:
- apiref
ms.openlocfilehash: ef5122d49c428af4faa27f3827a5c60721ef0f74
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74435825"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="2abbf-102">Метод ICorProfilerCallback::ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="2abbf-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="2abbf-103">Вызывается, когда блок `catch` для исключения находится внутри самой среды CLR.</span><span class="sxs-lookup"><span data-stu-id="2abbf-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="2abbf-104">Этот метод является устаревшим в .NET Framework версии 2,0.</span><span class="sxs-lookup"><span data-stu-id="2abbf-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2abbf-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2abbf-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="2abbf-106">Требования</span><span class="sxs-lookup"><span data-stu-id="2abbf-106">Requirements</span></span>  
 <span data-ttu-id="2abbf-107">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2abbf-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2abbf-108">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2abbf-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="2abbf-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2abbf-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2abbf-110">**Версия .NET Framework:** 1,0</span><span class="sxs-lookup"><span data-stu-id="2abbf-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2abbf-111">См. также:</span><span class="sxs-lookup"><span data-stu-id="2abbf-111">See also</span></span>

- [<span data-ttu-id="2abbf-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="2abbf-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="2abbf-113">Метод ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="2abbf-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
