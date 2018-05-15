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
ms.openlocfilehash: 56a49b3d08b58da109924267e6c23c188efefe29
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="bd1f8-102">Метод ICLRRuntimeHost::ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="bd1f8-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="bd1f8-103">Используется в сценариях развертывания служб на основе манифестов ClickOnce укажите приложение, которое необходимо активировать в новом домене.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="bd1f8-104">Дополнительные сведения об этих сценариях см. в разделе [развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="bd1f8-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd1f8-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bd1f8-105">Syntax</span></span>  
  
```  
HRESULT ExecuteApplication(  
    [in] LPCWSTR   pwzAppFullName,  
    [in] DWORD     dwManifestPaths,  
    [in] LPCWSTR   *ppwzManifestPaths,  
    [in] DWORD     dwActivationData,  
    [in] LPCWSTR   *ppwzActivationData,  
    [out] int      *pReturnValue  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bd1f8-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="bd1f8-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="bd1f8-107">[in] Полное имя приложения, как это определено для <xref:System.ApplicationIdentity>.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="bd1f8-108">[in] Число строк, содержащихся в `ppwzManifestPaths` массива.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="bd1f8-109">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-109">[in] Optional.</span></span> <span data-ttu-id="bd1f8-110">Строковый массив, содержащий путями манифеста приложения.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="bd1f8-111">[in] Число строк, содержащихся в `ppwzActivationData` массива.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="bd1f8-112">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-112">[in] Optional.</span></span> <span data-ttu-id="bd1f8-113">Строковый массив, содержащий данные активации приложения, такие как часть строки запроса URL-адрес приложения, развернутые через Интернет.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="bd1f8-114">[out] Значение, возвращаемое точкой входа приложения.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bd1f8-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bd1f8-115">Return Value</span></span>  
  
|<span data-ttu-id="bd1f8-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bd1f8-116">HRESULT</span></span>|<span data-ttu-id="bd1f8-117">Описание</span><span class="sxs-lookup"><span data-stu-id="bd1f8-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bd1f8-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="bd1f8-118">S_OK</span></span>|<span data-ttu-id="bd1f8-119">`ExecuteApplication` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="bd1f8-120">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bd1f8-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bd1f8-121">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="bd1f8-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="bd1f8-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="bd1f8-123">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-123">The call timed out.</span></span>|  
|<span data-ttu-id="bd1f8-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="bd1f8-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="bd1f8-125">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="bd1f8-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="bd1f8-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="bd1f8-127">Событие было отменено заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="bd1f8-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bd1f8-128">E_FAIL</span></span>|<span data-ttu-id="bd1f8-129">Неизвестная Неустранимая ошибка.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="bd1f8-130">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="bd1f8-131">Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bd1f8-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="bd1f8-132">Remarks</span></span>  
 <span data-ttu-id="bd1f8-133">`ExecuteApplication` используется для активации приложений ClickOnce в новом домене приложения.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="bd1f8-134">`pReturnValue` Выходного параметра присваивается значение, возвращенное приложением.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="bd1f8-135">Если указать значение null для `pReturnValue`, `ExecuteApplication` не завершается ошибкой, но не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bd1f8-136">Не вызывайте [метод Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод перед вызовом метода `ExecuteApplication` метода активации приложения на основе манифеста.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="bd1f8-137">Если `Start` сначала вызывается метод `ExecuteApplication` вызов метода завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="bd1f8-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd1f8-138">Требования</span><span class="sxs-lookup"><span data-stu-id="bd1f8-138">Requirements</span></span>  
 <span data-ttu-id="bd1f8-139">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bd1f8-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd1f8-140">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bd1f8-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bd1f8-141">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bd1f8-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bd1f8-142">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd1f8-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd1f8-143">См. также</span><span class="sxs-lookup"><span data-stu-id="bd1f8-143">See Also</span></span>  
 <xref:System.ActivationContext>  
 <xref:System.AppDomainManager>  
 <xref:System.ApplicationIdentity>  
 [<span data-ttu-id="bd1f8-144">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="bd1f8-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)  
 [<span data-ttu-id="bd1f8-145">Метод SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="bd1f8-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)  
 [<span data-ttu-id="bd1f8-146">Пошаговое руководство. Загрузка сборок по требованию с помощью API развертывания ClickOnce с использованием конструктора</span><span class="sxs-lookup"><span data-stu-id="bd1f8-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
