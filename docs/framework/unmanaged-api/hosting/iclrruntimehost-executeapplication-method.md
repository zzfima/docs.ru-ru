---
title: Метод ICLRRuntimeHost::ExecuteApplication
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.ExecuteApplication
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::ExecuteApplication
helpviewer_keywords:
- ICLRRuntimeHost::ExecuteApplication method [.NET Framework hosting]
- ExecuteApplication method [.NET Framework hosting]
ms.assetid: 5f28cc4e-7176-4e00-aa1f-58ae6ee52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38938de335e5f0d7cb8051554c400f16df012362
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965361"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="48e48-102">Метод ICLRRuntimeHost::ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="48e48-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="48e48-103">Используется в сценариях развертывания ClickOnce на основе манифеста для указания приложения, которое должно быть активировано в новом домене.</span><span class="sxs-lookup"><span data-stu-id="48e48-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="48e48-104">Дополнительные сведения об этих сценариях см. в разделе [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="48e48-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48e48-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="48e48-105">Syntax</span></span>  
  
```cpp  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48e48-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="48e48-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="48e48-107">окне Полное имя приложения, определенное для <xref:System.ApplicationIdentity>.</span><span class="sxs-lookup"><span data-stu-id="48e48-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="48e48-108">окне Число строк, `ppwzManifestPaths` содержащихся в массиве.</span><span class="sxs-lookup"><span data-stu-id="48e48-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="48e48-109">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="48e48-109">[in] Optional.</span></span> <span data-ttu-id="48e48-110">Массив строк, содержащий пути манифеста для приложения.</span><span class="sxs-lookup"><span data-stu-id="48e48-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="48e48-111">окне Число строк, `ppwzActivationData` содержащихся в массиве.</span><span class="sxs-lookup"><span data-stu-id="48e48-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="48e48-112">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="48e48-112">[in] Optional.</span></span> <span data-ttu-id="48e48-113">Массив строк, содержащий данные активации приложения, такие как часть строки запроса URL-адреса для приложений, развернутых через Интернет.</span><span class="sxs-lookup"><span data-stu-id="48e48-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="48e48-114">заполняет Значение, возвращаемое из точки входа приложения.</span><span class="sxs-lookup"><span data-stu-id="48e48-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48e48-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="48e48-115">Return Value</span></span>  
  
|<span data-ttu-id="48e48-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48e48-116">HRESULT</span></span>|<span data-ttu-id="48e48-117">Описание</span><span class="sxs-lookup"><span data-stu-id="48e48-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48e48-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="48e48-118">S_OK</span></span>|<span data-ttu-id="48e48-119">`ExecuteApplication`успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="48e48-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="48e48-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="48e48-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="48e48-121">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="48e48-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="48e48-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="48e48-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="48e48-123">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="48e48-123">The call timed out.</span></span>|  
|<span data-ttu-id="48e48-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="48e48-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="48e48-125">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="48e48-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="48e48-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="48e48-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="48e48-127">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="48e48-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="48e48-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="48e48-128">E_FAIL</span></span>|<span data-ttu-id="48e48-129">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="48e48-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="48e48-130">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="48e48-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="48e48-131">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="48e48-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48e48-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="48e48-132">Remarks</span></span>  
 <span data-ttu-id="48e48-133">`ExecuteApplication`используется для активации приложений ClickOnce в только что созданном домене приложения.</span><span class="sxs-lookup"><span data-stu-id="48e48-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="48e48-134">Параметру `pReturnValue` Output задается значение, возвращаемое приложением.</span><span class="sxs-lookup"><span data-stu-id="48e48-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="48e48-135">Если для `pReturnValue` `ExecuteApplication` задано значение null, то не завершается ошибкой, но не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="48e48-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="48e48-136">Не вызывайте метод [метода Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) перед вызовом `ExecuteApplication` метода для активации приложения на основе манифеста.</span><span class="sxs-lookup"><span data-stu-id="48e48-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="48e48-137">Если метод вызывается первым, вызов `ExecuteApplication` метода завершится ошибкой. `Start`</span><span class="sxs-lookup"><span data-stu-id="48e48-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="48e48-138">Требования</span><span class="sxs-lookup"><span data-stu-id="48e48-138">Requirements</span></span>  
 <span data-ttu-id="48e48-139">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48e48-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48e48-140">**Заголовок.** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="48e48-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="48e48-141">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="48e48-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48e48-142">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48e48-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48e48-143">См. также</span><span class="sxs-lookup"><span data-stu-id="48e48-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="48e48-144">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="48e48-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="48e48-145">Метод SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="48e48-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="48e48-146">Пошаговое руководство: Загрузка сборок по требованию с помощью API развертывания ClickOnce с использованием конструктора</span><span class="sxs-lookup"><span data-stu-id="48e48-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
