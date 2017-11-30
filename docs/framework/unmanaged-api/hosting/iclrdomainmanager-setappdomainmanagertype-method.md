---
title: "Метод ICLRDomainManager::SetAppDomainManagerType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager.SetAppDomainManagerType
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager::SetAppDomainManagerType
helpviewer_keywords:
- SetAppDomainManagerType method, ICLRDomainManager interface [.NET Framework hosting]
- ICLRDomainManager::SetAppDomainManagerType method [.NET Framework hosting]
ms.assetid: ee91abb0-cb74-41dd-927b-e117fb8ffdf4
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 17c99d21155d8f985ea455e171067855edcafedc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdomainmanagersetappdomainmanagertype-method"></a><span data-ttu-id="0ae39-102">Метод ICLRDomainManager::SetAppDomainManagerType</span><span class="sxs-lookup"><span data-stu-id="0ae39-102">ICLRDomainManager::SetAppDomainManagerType Method</span></span>
<span data-ttu-id="0ae39-103">Указывает тип, производный от <xref:System.AppDomainManager?displayProperty=nameWithType> класса диспетчера домена приложения, который будет использоваться для инициализации домена приложения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0ae39-103">Specifies the type, derived from the <xref:System.AppDomainManager?displayProperty=nameWithType> class, of the application domain manager that will be used to initialize the default application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0ae39-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="0ae39-104">Syntax</span></span>  
  
```  
HRESULT SetAppDomainManagerType(  
    [in] LPCWSTR wszAppDomainManagerAssembly,  
    [in] LPCWSTR wszAppDomainManagerType,  
    [in] EInitializeNewDomainFlags dwInitializeDomainFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0ae39-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="0ae39-105">Parameters</span></span>  
 `wszAppDomainManagerAssembly`  
 <span data-ttu-id="0ae39-106">[in] Отображаемое имя сборки, содержащей тип диспетчера домена приложения; Например: «AdMgrExample, Version = 1.0.0.0, язык и региональные параметры = neutral, PublicKeyToken = 6856bccf150f00b3».</span><span class="sxs-lookup"><span data-stu-id="0ae39-106">[in] The display name of the assembly that contains the application domain manager type; for example: "AdMgrExample, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6856bccf150f00b3".</span></span>  
  
 `wszAppDomainManagerType`  
 <span data-ttu-id="0ae39-107">[in] Имя типа диспетчера домена приложения, включая пространство имен.</span><span class="sxs-lookup"><span data-stu-id="0ae39-107">[in] The type name of the application domain manager, including the namespace.</span></span>  
  
 `dwInitializeDomainFlags`  
 <span data-ttu-id="0ae39-108">[in] Сочетание [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) значений перечисления, предоставляющих сведения о диспетчере домена приложения.</span><span class="sxs-lookup"><span data-stu-id="0ae39-108">[in] A combination of [EInitializeNewDomainFlags](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md) enumeration values that provide information about the application domain manager.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0ae39-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="0ae39-109">Return Value</span></span>  
 <span data-ttu-id="0ae39-110">Этот метод возвращает следующие конкретные результаты HRESULT, а также ошибки HRESULT, которые указывают на сбой метода.</span><span class="sxs-lookup"><span data-stu-id="0ae39-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0ae39-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0ae39-111">HRESULT</span></span>|<span data-ttu-id="0ae39-112">Описание</span><span class="sxs-lookup"><span data-stu-id="0ae39-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0ae39-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="0ae39-113">S_OK</span></span>|<span data-ttu-id="0ae39-114">Метод завершился успешно.</span><span class="sxs-lookup"><span data-stu-id="0ae39-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="0ae39-115">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0ae39-115">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0ae39-116">Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="0ae39-116">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0ae39-117">Примечания</span><span class="sxs-lookup"><span data-stu-id="0ae39-117">Remarks</span></span>  
 <span data-ttu-id="0ae39-118">В настоящее время единственным пользователем значение для `dwInitializeDomainFlags` — `eInitializeNewDomainFlags_NoSecurityChanges`, который сообщает среде (CLR), диспетчер домена приложения, не изменяйте параметры безопасности во время выполнения <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> метод.</span><span class="sxs-lookup"><span data-stu-id="0ae39-118">Currently, the only defined value for `dwInitializeDomainFlags` is `eInitializeNewDomainFlags_NoSecurityChanges`, which tells the common language runtime (CLR) that the application domain manager will not modify security settings during the execution of the <xref:System.AppDomainManager.InitializeNewDomain%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="0ae39-119">Это позволяет среде CLR для оптимизации загрузки сборок, содержащих условной <xref:System.Security.AllowPartiallyTrustedCallersAttribute> атрибут (APTCA).</span><span class="sxs-lookup"><span data-stu-id="0ae39-119">This allows the CLR to optimize the loading of assemblies that have the conditional <xref:System.Security.AllowPartiallyTrustedCallersAttribute> (APTCA) attribute.</span></span> <span data-ttu-id="0ae39-120">Это может привести к существенным усовершенствованием времени запуска, если транзитивное замыкание этого набора сборок имеет большой размер.</span><span class="sxs-lookup"><span data-stu-id="0ae39-120">This can result in a significant improvement in startup time if the transitive closure of this set of assemblies is large.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0ae39-121">Если узел указывает `eInitializeNewDomainFlags_NoSecurityChanges` для домена приложения <xref:System.InvalidOperationException> создается, если все попытки изменения уровня безопасности домена приложения.</span><span class="sxs-lookup"><span data-stu-id="0ae39-121">If the host specifies `eInitializeNewDomainFlags_NoSecurityChanges` for the application domain manager, an <xref:System.InvalidOperationException> is thrown if any attempt is made to modify the security of the application domain.</span></span>  
  
 <span data-ttu-id="0ae39-122">Вызов [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)метода эквивалентен вызову `ICLRDomainManager::SetAppDomainManagerType` с `eInitializeNewDomainFlags_None`.</span><span class="sxs-lookup"><span data-stu-id="0ae39-122">Calling the [ICLRControl::SetAppDomainManagerType](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-setappdomainmanagertype-method.md)method is equivalent to calling `ICLRDomainManager::SetAppDomainManagerType` with `eInitializeNewDomainFlags_None`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0ae39-123">Требования</span><span class="sxs-lookup"><span data-stu-id="0ae39-123">Requirements</span></span>  
 <span data-ttu-id="0ae39-124">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0ae39-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0ae39-125">**Заголовок:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="0ae39-125">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0ae39-126">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0ae39-126">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0ae39-127">**Версии платформы .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0ae39-127">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0ae39-128">См. также</span><span class="sxs-lookup"><span data-stu-id="0ae39-128">See Also</span></span>  
 [<span data-ttu-id="0ae39-129">Размещение</span><span class="sxs-lookup"><span data-stu-id="0ae39-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)  
 [<span data-ttu-id="0ae39-130">Iclrdomainmanager-интерфейс</span><span class="sxs-lookup"><span data-stu-id="0ae39-130">ICLRDomainManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-interface.md)  
 [<span data-ttu-id="0ae39-131">Einitializenewdomainflags-перечисление</span><span class="sxs-lookup"><span data-stu-id="0ae39-131">EInitializeNewDomainFlags Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/einitializenewdomainflags-enumeration.md)
