---
title: Метод ICorProfilerCallback::AppDomainCreationFinished
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a08a0ed8303804df1889973fe3ffab6db93249d5
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57481447"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="8f292-102">Метод ICorProfilerCallback::AppDomainCreationFinished</span><span class="sxs-lookup"><span data-stu-id="8f292-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="8f292-103">Уведомляет профилировщик, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="8f292-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f292-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8f292-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="8f292-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8f292-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="8f292-106">[in] Определяет домен, который был создан.</span><span class="sxs-lookup"><span data-stu-id="8f292-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="8f292-107">[in] Значение HRESULT, указывающее, успешно ли завершено создание домена приложения.</span><span class="sxs-lookup"><span data-stu-id="8f292-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f292-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="8f292-108">Remarks</span></span>  
 <span data-ttu-id="8f292-109">Идентификатор приложения не является допустимым для любого запроса информации до `AppDomainCreationFinished` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="8f292-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="8f292-110">Некоторые части загрузки домена приложения может по-прежнему после `AppDomainCreationFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="8f292-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="8f292-111">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="8f292-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="8f292-112">Тем не менее значение HRESULT в `hrStatus` указывает только что первая часть создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="8f292-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f292-113">Требования</span><span class="sxs-lookup"><span data-stu-id="8f292-113">Requirements</span></span>  
 <span data-ttu-id="8f292-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f292-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f292-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f292-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f292-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f292-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f292-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f292-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f292-118">См. также</span><span class="sxs-lookup"><span data-stu-id="8f292-118">See also</span></span>
- [<span data-ttu-id="8f292-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="8f292-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
