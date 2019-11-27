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
ms.openlocfilehash: 6a0f6dc9d2559bafed416d409063088d2f51c27d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445216"
---
# <a name="icorprofilercallbackappdomaincreationstarted-method"></a><span data-ttu-id="e798a-102">Метод ICorProfilerCallback::AppDomainCreationStarted</span><span class="sxs-lookup"><span data-stu-id="e798a-102">ICorProfilerCallback::AppDomainCreationStarted Method</span></span>
<span data-ttu-id="e798a-103">Уведомляет профилировщик о том, что создается домен приложения.</span><span class="sxs-lookup"><span data-stu-id="e798a-103">Notifies the profiler that an application domain is being created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e798a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e798a-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationStarted(  
    [in] AppDomainID appDomainId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e798a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e798a-105">Parameters</span></span>  
 `appDomainId`  
 <span data-ttu-id="e798a-106">окне Определяет создаваемый домен.</span><span class="sxs-lookup"><span data-stu-id="e798a-106">[in] Identifies the domain which is being created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e798a-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e798a-107">Remarks</span></span>  
 <span data-ttu-id="e798a-108">Идентификатор не является допустимым для запроса информации до вызова метода [ICorProfilerCallback:: аппдомаинкреатионфинишед](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="e798a-108">The ID is not valid for any information request until the [ICorProfilerCallback::AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md) method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e798a-109">Требования</span><span class="sxs-lookup"><span data-stu-id="e798a-109">Requirements</span></span>  
 <span data-ttu-id="e798a-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e798a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e798a-111">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e798a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e798a-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e798a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e798a-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e798a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e798a-114">См. также:</span><span class="sxs-lookup"><span data-stu-id="e798a-114">See also</span></span>

- [<span data-ttu-id="e798a-115">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="e798a-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
