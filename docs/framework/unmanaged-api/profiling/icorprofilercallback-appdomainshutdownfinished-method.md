---
title: "Метод ICorProfilerCallback::AppDomainShutdownFinished"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainShutdownFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainShutdownFinished
helpviewer_keywords:
- AppDomainShutdownFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainShutdownFinished method [.NET Framework profiling]
ms.assetid: 52794819-0a59-4bb1-a265-0f158cd5cd65
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 443f5cd48693d6ac3ce732746666bd2d5e3786fe
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="6c68c-102">Метод ICorProfilerCallback::AppDomainShutdownFinished</span><span class="sxs-lookup"><span data-stu-id="6c68c-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="6c68c-103">Уведомляет профилировщик о том, что домен приложения выгружен из процесса.</span><span class="sxs-lookup"><span data-stu-id="6c68c-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c68c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6c68c-104">Syntax</span></span>  
  
```  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c68c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6c68c-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="6c68c-106">[in] Определяет домен, в котором хранятся сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="6c68c-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="6c68c-107">[in] Значение HRESULT, указывающее, является ли домен приложения выгружен успешно.</span><span class="sxs-lookup"><span data-stu-id="6c68c-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c68c-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="6c68c-108">Remarks</span></span>  
 <span data-ttu-id="6c68c-109">Значение `appDomainId` является недопустимым для информационного запроса после [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) возвращает метод.</span><span class="sxs-lookup"><span data-stu-id="6c68c-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="6c68c-110">Некоторые части выгрузки домена приложения может быть продолжено после `AppDomainCreationFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="6c68c-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="6c68c-111">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="6c68c-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="6c68c-112">Тем не менее значение HRESULT в `hrStatus` указывает только на том, что в первой части выгрузки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="6c68c-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c68c-113">Требования</span><span class="sxs-lookup"><span data-stu-id="6c68c-113">Requirements</span></span>  
 <span data-ttu-id="6c68c-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c68c-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c68c-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6c68c-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6c68c-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6c68c-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6c68c-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c68c-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c68c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="6c68c-118">See Also</span></span>  
 [<span data-ttu-id="6c68c-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="6c68c-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
