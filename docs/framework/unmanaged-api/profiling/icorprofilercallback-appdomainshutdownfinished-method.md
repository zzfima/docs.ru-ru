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
ms.openlocfilehash: 8ff7d5a593388bd3a584e031aea411dfdb6c9845
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445195"
---
# <a name="icorprofilercallbackappdomainshutdownfinished-method"></a><span data-ttu-id="c7f2f-102">Метод ICorProfilerCallback::AppDomainShutdownFinished</span><span class="sxs-lookup"><span data-stu-id="c7f2f-102">ICorProfilerCallback::AppDomainShutdownFinished Method</span></span>
<span data-ttu-id="c7f2f-103">Уведомляет профилировщик о том, что домен приложения был выгружен из процесса.</span><span class="sxs-lookup"><span data-stu-id="c7f2f-103">Notifies the profiler that an application domain has been unloaded from a process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c7f2f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c7f2f-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainShutdownFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c7f2f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c7f2f-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="c7f2f-106">окне Определяет домен, в котором хранятся сборки приложения.</span><span class="sxs-lookup"><span data-stu-id="c7f2f-106">[in] Identifies the domain in which the application's assemblies are stored.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="c7f2f-107">окне Значение HRESULT, указывающее, успешно ли выгружен домен приложения.</span><span class="sxs-lookup"><span data-stu-id="c7f2f-107">[in] An HRESULT that indicates whether the application domain was unloaded successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c7f2f-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="c7f2f-108">Remarks</span></span>  
 <span data-ttu-id="c7f2f-109">Значение `appDomainId` недопустимо для информационного запроса после возврата метода [ICorProfilerCallback:: AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="c7f2f-109">The value of `appDomainId` is not valid for an information request after the [ICorProfilerCallback::AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md) method returns.</span></span>  
  
 <span data-ttu-id="c7f2f-110">Некоторые части выгрузки домена приложения могут продолжаться после обратного вызова `AppDomainCreationFinished`.</span><span class="sxs-lookup"><span data-stu-id="c7f2f-110">Some parts of unloading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="c7f2f-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="c7f2f-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="c7f2f-112">Однако значение HRESULT успешного выполнения в `hrStatus` указывает, что первая часть выгрузки домена приложения успешно выполнена.</span><span class="sxs-lookup"><span data-stu-id="c7f2f-112">However, a success HRESULT in `hrStatus` indicates only that the first part of unloading the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c7f2f-113">Требования</span><span class="sxs-lookup"><span data-stu-id="c7f2f-113">Requirements</span></span>  
 <span data-ttu-id="c7f2f-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c7f2f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c7f2f-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c7f2f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c7f2f-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c7f2f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c7f2f-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c7f2f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7f2f-118">См. также</span><span class="sxs-lookup"><span data-stu-id="c7f2f-118">See also</span></span>

- [<span data-ttu-id="c7f2f-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="c7f2f-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
