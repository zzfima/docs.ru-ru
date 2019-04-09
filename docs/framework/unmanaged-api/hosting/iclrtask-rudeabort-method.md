---
title: Метод ICLRTask::RudeAbort
ms.date: 03/30/2017
api_name:
- ICLRTask.RudeAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::RudeAbort
helpviewer_keywords:
- RudeAbort method, ICLRTask interface [.NET Framework hosting]
- ICLRTask::RudeAbort method [.NET Framework hosting]
ms.assetid: b5785468-fcd7-4cc3-8a5d-8796337b53fc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2db47f90e73922858013885e99e953ddcacbd450
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59147619"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="1f1e1-102">Метод ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="1f1e1-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="1f1e1-103">Указывает, что среда CLR (CLR), чтобы прервать задачу, представленную текущим [интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра немедленно и без дополнительных условий.</span><span class="sxs-lookup"><span data-stu-id="1f1e1-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1f1e1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="1f1e1-104">Syntax</span></span>  
  
```  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="1f1e1-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="1f1e1-105">Return Value</span></span>  
  
|<span data-ttu-id="1f1e1-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1f1e1-106">HRESULT</span></span>|<span data-ttu-id="1f1e1-107">Описание</span><span class="sxs-lookup"><span data-stu-id="1f1e1-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1f1e1-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="1f1e1-108">S_OK</span></span>|`RudeAbort` <span data-ttu-id="1f1e1-109">успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="1f1e1-109">returned successfully.</span></span>|  
|<span data-ttu-id="1f1e1-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="1f1e1-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="1f1e1-111">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="1f1e1-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="1f1e1-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="1f1e1-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="1f1e1-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="1f1e1-113">The call timed out.</span></span>|  
|<span data-ttu-id="1f1e1-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="1f1e1-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="1f1e1-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="1f1e1-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="1f1e1-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="1f1e1-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="1f1e1-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="1f1e1-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="1f1e1-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="1f1e1-118">E_FAIL</span></span>|<span data-ttu-id="1f1e1-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="1f1e1-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="1f1e1-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="1f1e1-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="1f1e1-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="1f1e1-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1f1e1-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="1f1e1-122">Remarks</span></span>  
 <span data-ttu-id="1f1e1-123">Узел вызывает `RudeAbort` немедленному прерыванию задачу.</span><span class="sxs-lookup"><span data-stu-id="1f1e1-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="1f1e1-124">Для выполнения методов завершения и процедур обработки исключений не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="1f1e1-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1f1e1-125">Требования</span><span class="sxs-lookup"><span data-stu-id="1f1e1-125">Requirements</span></span>  
 <span data-ttu-id="1f1e1-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1f1e1-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f1e1-127">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="1f1e1-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1f1e1-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1f1e1-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="1f1e1-129">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="1f1e1-129">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1f1e1-130">См. также</span><span class="sxs-lookup"><span data-stu-id="1f1e1-130">See also</span></span>

- [<span data-ttu-id="1f1e1-131">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="1f1e1-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="1f1e1-132">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="1f1e1-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="1f1e1-133">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="1f1e1-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="1f1e1-134">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="1f1e1-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
