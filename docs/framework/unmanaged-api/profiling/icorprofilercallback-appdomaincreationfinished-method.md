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
ms.openlocfilehash: 35dac5fd000f5ae30af917e3813239b2e365e64a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59153989"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="162c1-102">Метод ICorProfilerCallback::AppDomainCreationFinished</span><span class="sxs-lookup"><span data-stu-id="162c1-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="162c1-103">Уведомляет профилировщик, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="162c1-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="162c1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="162c1-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="162c1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="162c1-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="162c1-106">[in] Определяет домен, который был создан.</span><span class="sxs-lookup"><span data-stu-id="162c1-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="162c1-107">[in] Значение HRESULT, указывающее, успешно ли завершено создание домена приложения.</span><span class="sxs-lookup"><span data-stu-id="162c1-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="162c1-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="162c1-108">Remarks</span></span>  
 <span data-ttu-id="162c1-109">Идентификатор приложения не является допустимым для любого запроса информации до `AppDomainCreationFinished` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="162c1-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="162c1-110">Некоторые части загрузки домена приложения может по-прежнему после `AppDomainCreationFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="162c1-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="162c1-111">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="162c1-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="162c1-112">Тем не менее значение HRESULT в `hrStatus` указывает только что первая часть создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="162c1-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="162c1-113">Требования</span><span class="sxs-lookup"><span data-stu-id="162c1-113">Requirements</span></span>  
 <span data-ttu-id="162c1-114">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="162c1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="162c1-115">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="162c1-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="162c1-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="162c1-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="162c1-117">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="162c1-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="162c1-118">См. также</span><span class="sxs-lookup"><span data-stu-id="162c1-118">See also</span></span>

- [<span data-ttu-id="162c1-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="162c1-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
