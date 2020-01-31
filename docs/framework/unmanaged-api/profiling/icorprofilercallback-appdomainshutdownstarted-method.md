---
title: Метод ICorProfilerCallback::AppDomainShutdownStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownStarted
helpviewer_keywords:
- AppDomainShutdownStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownStarted method [.NET Framework profiling]
ms.assetid: d23a3408-b525-4aec-a186-2ac7ca65d7a4
topic_type:
- apiref
ms.openlocfilehash: 6edf498d506a0ca914124a284c0da3f869f28130
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790220"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="c4dec-102">Метод ICorProfilerCallback::AppDomainShutdownStarted</span><span class="sxs-lookup"><span data-stu-id="c4dec-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="c4dec-103">Уведомляет профилировщик о том, что домен приложения выгружается из процесса.</span><span class="sxs-lookup"><span data-stu-id="c4dec-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4dec-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c4dec-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4dec-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c4dec-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="c4dec-106">\[в] определяет домен, в котором хранятся сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="c4dec-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="c4dec-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="c4dec-107">Remarks</span></span>  
 <span data-ttu-id="c4dec-108">Значение `appDomainId` недопустимо для запроса информации после возврата метода `AppDomainShutdownStarted` — это последний шанс профилировщика получить сведения об этом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="c4dec-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4dec-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c4dec-109">Requirements</span></span>  
 <span data-ttu-id="c4dec-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c4dec-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4dec-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c4dec-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c4dec-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c4dec-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c4dec-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4dec-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4dec-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="c4dec-114">See also</span></span>

- [<span data-ttu-id="c4dec-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c4dec-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
