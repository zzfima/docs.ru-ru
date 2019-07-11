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
ms.openlocfilehash: 2bc996973a98f3b8596b449e1524d5c93b4456e3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749811"
---
# <a name="ihosttaskstart-method"></a><span data-ttu-id="ac69c-102">Метод IHostTask::Start</span><span class="sxs-lookup"><span data-stu-id="ac69c-102">IHostTask::Start Method</span></span>
<span data-ttu-id="ac69c-103">Запросы, что узел перемещения задач, представленный текущим [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляр из приостановленного состояния в активное, в котором можно выполнять код.</span><span class="sxs-lookup"><span data-stu-id="ac69c-103">Requests that the host move the task represented by the current [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instance from a suspended to a live state, in which code can be executed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac69c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ac69c-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ac69c-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ac69c-105">Return Value</span></span>  
  
|<span data-ttu-id="ac69c-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ac69c-106">HRESULT</span></span>|<span data-ttu-id="ac69c-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ac69c-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ac69c-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ac69c-108">S_OK</span></span>|<span data-ttu-id="ac69c-109">Start возвращается успешно.</span><span class="sxs-lookup"><span data-stu-id="ac69c-109">Start returned successfully.</span></span>|  
|<span data-ttu-id="ac69c-110">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ac69c-110">E_FAIL</span></span>|<span data-ttu-id="ac69c-111">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="ac69c-111">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ac69c-112">Когда метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="ac69c-112">When a method returns E_FAIL, the common language runtime (CLR) is no longer usable within the process.</span></span> <span data-ttu-id="ac69c-113">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ac69c-113">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ac69c-114">Примечания</span><span class="sxs-lookup"><span data-stu-id="ac69c-114">Remarks</span></span>  
 <span data-ttu-id="ac69c-115">`Start` всегда возвращает HRESULT со значением S_OK, за исключением в случаях, где фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="ac69c-115">`Start` always returns an HRESULT value of S_OK, except in cases where a catastrophic failure has occurred.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac69c-116">Требования</span><span class="sxs-lookup"><span data-stu-id="ac69c-116">Requirements</span></span>  
 <span data-ttu-id="ac69c-117">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac69c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac69c-118">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ac69c-118">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ac69c-119">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac69c-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ac69c-120">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac69c-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac69c-121">См. также</span><span class="sxs-lookup"><span data-stu-id="ac69c-121">See also</span></span>

- [<span data-ttu-id="ac69c-122">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="ac69c-122">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="ac69c-123">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="ac69c-123">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="ac69c-124">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="ac69c-124">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="ac69c-125">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="ac69c-125">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
