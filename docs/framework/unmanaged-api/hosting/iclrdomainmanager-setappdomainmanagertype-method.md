---
title: Метод ICLRDomainManager::SetAppDomainManagerType
ms.date: 03/30/2017
api_name:
- ICLRDomainManager.SetAppDomainManagerType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9b142f1a05036eddf44c69d8b7da95091dc8f445
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963093"
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="8baf7-102">Метод ICLRDomainManager::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="8baf7-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="8baf7-103">Задает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класса диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="8baf7-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8baf7-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8baf7-104">Syntax</span></span>  
  
```cpp  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8baf7-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8baf7-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="8baf7-106">окне Отображаемое имя сборки, содержащей тип диспетчера домена приложения; Например: "Адмгрексампле, Version = 1.0.0.0, культура = Neutral, PublicKeyToken = 6856bccf150f00b3".</span><span class="sxs-lookup"><span data-stu-id="8baf7-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="8baf7-107">окне Имя типа диспетчера домена приложения, включая пространство имен.</span><span class="sxs-lookup"><span data-stu-id="8baf7-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="8baf7-108">окне Сочетание значений перечисления [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) , которые предоставляют сведения о диспетчере доменов приложений.</span><span class="sxs-lookup"><span data-stu-id="8baf7-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8baf7-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8baf7-109">Return Value</span></span>  
 <span data-ttu-id="8baf7-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="8baf7-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8baf7-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8baf7-111">HRESULT</span></span>|<span data-ttu-id="8baf7-112">Описание</span><span class="sxs-lookup"><span data-stu-id="8baf7-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8baf7-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="8baf7-113">S_OK</span></span>|<span data-ttu-id="8baf7-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="8baf7-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="8baf7-115">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8baf7-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8baf7-116">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8baf7-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8baf7-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="8baf7-117">Remarks</span></span>  
 <span data-ttu-id="8baf7-118">В настоящее время единственным определенным значением для `dwInitializeDomainFlags` является `eInitializeNewDomainFlags_NoSecurityChanges`, которое указывает среде CLR, что диспетчер домена приложения не изменяет параметры безопасности <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> во время выполнения метода.</span><span class="sxs-lookup"><span data-stu-id="8baf7-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="8baf7-119">Это позволяет среде CLR оптимизировать загрузку сборок с условным <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибутом (APTCA).</span><span class="sxs-lookup"><span data-stu-id="8baf7-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="8baf7-120">Это может привести к значительному улучшению времени запуска, если транзитивное замыкание этого набора сборок велико.</span><span class="sxs-lookup"><span data-stu-id="8baf7-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="8baf7-121">Если узел указан `eInitializeNewDomainFlags_NoSecurityChanges` для диспетчера доменов приложений <xref:System.InvalidOperationException> , создается исключение, если выполняется любая попытка изменить безопасность домена приложения.</span><span class="sxs-lookup"><span data-stu-id="8baf7-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="8baf7-122">Вызов метода [ICLRControl:: SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)эквивалентен вызову `ICLRDomainManager::SetAppDomainManagerType` с `eInitializeNewDomainFlags_None`.</span><span class="sxs-lookup"><span data-stu-id="8baf7-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8baf7-123">Требования</span><span class="sxs-lookup"><span data-stu-id="8baf7-123">Requirements</span></span>  
 <span data-ttu-id="8baf7-124">**Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8baf7-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8baf7-125">**Заголовок.** Метахост. h</span><span class="sxs-lookup"><span data-stu-id="8baf7-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8baf7-126">**Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8baf7-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8baf7-127">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8baf7-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8baf7-128">См. также</span><span class="sxs-lookup"><span data-stu-id="8baf7-128">See also</span></span>

- [<span data-ttu-id="8baf7-129">Размещение</span><span class="sxs-lookup"><span data-stu-id="8baf7-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
- [<span data-ttu-id="8baf7-130">Интерфейс ICLRDomainManager</span><span class="sxs-lookup"><span data-stu-id="8baf7-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)
- [<span data-ttu-id="8baf7-131">Перечисление EInitializeNewDomainFlags</span><span class="sxs-lookup"><span data-stu-id="8baf7-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
