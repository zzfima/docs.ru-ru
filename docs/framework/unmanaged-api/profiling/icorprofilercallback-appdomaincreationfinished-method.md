---
title: "Метод ICorProfilerCallback::AppDomainCreationFinished"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.AppDomainCreationFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::AppDomainCreationFinished
helpviewer_keywords:
- AppDomainCreationFinished method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationFinished method [.NET Framework profiling]
ms.assetid: dbab7d90-d515-4dc9-8195-294d5d04bab6
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f779e5a7b0b38558593e84c26b33784383765ca0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="4f9df-102">Метод ICorProfilerCallback::AppDomainCreationFinished</span><span class="sxs-lookup"><span data-stu-id="4f9df-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="4f9df-103">Уведомляет профилировщик, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="4f9df-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f9df-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4f9df-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="4f9df-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="4f9df-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="4f9df-106">[in] Определяет домен, который был создан.</span><span class="sxs-lookup"><span data-stu-id="4f9df-106">[in] Identifies the domain which has been created.</span></span>  
  
 `hrStatus`  
 <span data-ttu-id="4f9df-107">[in] Значение HRESULT, указывающее, успешно ли выполнено создание домена приложения.</span><span class="sxs-lookup"><span data-stu-id="4f9df-107">[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4f9df-108">Примечания</span><span class="sxs-lookup"><span data-stu-id="4f9df-108">Remarks</span></span>  
 <span data-ttu-id="4f9df-109">Идентификатор приложения является недопустимым для любого запроса информации до `AppDomainCreationFinished` вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="4f9df-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="4f9df-110">Некоторые части загрузки домена приложения может быть продолжено после `AppDomainCreationFinished` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="4f9df-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="4f9df-111">Значение HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="4f9df-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="4f9df-112">Тем не менее значение HRESULT в `hrStatus` указывает, что первая часть создания домена приложения выполнено успешно.</span><span class="sxs-lookup"><span data-stu-id="4f9df-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f9df-113">Требования</span><span class="sxs-lookup"><span data-stu-id="4f9df-113">Requirements</span></span>  
 <span data-ttu-id="4f9df-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f9df-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f9df-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4f9df-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4f9df-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4f9df-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4f9df-117">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f9df-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f9df-118">См. также</span><span class="sxs-lookup"><span data-stu-id="4f9df-118">See Also</span></span>  
 [<span data-ttu-id="4f9df-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="4f9df-119">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
