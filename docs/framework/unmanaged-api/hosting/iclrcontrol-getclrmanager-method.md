---
title: Метод ICLRControl::GetCLRManager
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d97d75eb5fab396530a6f48314e96c8d47d06439
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/28/2019
ms.locfileid: "64656486"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="a5650-102">Метод ICLRControl::GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="a5650-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="a5650-103">Получает указатель интерфейса на экземпляр любого типа, который узел можно использовать для настройки общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="a5650-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5650-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a5650-104">Syntax</span></span>  
  
```  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a5650-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a5650-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="a5650-106">[in] `IID` Типа диспетчера для возврата.</span><span class="sxs-lookup"><span data-stu-id="a5650-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="a5650-107">Следующие `IID` значения поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="a5650-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="a5650-108">IID_ICLRDebugManager: Указывает, что `ppObject` будет иметь тип [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a5650-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="a5650-109">IID_ICLRErrorReportingManager: Указывает, что `ppObject` будет иметь тип [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a5650-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="a5650-110">IID_ICLRGCManager: Указывает, что `ppObject` будет иметь тип [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a5650-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="a5650-111">IID_ICLRHostProtectionManager: Указывает, что `ppObject` будет иметь тип [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a5650-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="a5650-112">IID_ICLROnEventManager: Указывает, что `ppObject` будет иметь тип [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a5650-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="a5650-113">IID_ICLRPolicyManager: Указывает, что `ppObject` будет иметь тип [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a5650-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="a5650-114">IID_ICLRTaskManager: Указывает, что `ppObject` будет иметь тип [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a5650-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="a5650-115">[out] Указатель интерфейса на запрошенный manager, или значение null, если был запрошен тип диспетчера с недопустимым.</span><span class="sxs-lookup"><span data-stu-id="a5650-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a5650-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="a5650-116">Return Value</span></span>  
  
|<span data-ttu-id="a5650-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a5650-117">HRESULT</span></span>|<span data-ttu-id="a5650-118">Описание</span><span class="sxs-lookup"><span data-stu-id="a5650-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a5650-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="a5650-119">S_OK</span></span>|<span data-ttu-id="a5650-120">Метод возвратился успешно.</span><span class="sxs-lookup"><span data-stu-id="a5650-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="a5650-121">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a5650-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a5650-122">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="a5650-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a5650-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a5650-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a5650-124">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="a5650-124">The call timed out.</span></span>|  
|<span data-ttu-id="a5650-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a5650-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a5650-126">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="a5650-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a5650-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a5650-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a5650-128">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="a5650-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a5650-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a5650-129">E_FAIL</span></span>|<span data-ttu-id="a5650-130">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="a5650-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a5650-131">После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе.</span><span class="sxs-lookup"><span data-stu-id="a5650-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a5650-132">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a5650-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a5650-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="a5650-133">E_NOINTERFACE</span></span>|<span data-ttu-id="a5650-134">Тип интерфейса не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="a5650-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a5650-135">Требования</span><span class="sxs-lookup"><span data-stu-id="a5650-135">Requirements</span></span>  
 <span data-ttu-id="a5650-136">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a5650-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a5650-137">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a5650-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a5650-138">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a5650-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a5650-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a5650-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5650-140">См. также</span><span class="sxs-lookup"><span data-stu-id="a5650-140">See also</span></span>

- [<span data-ttu-id="a5650-141">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="a5650-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="a5650-142">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="a5650-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
