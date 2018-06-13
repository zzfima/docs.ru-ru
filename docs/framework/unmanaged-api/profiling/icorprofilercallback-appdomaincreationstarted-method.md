---
title: Метод ICorProfilerCallback::AppDomainCreationStarted
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.AppDomainCreationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::AppDomainCreationStarted
helpviewer_keywords:
- AppDomainCreationStarted method [.NET Framework profiling]
- ICorProfilerCallback::AppDomainCreationStarted method [.NET Framework profiling]
ms.assetid: b2a8240b-07fe-4859-bb2b-7d3adbfa0a9f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 141fd99ab0a96b20bfe06f1eb8612dd92b6cccc0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451494"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="505e7-102">Метод ICorProfilerCallback::AppDomainCreationStarted</span><span class="sxs-lookup"><span data-stu-id="505e7-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="505e7-103">Уведомляет профилировщик создания домена приложения.</span><span class="sxs-lookup"><span data-stu-id="505e7-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="505e7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="505e7-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="505e7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="505e7-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="505e7-106">[in] Определяет домен, который находится в процессе создания.</span><span class="sxs-lookup"><span data-stu-id="505e7-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="505e7-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="505e7-107">Remarks</span></span>  
 <span data-ttu-id="505e7-108">Недопустимый идентификатор для любого запроса информации до [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="505e7-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="505e7-109">Требования</span><span class="sxs-lookup"><span data-stu-id="505e7-109">Requirements</span></span>  
 <span data-ttu-id="505e7-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="505e7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="505e7-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="505e7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="505e7-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="505e7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="505e7-113">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="505e7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="505e7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="505e7-114">See Also</span></span>  
 [<span data-ttu-id="505e7-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="505e7-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
