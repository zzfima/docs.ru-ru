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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d927bd21903bda6fd8a34992145eb495a3342382
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61598263"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="6d28d-102">Метод ICorProfilerCallback::AppDomainShutdownFinished</span><span class="sxs-lookup"><span data-stu-id="6d28d-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="6d28d-103">Уведомляет профилировщик о том, что домен приложения был выгружен из процесса.</span><span class="sxs-lookup"><span data-stu-id="6d28d-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6d28d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6d28d-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6d28d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6d28d-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="6d28d-106">[in] Определяет домен, в котором хранятся сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="6d28d-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="6d28d-107">[in] Значение HRESULT, указывающее, является ли домен приложения был успешно высвобожден.</span><span class="sxs-lookup"><span data-stu-id="6d28d-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6d28d-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6d28d-108">Remarks</span></span>  
 <span data-ttu-id="6d28d-109">Значение `appDomainId` не является допустимым для информационного запроса после [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) возвращает метод.</span><span class="sxs-lookup"><span data-stu-id="6d28d-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="6d28d-110">Некоторые части выгрузки домена приложения может по-прежнему после `AppDomainCreationFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="6d28d-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="6d28d-111">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="6d28d-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="6d28d-112">Тем не менее значение HRESULT в `hrStatus` указывает только что в первой части выгрузки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="6d28d-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6d28d-113">Требования</span><span class="sxs-lookup"><span data-stu-id="6d28d-113">Requirements</span></span>  
 <span data-ttu-id="6d28d-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6d28d-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6d28d-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6d28d-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6d28d-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6d28d-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6d28d-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6d28d-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d28d-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6d28d-118">See also</span></span>

- [<span data-ttu-id="6d28d-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="6d28d-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
