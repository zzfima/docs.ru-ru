---
title: "Метод IHostTask::Start"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask.Start
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask::Start
helpviewer_keywords:
- IHostTask::Start method [.NET Framework hosting]
- Start method, IHostTask interface [.NET Framework hosting]
ms.assetid: b18742b0-d8c4-401c-ae89-e6eccdaa81d0
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: db43ec56fac86b0040aa4f701940abf0d1c0df07
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="170cd-102">Метод IHostTask::Start</span><span class="sxs-lookup"><span data-stu-id="170cd-102">IHostTask::Start Method</span></span>
<span data-ttu-id="170cd-103">Запросы, что узел перемещения задач, представленный текущим [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляр из приостановленного состояния в активное, в котором можно выполнять код.</span><span class="sxs-lookup"><span data-stu-id="170cd-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="170cd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="170cd-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="170cd-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="170cd-105">Return Value</span></span>  
  
|<span data-ttu-id="170cd-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="170cd-106">HRESULT</span></span>|<span data-ttu-id="170cd-107">Описание</span><span class="sxs-lookup"><span data-stu-id="170cd-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="170cd-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="170cd-108">S_OK</span></span>|<span data-ttu-id="170cd-109">Запуск успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="170cd-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="170cd-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="170cd-110">E_FAIL</span></span>|<span data-ttu-id="170cd-111">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="170cd-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="170cd-112">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="170cd-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="170cd-113">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="170cd-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="170cd-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="170cd-114">Remarks</span></span>  
 <span data-ttu-id="170cd-115">`Start`всегда возвращает значение HRESULT S_OK, за исключением того, в случаях, где происходит разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="170cd-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="170cd-116">Требования</span><span class="sxs-lookup"><span data-stu-id="170cd-116">Requirements</span></span>  
 <span data-ttu-id="170cd-117">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="170cd-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="170cd-118">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="170cd-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="170cd-119">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="170cd-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="170cd-120">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="170cd-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="170cd-121">См. также</span><span class="sxs-lookup"><span data-stu-id="170cd-121">See Also</span></span>  
 [<span data-ttu-id="170cd-122">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="170cd-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="170cd-123">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="170cd-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="170cd-124">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="170cd-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="170cd-125">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="170cd-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
