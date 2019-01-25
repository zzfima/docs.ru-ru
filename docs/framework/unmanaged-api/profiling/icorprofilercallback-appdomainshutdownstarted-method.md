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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6e7679fd8010ebe06f20a2a894cbc8e9864b81f4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54705499"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="accae-102">Метод ICorProfilerCallback::AppDomainShutdownStarted</span><span class="sxs-lookup"><span data-stu-id="accae-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="accae-103">Уведомляет профилировщик о том, что домен приложения выгружается из процесса.</span><span class="sxs-lookup"><span data-stu-id="accae-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="accae-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="accae-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="accae-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="accae-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="accae-106">[in] Определяет домен, в котором хранятся сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="accae-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="accae-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="accae-107">Remarks</span></span>  
 <span data-ttu-id="accae-108">Значение `appDomainId` не является допустимым для любого запроса информации после `AppDomainShutdownStarted` возвращает метод — это последняя возможность профилировщика для получения сведений о домене приложения.</span><span class="sxs-lookup"><span data-stu-id="accae-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="accae-109">Требования</span><span class="sxs-lookup"><span data-stu-id="accae-109">Requirements</span></span>  
 <span data-ttu-id="accae-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="accae-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="accae-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="accae-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="accae-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="accae-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="accae-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="accae-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="accae-114">См. также</span><span class="sxs-lookup"><span data-stu-id="accae-114">See also</span></span>
- [<span data-ttu-id="accae-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="accae-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
