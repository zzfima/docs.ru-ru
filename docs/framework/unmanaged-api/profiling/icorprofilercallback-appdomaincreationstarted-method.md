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
ms.openlocfilehash: 6e42a8ab23705703770c8214b8c641b48c86094a
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117226"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="f7c0c-102">Метод ICorProfilerCallback::AppDomainCreationStarted</span><span class="sxs-lookup"><span data-stu-id="f7c0c-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="f7c0c-103">Уведомляет профилировщик о том, что создается домен приложения.</span><span class="sxs-lookup"><span data-stu-id="f7c0c-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7c0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f7c0c-104">Syntax</span></span>  
  
```  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f7c0c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f7c0c-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="f7c0c-106">[in] Определяет домен, который создается.</span><span class="sxs-lookup"><span data-stu-id="f7c0c-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7c0c-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="f7c0c-107">Remarks</span></span>  
 <span data-ttu-id="f7c0c-108">Идентификатор не является допустимым для любого запроса информации до [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) вызывается метод.</span><span class="sxs-lookup"><span data-stu-id="f7c0c-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7c0c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="f7c0c-109">Requirements</span></span>  
 <span data-ttu-id="f7c0c-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7c0c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7c0c-111">**Заголовок.** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7c0c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7c0c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7c0c-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f7c0c-113">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="f7c0c-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f7c0c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="f7c0c-114">See also</span></span>

- [<span data-ttu-id="f7c0c-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="f7c0c-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
