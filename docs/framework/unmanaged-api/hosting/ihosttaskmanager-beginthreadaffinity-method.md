---
title: Метод IHostTaskManager::BeginThreadAffinity
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a94797e6279a1f1d419b977c22d73ca41bbafc9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443380"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a><span data-ttu-id="ce066-102">Метод IHostTaskManager::BeginThreadAffinity</span><span class="sxs-lookup"><span data-stu-id="ce066-102">IHostTaskManager::BeginThreadAffinity Method</span></span>
<span data-ttu-id="ce066-103">Уведомляет хост, что управляемый код к периоду, в котором текущую задачу нельзя перемещать в другой поток операционной системы.</span><span class="sxs-lookup"><span data-stu-id="ce066-103">Notifies the host that managed code is entering a period in which the current task must not be moved to another operating system thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce066-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ce066-104">Syntax</span></span>  
  
```  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="ce066-105">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="ce066-105">Return Value</span></span>  
  
|<span data-ttu-id="ce066-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ce066-106">HRESULT</span></span>|<span data-ttu-id="ce066-107">Описание</span><span class="sxs-lookup"><span data-stu-id="ce066-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ce066-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="ce066-108">S_OK</span></span>|<span data-ttu-id="ce066-109">`BeginThreadAffinity` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="ce066-109">`BeginThreadAffinity` returned successfully.</span></span>|  
|<span data-ttu-id="ce066-110">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ce066-110">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ce066-111">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="ce066-111">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ce066-112">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ce066-112">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ce066-113">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="ce066-113">The call timed out.</span></span>|  
|<span data-ttu-id="ce066-114">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ce066-114">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ce066-115">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="ce066-115">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ce066-116">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ce066-116">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ce066-117">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="ce066-117">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ce066-118">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ce066-118">E_FAIL</span></span>|<span data-ttu-id="ce066-119">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="ce066-119">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ce066-120">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="ce066-120">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ce066-121">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ce066-121">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ce066-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="ce066-122">Remarks</span></span>  
 <span data-ttu-id="ce066-123">Как правило, среда CLR вызывает `IHostTaskManager::BeginThreadAffinity` в контексте вызова <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="ce066-123">The CLR typically calls `IHostTaskManager::BeginThreadAffinity` in the context of a call to <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ce066-124">Текущая задача не должно быть Переназначено, пока соответствующий вызов [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span><span class="sxs-lookup"><span data-stu-id="ce066-124">The current task must not be rescheduled until a corresponding call is made to [IHostTaskManager::EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md).</span></span> <span data-ttu-id="ce066-125">Задачи могут отключаться, но после переключения обратно в должны быть назначены для одного потока операционной системы, из которого они были выключены. Вложенные вызовы `BeginThreadAffinity` не действуют, поскольку вызов ссылается на текущую задачу.</span><span class="sxs-lookup"><span data-stu-id="ce066-125">Tasks can be switched out, but when they are switched back in, they must be assigned to the same operating system thread from which they were switched out. Nested calls to `BeginThreadAffinity` have no effect, because the call refers to the current task.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce066-126">Требования</span><span class="sxs-lookup"><span data-stu-id="ce066-126">Requirements</span></span>  
 <span data-ttu-id="ce066-127">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce066-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce066-128">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ce066-128">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ce066-129">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ce066-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ce066-130">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce066-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce066-131">См. также</span><span class="sxs-lookup"><span data-stu-id="ce066-131">See Also</span></span>  
 [<span data-ttu-id="ce066-132">Интерфейс ICLRTask</span><span class="sxs-lookup"><span data-stu-id="ce066-132">ICLRTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [<span data-ttu-id="ce066-133">Интерфейс ICLRTaskManager</span><span class="sxs-lookup"><span data-stu-id="ce066-133">ICLRTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [<span data-ttu-id="ce066-134">Интерфейс IHostTask</span><span class="sxs-lookup"><span data-stu-id="ce066-134">IHostTask Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [<span data-ttu-id="ce066-135">Интерфейс IHostTaskManager</span><span class="sxs-lookup"><span data-stu-id="ce066-135">IHostTaskManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
