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
ms.openlocfilehash: 1cf3f2b62b388b6c2d6fcd75b1b07a67d5b2e49f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866707"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="15f3b-102">Метод ICorProfilerCallback::AppDomainCreationFinished</span><span class="sxs-lookup"><span data-stu-id="15f3b-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="15f3b-103">Уведомляет профилировщик о том, что домен приложения создан.</span><span class="sxs-lookup"><span data-stu-id="15f3b-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15f3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="15f3b-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);   
```  
  
## <a name="parameters"></a><span data-ttu-id="15f3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="15f3b-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="15f3b-106">\[в] определяет домен, который был создан.</span><span class="sxs-lookup"><span data-stu-id="15f3b-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="15f3b-107">\[in] значение HRESULT, указывающее, успешно ли выполнено создание домена приложения.</span><span class="sxs-lookup"><span data-stu-id="15f3b-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="15f3b-108">Заметки</span><span class="sxs-lookup"><span data-stu-id="15f3b-108">Remarks</span></span>  
 <span data-ttu-id="15f3b-109">Идентификатор приложения не является допустимым для запроса информации, пока не будет вызван метод `AppDomainCreationFinished`.</span><span class="sxs-lookup"><span data-stu-id="15f3b-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="15f3b-110">Некоторые части загрузки домена приложения могут продолжаться после обратного вызова `AppDomainCreationFinished`.</span><span class="sxs-lookup"><span data-stu-id="15f3b-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="15f3b-111">Ошибка HRESULT в `hrStatus` указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="15f3b-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="15f3b-112">Однако значение HRESULT успешного выполнения в `hrStatus` указывает, что первая часть создания домена приложения успешно выполнена.</span><span class="sxs-lookup"><span data-stu-id="15f3b-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="15f3b-113">Требования</span><span class="sxs-lookup"><span data-stu-id="15f3b-113">Requirements</span></span>  
 <span data-ttu-id="15f3b-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="15f3b-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15f3b-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="15f3b-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="15f3b-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="15f3b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="15f3b-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15f3b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15f3b-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="15f3b-118">See also</span></span>

- [<span data-ttu-id="15f3b-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="15f3b-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
