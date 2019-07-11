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
ms.openlocfilehash: e7750d50b772ff17cf9dcd05de2e2f34556714e4
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770475"
---
# <a name="iclrtaskrudeabort-method"></a><span data-ttu-id="b2cd9-102">Метод ICLRTask::RudeAbort</span><span class="sxs-lookup"><span data-stu-id="b2cd9-102">ICLRTask::RudeAbort Method</span></span>
<span data-ttu-id="b2cd9-103">Указывает, что среда CLR (CLR), чтобы прервать задачу, представленную текущим [интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра немедленно и без дополнительных условий.</span><span class="sxs-lookup"><span data-stu-id="b2cd9-103">Instructs the common language runtime (CLR) to abort the task represented by the current [ICLRTask Interface](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instance immediately and unconditionally.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2cd9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2cd9-104">Syntax</span></span>  
  
```cpp  
HRESULT RudeAbort ();   
```  
  
## <a name="return-value"></a><span data-ttu-id="b2cd9-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b2cd9-105">Return Value</span></span>  
  
|<span data-ttu-id="b2cd9-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2cd9-106">HRESULT</span></span>|<span data-ttu-id="b2cd9-107">Описание</span><span class="sxs-lookup"><span data-stu-id="b2cd9-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2cd9-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2cd9-108">S_OK</span></span>|<span data-ttu-id="b2cd9-109">`RudeAbort` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="b2cd9-109">`RudeAbort` returned successfully.</span></span>|  
|<span data-ttu-id="b2cd9-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b2cd9-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b2cd9-111">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b2cd9-111">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b2cd9-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b2cd9-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b2cd9-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="b2cd9-113">The call timed out.</span></span>|  
|<span data-ttu-id="b2cd9-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b2cd9-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b2cd9-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="b2cd9-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b2cd9-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b2cd9-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b2cd9-117">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="b2cd9-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b2cd9-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2cd9-118">E_FAIL</span></span>|<span data-ttu-id="b2cd9-119">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="b2cd9-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2cd9-120">Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b2cd9-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b2cd9-121">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b2cd9-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2cd9-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="b2cd9-122">Remarks</span></span>  
 <span data-ttu-id="b2cd9-123">Узел вызывает `RudeAbort` немедленному прерыванию задачу.</span><span class="sxs-lookup"><span data-stu-id="b2cd9-123">A host calls `RudeAbort` to abort a task immediately.</span></span> <span data-ttu-id="b2cd9-124">Для выполнения методов завершения и процедур обработки исключений не гарантируется.</span><span class="sxs-lookup"><span data-stu-id="b2cd9-124">Finalizers and exception handling routines are not guaranteed to be executed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2cd9-125">Требования</span><span class="sxs-lookup"><span data-stu-id="b2cd9-125">Requirements</span></span>  
 <span data-ttu-id="b2cd9-126">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2cd9-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2cd9-127">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b2cd9-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2cd9-128">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b2cd9-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2cd9-129">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2cd9-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2cd9-130">См. также</span><span class="sxs-lookup"><span data-stu-id="b2cd9-130">See also</span></span>

- [<span data-ttu-id="b2cd9-131">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="b2cd9-131">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [<span data-ttu-id="b2cd9-132">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="b2cd9-132">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [<span data-ttu-id="b2cd9-133">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="b2cd9-133">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [<span data-ttu-id="b2cd9-134">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="b2cd9-134">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
