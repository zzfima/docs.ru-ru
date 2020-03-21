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
ms.openlocfilehash: 8b3f7712436c001e5cd44f214f6edb06390abd41
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177076"
---
# <a name="icorprofilercallbackappdomaincreationfinished-method"></a><span data-ttu-id="09944-102">Метод ICorProfilerCallback::AppDomainCreationFinished</span><span class="sxs-lookup"><span data-stu-id="09944-102">ICorProfilerCallback::AppDomainCreationFinished Method</span></span>
<span data-ttu-id="09944-103">Уведомляет профайлера о том, что был создан домен приложения.</span><span class="sxs-lookup"><span data-stu-id="09944-103">Notifies the profiler that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09944-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="09944-104">Syntax</span></span>  
  
```cpp  
HRESULT AppDomainCreationFinished(  
    [in] AppDomainID appDomainId,  
    [in] HRESULT     hrStatus);
```  
  
## <a name="parameters"></a><span data-ttu-id="09944-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="09944-105">Parameters</span></span>

- `appDomainId`

  <span data-ttu-id="09944-106">\[в» определяет созданный домен.</span><span class="sxs-lookup"><span data-stu-id="09944-106">\[in] Identifies the domain which has been created.</span></span>

- `hrStatus`

  <span data-ttu-id="09944-107">\[в HRESULT, который указывает, успешно ли завершено создание домена приложения.</span><span class="sxs-lookup"><span data-stu-id="09944-107">\[in] An HRESULT that indicates whether creation of the application domain completed successfully.</span></span>

## <a name="remarks"></a><span data-ttu-id="09944-108">Remarks</span><span class="sxs-lookup"><span data-stu-id="09944-108">Remarks</span></span>  
 <span data-ttu-id="09944-109">Идентификатор приложения не действителен `AppDomainCreationFinished` для любого запроса информации до тех пор, пока метод не будет вызван.</span><span class="sxs-lookup"><span data-stu-id="09944-109">The application ID is not valid for any information request until the `AppDomainCreationFinished` method is called.</span></span>  
  
 <span data-ttu-id="09944-110">Некоторые части загрузки домена приложения `AppDomainCreationFinished` могут продолжиться после обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="09944-110">Some parts of loading the application domain might continue after the `AppDomainCreationFinished` callback.</span></span> <span data-ttu-id="09944-111">Сбой HRESULT `hrStatus` в указывает на сбой.</span><span class="sxs-lookup"><span data-stu-id="09944-111">A failure HRESULT in `hrStatus` indicates a failure.</span></span> <span data-ttu-id="09944-112">Тем не менее, `hrStatus` успех HRESULT в указывает только на то, что первая часть создания домена приложения удалось.</span><span class="sxs-lookup"><span data-stu-id="09944-112">However, a success HRESULT in `hrStatus` indicates only that the first part of creating the application domain has succeeded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09944-113">Требования</span><span class="sxs-lookup"><span data-stu-id="09944-113">Requirements</span></span>  
 <span data-ttu-id="09944-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09944-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09944-115">**Заголовок:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09944-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09944-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09944-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09944-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09944-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09944-118">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="09944-118">See also</span></span>

- [<span data-ttu-id="09944-119">Интерфейс ICorProfilerCallback</span><span class="sxs-lookup"><span data-stu-id="09944-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
