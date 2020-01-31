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
ms.openlocfilehash: d280b008b34befce04159d02dfbb3de37b262c3c
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866668"
---
# <a name="icorprofilercallbackappdomainshutdownstarted-method"></a><span data-ttu-id="b4d44-102">Метод ICorProfilerCallback::AppDomainShutdownStarted</span><span class="sxs-lookup"><span data-stu-id="b4d44-102">ICorProfilerCallback::AppDomainShutdownStarted Method</span></span>
<span data-ttu-id="b4d44-103">Уведомляет профилировщик о том, что домен приложения выгружается из процесса.</span><span class="sxs-lookup"><span data-stu-id="b4d44-103">Notifies the profiler that an application domain is being unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4d44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4d44-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4d44-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4d44-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="b4d44-106">\[в] определяет домен, в котором хранятся сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="b4d44-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4d44-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="b4d44-107">Remarks</span></span>  
 <span data-ttu-id="b4d44-108">Значение `appDomainId` недопустимо для запроса информации после возврата метода `AppDomainShutdownStarted` — это последний шанс профилировщика получить сведения об этом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="b4d44-108">The value of `appDomainId` is not valid for any information request after the `AppDomainShutdownStarted` method returns — this is the profiler's last chance to get information about this application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4d44-109">Требования</span><span class="sxs-lookup"><span data-stu-id="b4d44-109">Requirements</span></span>  
 <span data-ttu-id="b4d44-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4d44-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4d44-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b4d44-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b4d44-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4d44-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4d44-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4d44-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4d44-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="b4d44-114">See also</span></span>

- [<span data-ttu-id="b4d44-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="b4d44-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
