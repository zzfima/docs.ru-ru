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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2a17776b38d7e16b39f966e0d83d50a7d004d4c3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776072"
---
# <a name="icorprofilercallbackexceptionclrcatcherexecute-method"></a><span data-ttu-id="4ca60-102">Метод ICorProfilerCallback::ExceptionCLRCatcherExecute</span><span class="sxs-lookup"><span data-stu-id="4ca60-102">ICorProfilerCallback::ExceptionCLRCatcherExecute Method</span></span>
<span data-ttu-id="4ca60-103">Вызывается, когда `catch` блоков исключения выполняется внутри общеязыковой среды выполнения (CLR), сам.</span><span class="sxs-lookup"><span data-stu-id="4ca60-103">Called when a `catch` block for an exception is executed inside the common language runtime (CLR) itself.</span></span> <span data-ttu-id="4ca60-104">Этот метод является устаревшим в .NET Framework версии 2.0.</span><span class="sxs-lookup"><span data-stu-id="4ca60-104">This method is obsolete in the .NET Framework version 2.0.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4ca60-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4ca60-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCLRCatcherExecute();  
```  
  
## <a name="requirements"></a><span data-ttu-id="4ca60-106">Требования</span><span class="sxs-lookup"><span data-stu-id="4ca60-106">Requirements</span></span>  
 <span data-ttu-id="4ca60-107">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4ca60-107">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4ca60-108">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4ca60-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4ca60-109">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4ca60-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4ca60-110">**Версии платформы .NET framework:** 1.1, 1.0</span><span class="sxs-lookup"><span data-stu-id="4ca60-110">**.NET Framework Versions:** 1.1, 1.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ca60-111">См. также</span><span class="sxs-lookup"><span data-stu-id="4ca60-111">See also</span></span>

- [<span data-ttu-id="4ca60-112">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4ca60-112">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="4ca60-113">Метод ExceptionCLRCatcherFound</span><span class="sxs-lookup"><span data-stu-id="4ca60-113">ExceptionCLRCatcherFound Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)
