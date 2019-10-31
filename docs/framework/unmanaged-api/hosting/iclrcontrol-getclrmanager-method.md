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
ms.openlocfilehash: fa9608423456caeb6020e883a14f2c41583ac4d9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126616"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="5c6b1-102">Метод ICLRControl::GetCLRManager</span><span class="sxs-lookup"><span data-stu-id="5c6b1-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="5c6b1-103">Возвращает указатель интерфейса на экземпляр любого из типов диспетчера, который узел может использовать для настройки среды CLR.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c6b1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5c6b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c6b1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5c6b1-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="5c6b1-106">окне `IID` возвращаемого типа диспетчера.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="5c6b1-107">Поддерживаются следующие значения `IID`.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="5c6b1-108">IID_ICLRDebugManager: указывает, что `ppObject` будет иметь тип [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b1-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="5c6b1-109">IID_ICLRErrorReportingManager: указывает, что `ppObject` будет иметь тип [iclrerrorreportingmanagergetbucketparametersforcurrentexception](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b1-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="5c6b1-110">IID_ICLRGCManager: указывает, что `ppObject` будет иметь тип [иклргкманажер](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b1-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="5c6b1-111">IID_ICLRHostProtectionManager: указывает, что `ppObject` будет иметь тип [иклрхостпротектионманажер](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b1-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="5c6b1-112">IID_ICLROnEventManager: указывает, что `ppObject` будет иметь тип [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b1-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="5c6b1-113">IID_ICLRPolicyManager: указывает, что `ppObject` будет иметь тип [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b1-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="5c6b1-114">IID_ICLRTaskManager: указывает, что `ppObject` будет иметь тип [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b1-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="5c6b1-115">заполняет Указатель интерфейса на запрошенный диспетчер или значение null, если был запрошен недопустимый тип диспетчера.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5c6b1-116">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="5c6b1-116">Return Value</span></span>  
  
|<span data-ttu-id="5c6b1-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5c6b1-117">HRESULT</span></span>|<span data-ttu-id="5c6b1-118">Описание</span><span class="sxs-lookup"><span data-stu-id="5c6b1-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5c6b1-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="5c6b1-119">S_OK</span></span>|<span data-ttu-id="5c6b1-120">Метод успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="5c6b1-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5c6b1-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5c6b1-122">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5c6b1-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5c6b1-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5c6b1-124">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-124">The call timed out.</span></span>|  
|<span data-ttu-id="5c6b1-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5c6b1-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5c6b1-126">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5c6b1-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5c6b1-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5c6b1-128">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5c6b1-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5c6b1-129">E_FAIL</span></span>|<span data-ttu-id="5c6b1-130">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5c6b1-131">После того как метод вернет значение E_FAIL, среда CLR больше не будет использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5c6b1-132">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="5c6b1-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="5c6b1-133">E_NOINTERFACE</span></span>|<span data-ttu-id="5c6b1-134">Тип интерфейса не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="5c6b1-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5c6b1-135">Требования</span><span class="sxs-lookup"><span data-stu-id="5c6b1-135">Requirements</span></span>  
 <span data-ttu-id="5c6b1-136">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5c6b1-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c6b1-137">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5c6b1-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5c6b1-138">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5c6b1-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5c6b1-139">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c6b1-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c6b1-140">См. также</span><span class="sxs-lookup"><span data-stu-id="5c6b1-140">See also</span></span>

- [<span data-ttu-id="5c6b1-141">Интерфейс ICLRControl</span><span class="sxs-lookup"><span data-stu-id="5c6b1-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5c6b1-142">Интерфейс IHostControl</span><span class="sxs-lookup"><span data-stu-id="5c6b1-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
