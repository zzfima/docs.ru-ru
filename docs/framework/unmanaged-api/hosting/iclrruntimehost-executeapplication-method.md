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
ms.openlocfilehash: 4b56ffab8fb6a9ef70b51421f9cdc5535111e527
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120485"
---
# <a name="iclrruntimehostexecuteapplication-method"></a><span data-ttu-id="b2346-102">Метод ICLRRuntimeHost::ExecuteApplication</span><span class="sxs-lookup"><span data-stu-id="b2346-102">ICLRRuntimeHost::ExecuteApplication Method</span></span>
<span data-ttu-id="b2346-103">Используется в сценариях развертывания ClickOnce на основе манифеста для указания приложения, которое должно быть активировано в новом домене.</span><span class="sxs-lookup"><span data-stu-id="b2346-103">Used in manifest-based ClickOnce deployment scenarios to specify the application to be activated in a new domain.</span></span> <span data-ttu-id="b2346-104">Дополнительные сведения об этих сценариях см. в разделе [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span><span class="sxs-lookup"><span data-stu-id="b2346-104">For more information about these scenarios, see [ClickOnce Security and Deployment](/visualstudio/deployment/clickonce-security-and-deployment).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2346-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b2346-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b2346-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b2346-106">Parameters</span></span>  
 `pwzAppFullName`  
 <span data-ttu-id="b2346-107">окне Полное имя приложения, определенное для <xref:System.ApplicationIdentity>.</span><span class="sxs-lookup"><span data-stu-id="b2346-107">[in] The full name of the application, as defined for <xref:System.ApplicationIdentity>.</span></span>  
  
 `dwManifestPaths`  
 <span data-ttu-id="b2346-108">окне Число строк, содержащихся в массиве `ppwzManifestPaths`.</span><span class="sxs-lookup"><span data-stu-id="b2346-108">[in] The number of strings contained in the `ppwzManifestPaths` array.</span></span>  
  
 `ppwzManifestPaths`  
 <span data-ttu-id="b2346-109">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="b2346-109">[in] Optional.</span></span> <span data-ttu-id="b2346-110">Массив строк, содержащий пути манифеста для приложения.</span><span class="sxs-lookup"><span data-stu-id="b2346-110">A string array that contains manifest paths for the application.</span></span>  
  
 `dwActivationData`  
 <span data-ttu-id="b2346-111">окне Число строк, содержащихся в массиве `ppwzActivationData`.</span><span class="sxs-lookup"><span data-stu-id="b2346-111">[in] The number of strings contained in the `ppwzActivationData` array.</span></span>  
  
 `ppwzActivationData`  
 <span data-ttu-id="b2346-112">[в] Необязательно.</span><span class="sxs-lookup"><span data-stu-id="b2346-112">[in] Optional.</span></span> <span data-ttu-id="b2346-113">Массив строк, содержащий данные активации приложения, такие как часть строки запроса URL-адреса для приложений, развернутых через Интернет.</span><span class="sxs-lookup"><span data-stu-id="b2346-113">A string array that contains the application's activation data, such as the query string portion of the URL for applications deployed over the Web.</span></span>  
  
 `pReturnValue`  
 <span data-ttu-id="b2346-114">заполняет Значение, возвращаемое из точки входа приложения.</span><span class="sxs-lookup"><span data-stu-id="b2346-114">[out] The value returned from the entry point of the application.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b2346-115">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b2346-115">Return Value</span></span>  
  
|<span data-ttu-id="b2346-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b2346-116">HRESULT</span></span>|<span data-ttu-id="b2346-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b2346-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b2346-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="b2346-118">S_OK</span></span>|<span data-ttu-id="b2346-119">`ExecuteApplication` успешно возвращено.</span><span class="sxs-lookup"><span data-stu-id="b2346-119">`ExecuteApplication` returned successfully.</span></span>|  
|<span data-ttu-id="b2346-120">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b2346-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b2346-121">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b2346-121">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="b2346-122">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="b2346-122">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="b2346-123">Время ожидания вызова истекло.</span><span class="sxs-lookup"><span data-stu-id="b2346-123">The call timed out.</span></span>|  
|<span data-ttu-id="b2346-124">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="b2346-124">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="b2346-125">Вызывающий объект не владеет блокировкой.</span><span class="sxs-lookup"><span data-stu-id="b2346-125">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="b2346-126">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="b2346-126">HOST_E_ABANDONED</span></span>|<span data-ttu-id="b2346-127">Событие было отменено, пока заблокированный поток или волокно ожидают его.</span><span class="sxs-lookup"><span data-stu-id="b2346-127">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="b2346-128">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b2346-128">E_FAIL</span></span>|<span data-ttu-id="b2346-129">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="b2346-129">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="b2346-130">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b2346-130">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="b2346-131">Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b2346-131">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b2346-132">Заметки</span><span class="sxs-lookup"><span data-stu-id="b2346-132">Remarks</span></span>  
 <span data-ttu-id="b2346-133">`ExecuteApplication` используется для активации приложений ClickOnce в только что созданном домене приложения.</span><span class="sxs-lookup"><span data-stu-id="b2346-133">`ExecuteApplication` is used to activate ClickOnce applications in a newly created application domain.</span></span>  
  
 <span data-ttu-id="b2346-134">Параметру вывода `pReturnValue` присваивается значение, возвращаемое приложением.</span><span class="sxs-lookup"><span data-stu-id="b2346-134">The `pReturnValue` output parameter is set to the value returned by the application.</span></span> <span data-ttu-id="b2346-135">Если для `pReturnValue`указано значение null, `ExecuteApplication` не завершается ошибкой, но не возвращает значение.</span><span class="sxs-lookup"><span data-stu-id="b2346-135">If you supply a value of null for `pReturnValue`, `ExecuteApplication` does not fail, but it does not return a value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="b2346-136">Не вызывайте метод [метода Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) перед вызовом метода `ExecuteApplication` для активации приложения на основе манифеста.</span><span class="sxs-lookup"><span data-stu-id="b2346-136">Do not call the [Start Method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) method before calling the `ExecuteApplication` method to activate a manifest-based application.</span></span> <span data-ttu-id="b2346-137">Если метод `Start` вызывается первым, вызов метода `ExecuteApplication` завершится ошибкой.</span><span class="sxs-lookup"><span data-stu-id="b2346-137">If the `Start` method is called first, the `ExecuteApplication` method call will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b2346-138">Требования</span><span class="sxs-lookup"><span data-stu-id="b2346-138">Requirements</span></span>  
 <span data-ttu-id="b2346-139">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b2346-139">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2346-140">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="b2346-140">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b2346-141">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b2346-141">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b2346-142">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b2346-142">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2346-143">См. также</span><span class="sxs-lookup"><span data-stu-id="b2346-143">See also</span></span>

- <xref:System.ActivationContext>
- <xref:System.AppDomainManager>
- <xref:System.ApplicationIdentity>
- [<span data-ttu-id="b2346-144">Интерфейс ICLRRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b2346-144">ICLRRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)
- [<span data-ttu-id="b2346-145">Метод SetAppDomainManager</span><span class="sxs-lookup"><span data-stu-id="b2346-145">SetAppDomainManager Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-setappdomainmanager-method.md)
- [<span data-ttu-id="b2346-146">Пошаговое руководство. Загрузка сборок по требованию с помощью API развертывания ClickOnce с использованием конструктора</span><span class="sxs-lookup"><span data-stu-id="b2346-146">Walkthrough: Downloading Assemblies on Demand with the ClickOnce Deployment API Using the Designer</span></span>](/visualstudio/deployment/walkthrough-downloading-assemblies-on-demand-with-the-clickonce-deployment-api-using-the-designer)
