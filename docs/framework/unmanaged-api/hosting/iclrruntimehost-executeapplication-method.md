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
ms.openlocfilehash: ca8db6fd1296420011dcbfbbb0e5682f8a484dc9
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67768813"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="76ca3-102">Метод ICLRRuntimeHost::ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="76ca3-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="76ca3-103">Используется в сценариях развертывания служб на основе манифестов ClickOnce для указания приложения, которое будет активировать в новом домене.</span><span class="sxs-lookup"><span data-stu-id="76ca3-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="76ca3-104">Дополнительные сведения об этих сценариях см. в разделе [развертывание и безопасность технологии ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="76ca3-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ca3-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="76ca3-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="76ca3-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="76ca3-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="76ca3-107">[in] Полное имя приложения, как определено для <xref:System.ApplicationIdentity>.</span><span class="sxs-lookup"><span data-stu-id="76ca3-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="76ca3-108">[in] Количество строк, содержащихся в `ppwzManifestPaths` массива.</span><span class="sxs-lookup"><span data-stu-id="76ca3-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="76ca3-109">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="76ca3-109">[in] Optional.</span></span> <span data-ttu-id="76ca3-110">Массив строк, содержащий путей манифестов для приложения.</span><span class="sxs-lookup"><span data-stu-id="76ca3-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="76ca3-111">[in] Количество строк, содержащихся в `ppwzActivationData` массива.</span><span class="sxs-lookup"><span data-stu-id="76ca3-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="76ca3-112">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="76ca3-112">[in] Optional.</span></span> <span data-ttu-id="76ca3-113">Массив строк, содержащий данные активации приложения, такие как часть строки запроса URL-адрес приложения, развернутые через Интернет.</span><span class="sxs-lookup"><span data-stu-id="76ca3-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="76ca3-114">[out] Значение, возвращенное из точки входа приложения.</span><span class="sxs-lookup"><span data-stu-id="76ca3-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76ca3-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="76ca3-115">Return Value</span></span>  
  
|<span data-ttu-id="76ca3-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76ca3-116">HRESULT</span></span>|<span data-ttu-id="76ca3-117">Описание</span><span class="sxs-lookup"><span data-stu-id="76ca3-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76ca3-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="76ca3-118">S_OK</span></span>|<span data-ttu-id="76ca3-119">`ExecuteApplication` успешно возвращен.</span><span class="sxs-lookup"><span data-stu-id="76ca3-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="76ca3-120">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="76ca3-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="76ca3-121">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="76ca3-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="76ca3-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="76ca3-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="76ca3-123">Истекло время ожидания вызова.</span><span class="sxs-lookup"><span data-stu-id="76ca3-123">The call timed out.</span></span>|  
|<span data-ttu-id="76ca3-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="76ca3-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="76ca3-125">Вызывающий объект не является владельцем блокировки.</span><span class="sxs-lookup"><span data-stu-id="76ca3-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="76ca3-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="76ca3-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="76ca3-127">Событие было отменено с сохранением заблокированный поток или ожидал волокон.</span><span class="sxs-lookup"><span data-stu-id="76ca3-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="76ca3-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="76ca3-128">E_FAIL</span></span>|<span data-ttu-id="76ca3-129">Неизвестный Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="76ca3-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="76ca3-130">Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="76ca3-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="76ca3-131">Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="76ca3-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76ca3-132">Примечания</span><span class="sxs-lookup"><span data-stu-id="76ca3-132">Remarks</span></span>  
 <span data-ttu-id="76ca3-133">`ExecuteApplication` используется для активации ClickOnce-приложений в домене только что созданное приложение.</span><span class="sxs-lookup"><span data-stu-id="76ca3-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="76ca3-134">`pReturnValue` Выходного параметра присваивается значение, возвращаемое для приложения.</span><span class="sxs-lookup"><span data-stu-id="76ca3-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="76ca3-135">Если указать значение null для `pReturnValue`, `ExecuteApplication` не произойдет сбой, но он не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="76ca3-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="76ca3-136">Не вызывайте [метод Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) метод перед вызовом `ExecuteApplication` метод для активации приложения на основе манифеста.</span><span class="sxs-lookup"><span data-stu-id="76ca3-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="76ca3-137">Если `Start` во-первых, вызывается метод `ExecuteApplication` вызов метода завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="76ca3-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ca3-138">Требования</span><span class="sxs-lookup"><span data-stu-id="76ca3-138">Requirements</span></span>  
 <span data-ttu-id="76ca3-139">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76ca3-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ca3-140">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="76ca3-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76ca3-141">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76ca3-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76ca3-142">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76ca3-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ca3-143">См. также</span><span class="sxs-lookup"><span data-stu-id="76ca3-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="76ca3-144">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="76ca3-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="76ca3-145">Метод SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="76ca3-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="76ca3-146">Пошаговое руководство: Загрузка сборок по требованию с помощью API развертывания ClickOnce с использованием конструктора</span><span class="sxs-lookup"><span data-stu-id="76ca3-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
