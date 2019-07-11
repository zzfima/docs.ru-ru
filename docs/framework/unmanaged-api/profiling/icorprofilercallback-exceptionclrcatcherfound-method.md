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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 683cec06cd4c2fdef310126adc2921c858ca5687
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776029"
---
# <a name="icorprofilercallbackexceptionclrcatcherfound-method"></a><span data-ttu-id="d15ef-102">Метод ICorProfilerCallback::ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="d15ef-102">ICorProfilerCallback::ExceptionCLRCatcherFound Method</span></span>
<span data-ttu-id="d15ef-103">Вызывается, когда `catch` блоков исключение находится внутри общеязыковой среды выполнения (CLR), сам.</span><span class="sxs-lookup"><span data-stu-id="d15ef-103">Called when a `catch` block for an exception is found inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="d15ef-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="d15ef-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d15ef-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="d15ef-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherFound();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d15ef-106">Требования</span><span class="sxs-lookup"><span data-stu-id="d15ef-106">Requirements</span></span>  
 <span data-ttu-id="d15ef-107">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d15ef-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d15ef-108">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d15ef-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d15ef-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d15ef-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d15ef-110">**Версии платформы .NET framework:** 1.0</span><span class="sxs-lookup"><span data-stu-id="d15ef-110">**.NET Framework Version:** 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d15ef-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d15ef-111">See also</span></span>

- [<span data-ttu-id="d15ef-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="d15ef-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d15ef-113">Метод ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="d15ef-113">ExceptionCLRCatcherExecute Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)
