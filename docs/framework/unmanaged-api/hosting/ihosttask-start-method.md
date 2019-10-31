---
title: Метод IHostTask::Start
ms.date: 03/30/2017
api_name:
- IHostTask.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type:
- apiref
ms.openlocfilehash: fe93a3bab267ccca941974b734c86329ad0f4d03
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121336"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="081bc-102">Метод IHostTask::Start</span><span class="sxs-lookup"><span data-stu-id="081bc-102">IHostTask::Start Method</span></span>
<span data-ttu-id="081bc-103">Запрашивает, что узел перемещает задачу, представленную текущим экземпляром [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) , из приостановленного в активное состояние, в котором можно выполнить код.</span><span class="sxs-lookup"><span data-stu-id="081bc-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="081bc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="081bc-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="081bc-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="081bc-105">Return Value</span></span>  
  
|<span data-ttu-id="081bc-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="081bc-106">HRESULT</span></span>|<span data-ttu-id="081bc-107">Описание</span><span class="sxs-lookup"><span data-stu-id="081bc-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="081bc-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="081bc-108">S_OK</span></span>|<span data-ttu-id="081bc-109">Успешное начало возврата.</span><span class="sxs-lookup"><span data-stu-id="081bc-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="081bc-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="081bc-110">E_FAIL</span></span>|<span data-ttu-id="081bc-111">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="081bc-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="081bc-112">Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="081bc-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="081bc-113">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="081bc-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="081bc-114">Заметки</span><span class="sxs-lookup"><span data-stu-id="081bc-114">Remarks</span></span>  
 <span data-ttu-id="081bc-115">`Start` всегда возвращает значение HRESULT, равное S_OK, за исключением случаев, когда произошла разрушительная ошибка.</span><span class="sxs-lookup"><span data-stu-id="081bc-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="081bc-116">Требования</span><span class="sxs-lookup"><span data-stu-id="081bc-116">Requirements</span></span>  
 <span data-ttu-id="081bc-117">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="081bc-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="081bc-118">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="081bc-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="081bc-119">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="081bc-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="081bc-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="081bc-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="081bc-121">См. также</span><span class="sxs-lookup"><span data-stu-id="081bc-121">See also</span></span>

- [<span data-ttu-id="081bc-122">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="081bc-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="081bc-123">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="081bc-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="081bc-124">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="081bc-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="081bc-125">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="081bc-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
