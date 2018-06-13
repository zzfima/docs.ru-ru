---
title: Метод ICLRGCManager::Collect
ms.date: 03/30/2017
api_name:
- ICLRGCManager.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::Collect
helpviewer_keywords:
- ICLRGCManager::Collect method [.NET Framework hosting]
- Collect method, ICLRGCManager interface [.NET Framework hosting]
ms.assetid: 0c6cbbea-c27c-4695-bda3-17c1910d8ddb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6b9c3899c4319c623bc991d0775945f0a4dc09e6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434759"
---
# <a name="iclrgcmanagercollect-method"></a><span data-ttu-id="cca46-102">Метод ICLRGCManager::Collect</span><span class="sxs-lookup"><span data-stu-id="cca46-102">ICLRGCManager::Collect Method</span></span>
<span data-ttu-id="cca46-103">Принудительная сборка мусора для заданного поколения.</span><span class="sxs-lookup"><span data-stu-id="cca46-103">Forces a garbage collection for the specified generation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cca46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="cca46-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="cca46-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="cca46-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="cca46-106">[in] Поколение, для сбора.</span><span class="sxs-lookup"><span data-stu-id="cca46-106">[in] The generation to collect.</span></span> <span data-ttu-id="cca46-107">Значение -1 принудительно мусора для всех поколений.</span><span class="sxs-lookup"><span data-stu-id="cca46-107">A value of -1 forces a collection of all generations.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="cca46-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="cca46-108">Return Value</span></span>  
  
|<span data-ttu-id="cca46-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="cca46-109">HRESULT</span></span>|<span data-ttu-id="cca46-110">Описание</span><span class="sxs-lookup"><span data-stu-id="cca46-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="cca46-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="cca46-111">S_OK</span></span>|<span data-ttu-id="cca46-112">`Collect` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="cca46-112">`Collect` returned successfully.</span></span>|  
|<span data-ttu-id="cca46-113">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="cca46-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="cca46-114">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="cca46-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="cca46-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="cca46-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="cca46-116">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="cca46-116">The call timed out.</span></span>|  
|<span data-ttu-id="cca46-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="cca46-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="cca46-118">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="cca46-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="cca46-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="cca46-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="cca46-120">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="cca46-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="cca46-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="cca46-121">E_FAIL</span></span>|<span data-ttu-id="cca46-122">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="cca46-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="cca46-123">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="cca46-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="cca46-124">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="cca46-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cca46-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="cca46-125">Remarks</span></span>  
 <span data-ttu-id="cca46-126">`Collect` Метод вынуждает сборщик мусора среды CLR для выполнения сбора, независимо от его текущего состояния.</span><span class="sxs-lookup"><span data-stu-id="cca46-126">The `Collect` method forces the CLR's garbage collector to perform a collection regardless of its current state.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cca46-127">Требования</span><span class="sxs-lookup"><span data-stu-id="cca46-127">Requirements</span></span>  
 <span data-ttu-id="cca46-128">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cca46-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cca46-129">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="cca46-129">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cca46-130">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cca46-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cca46-131">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cca46-131">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cca46-132">См. также</span><span class="sxs-lookup"><span data-stu-id="cca46-132">See Also</span></span>  
 [<span data-ttu-id="cca46-133">Автоматическое управление памятью</span><span class="sxs-lookup"><span data-stu-id="cca46-133">Automatic Memory Management</span></span>](../../../../docs/standard/automatic-memory-management.md)  
 [<span data-ttu-id="cca46-134">Сборка мусора</span><span class="sxs-lookup"><span data-stu-id="cca46-134">Garbage Collection</span></span>](../../../../docs/standard/garbage-collection/index.md)  
 [<span data-ttu-id="cca46-135">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="cca46-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="cca46-136">Интерфейс ICLRGCManager</span><span class="sxs-lookup"><span data-stu-id="cca46-136">ICLRGCManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)  
 [<span data-ttu-id="cca46-137">Интерфейсы размещения CLR</span><span class="sxs-lookup"><span data-stu-id="cca46-137">CLR Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [<span data-ttu-id="cca46-138">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="cca46-138">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="cca46-139">Размещение</span><span class="sxs-lookup"><span data-stu-id="cca46-139">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
