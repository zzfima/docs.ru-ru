---
title: Метод ICorProfilerCallback2::HandleDestroyed
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.HandleDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::HandleDestroyed
helpviewer_keywords:
- ICorProfilerCallback2::HandleDestroyed method [.NET Framework profiling]
- HandleDestroyed method [.NET Framework profiling]
ms.assetid: ab4f4bbd-40c7-4667-bfde-60cd73803110
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31492711ea9927c07f611ff9ec9bbe49d4857d46
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451965"
---
# <a name="icorprofilercallback2handledestroyed-method"></a><span data-ttu-id="7eae9-102">Метод ICorProfilerCallback2::HandleDestroyed</span><span class="sxs-lookup"><span data-stu-id="7eae9-102">ICorProfilerCallback2::HandleDestroyed Method</span></span>
<span data-ttu-id="7eae9-103">Уведомляет профилировщик кода уничтожение дескриптор сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="7eae9-103">Notifies the code profiler that a garbage collection handle has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7eae9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7eae9-104">Syntax</span></span>  
  
```  
HRESULT HandleDestroyed(  
    [in] GCHandleID handleId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="7eae9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="7eae9-105">Parameters</span></span>  
 `handleId`  
 <span data-ttu-id="7eae9-106">[in] Идентификатор дескриптора для сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="7eae9-106">[in] The ID of the handle for the garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7eae9-107">Требования</span><span class="sxs-lookup"><span data-stu-id="7eae9-107">Requirements</span></span>  
 <span data-ttu-id="7eae9-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7eae9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7eae9-109">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7eae9-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7eae9-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7eae9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7eae9-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7eae9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7eae9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="7eae9-112">See Also</span></span>  
 [<span data-ttu-id="7eae9-113">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="7eae9-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="7eae9-114">Интерфейс ICorProfilerCallback2</span><span class="sxs-lookup"><span data-stu-id="7eae9-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
