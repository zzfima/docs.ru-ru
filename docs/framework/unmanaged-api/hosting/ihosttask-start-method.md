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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d45c5b09358430535438734b38e5dce5d1bcdd3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789504"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="e12db-102">Метод IHostTask::Start</span><span class="sxs-lookup"><span data-stu-id="e12db-102">IHostTask::Start Method</span></span>
<span data-ttu-id="e12db-103">Запросы, что узел перемещения задач, представленный текущим [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляр из приостановленного состояния в активное, в котором можно выполнять код.</span><span class="sxs-lookup"><span data-stu-id="e12db-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e12db-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e12db-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e12db-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e12db-105">Return Value</span></span>  
  
|<span data-ttu-id="e12db-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e12db-106">HRESULT</span></span>|<span data-ttu-id="e12db-107">Описание</span><span class="sxs-lookup"><span data-stu-id="e12db-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e12db-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e12db-108">S_OK</span></span>|<span data-ttu-id="e12db-109">Start возвращается успешно.</span><span class="sxs-lookup"><span data-stu-id="e12db-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="e12db-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e12db-110">E_FAIL</span></span>|<span data-ttu-id="e12db-111">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="e12db-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e12db-112">Когда метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="e12db-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="e12db-113">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e12db-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e12db-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="e12db-114">Remarks</span></span>  
 <span data-ttu-id="e12db-115">`Start` всегда возвращает HRESULT со значением S_OK, за исключением в случаях, где фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="e12db-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e12db-116">Требования</span><span class="sxs-lookup"><span data-stu-id="e12db-116">Requirements</span></span>  
 <span data-ttu-id="e12db-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e12db-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e12db-118">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e12db-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e12db-119">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e12db-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e12db-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e12db-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e12db-121">См. также</span><span class="sxs-lookup"><span data-stu-id="e12db-121">See also</span></span>

- [<span data-ttu-id="e12db-122">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="e12db-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="e12db-123">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="e12db-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="e12db-124">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="e12db-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="e12db-125">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="e12db-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
