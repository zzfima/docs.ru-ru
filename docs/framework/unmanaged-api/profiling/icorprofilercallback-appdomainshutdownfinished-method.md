---
title: Метод ICorProfilerCallback::AppDomainShutdownFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainShutdownFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type:
- apiref
ms.openlocfilehash: 0851ac33a2bac4fcf727cf09e5225f6b83481b50
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866680"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="e8764-102">Метод ICorProfilerCallback::AppDomainShutdownFinished</span><span class="sxs-lookup"><span data-stu-id="e8764-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="e8764-103">Уведомляет профилировщик о том, что домен приложения был выгружен из процесса.</span><span class="sxs-lookup"><span data-stu-id="e8764-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8764-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e8764-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8764-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e8764-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="e8764-106">\[в] определяет домен, в котором хранятся сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="e8764-106">\[in] Identifies the domain in which the application's assemblies are stored.</span></span>

- `hrStatus`

  <span data-ttu-id="e8764-107">\[in] значение HRESULT, указывающее, успешно ли выгружен домен приложения.</span><span class="sxs-lookup"><span data-stu-id="e8764-107">\[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="e8764-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="e8764-108">Remarks</span></span>  
 <span data-ttu-id="e8764-109">Значение `appDomainId` недопустимо для информационного запроса после возврата метода [ICorProfilerCallback:: AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e8764-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="e8764-110">Некоторые части выгрузки домена приложения могут продолжаться после обратного вызова `AppDomainCreationFinished`.</span><span class="sxs-lookup"><span data-stu-id="e8764-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="e8764-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="e8764-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="e8764-112">Однако значение HRESULT успешного выполнения в `hrStatus` указывает, что первая часть выгрузки домена приложения успешно выполнена.</span><span class="sxs-lookup"><span data-stu-id="e8764-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8764-113">Требования</span><span class="sxs-lookup"><span data-stu-id="e8764-113">Requirements</span></span>  
 <span data-ttu-id="e8764-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8764-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8764-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e8764-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e8764-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e8764-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e8764-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8764-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8764-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="e8764-118">See also</span></span>

- [<span data-ttu-id="e8764-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e8764-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
