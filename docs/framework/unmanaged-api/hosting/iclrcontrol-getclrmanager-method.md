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
ms.openlocfilehash: f375afde247c3a9b95e1220df747d3f2b95e2840
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436433"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="e0fd7-102">Метод ICLRControl::GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="e0fd7-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="e0fd7-103">Получает указатель интерфейса на экземпляр любого типа, который узел может использовать для настройки общеязыковой среды выполнения (CLR).</span><span class="sxs-lookup"><span data-stu-id="e0fd7-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0fd7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0fd7-104">Syntax</span></span>  
  
```  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0fd7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0fd7-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="e0fd7-106">[in] `IID` Типа диспетчера для возврата.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="e0fd7-107">Следующие `IID` значения поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-107">The following `IID` values are supported.</span></span>  
  
-   <span data-ttu-id="e0fd7-108">IID_ICLRDebugManager: Указывает, что `ppObject` будет иметь тип [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd7-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="e0fd7-109">IID_ICLRErrorReportingManager: Указывает, что `ppObject` будет иметь тип [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd7-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="e0fd7-110">IID_ICLRGCManager: Указывает, что `ppObject` будет иметь тип [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd7-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="e0fd7-111">IID_ICLRHostProtectionManager: Указывает, что `ppObject` будет иметь тип [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd7-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="e0fd7-112">IID_ICLROnEventManager: Указывает, что `ppObject` будет иметь тип [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd7-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
-   <span data-ttu-id="e0fd7-113">IID_ICLRPolicyManager: Указывает, что `ppObject` будет иметь тип [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd7-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
-   <span data-ttu-id="e0fd7-114">IID_ICLRTaskManager: speciries, `ppObject` будет иметь тип [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd7-114">IID_ICLRTaskManager: speciries that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="e0fd7-115">[out] Указатель интерфейса, запрошенный диспетчера, или значение null, если был запрошен тип диспетчера с недопустимым.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0fd7-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e0fd7-116">Return Value</span></span>  
  
|<span data-ttu-id="e0fd7-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e0fd7-117">HRESULT</span></span>|<span data-ttu-id="e0fd7-118">Описание</span><span class="sxs-lookup"><span data-stu-id="e0fd7-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e0fd7-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="e0fd7-119">S_OK</span></span>|<span data-ttu-id="e0fd7-120">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="e0fd7-121">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e0fd7-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e0fd7-122">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="e0fd7-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e0fd7-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="e0fd7-124">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-124">The call timed out.</span></span>|  
|<span data-ttu-id="e0fd7-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="e0fd7-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="e0fd7-126">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="e0fd7-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="e0fd7-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="e0fd7-128">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="e0fd7-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e0fd7-129">E_FAIL</span></span>|<span data-ttu-id="e0fd7-130">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="e0fd7-131">После метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="e0fd7-132">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e0fd7-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="e0fd7-133">E_NOINTERFACE</span></span>|<span data-ttu-id="e0fd7-134">Тип интерфейса не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="e0fd7-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e0fd7-135">Требования</span><span class="sxs-lookup"><span data-stu-id="e0fd7-135">Requirements</span></span>  
 <span data-ttu-id="e0fd7-136">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0fd7-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0fd7-137">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0fd7-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0fd7-138">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0fd7-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0fd7-139">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0fd7-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0fd7-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e0fd7-140">See Also</span></span>  
 [<span data-ttu-id="e0fd7-141">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="e0fd7-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [<span data-ttu-id="e0fd7-142">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="e0fd7-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
