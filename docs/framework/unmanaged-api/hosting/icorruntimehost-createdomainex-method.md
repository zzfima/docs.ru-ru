---
title: Метод ICorRuntimeHost::CreateDomainEx
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainEx
helpviewer_keywords:
- ICorRuntimeHost::CreateDomainEx method [.NET Framework hosting]
- CreateDomainEx method [.NET Framework hosting]
ms.assetid: 1bdde382-f8ba-4cc8-94b2-d1ac919c585e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a538f14e7dbf24a94343f364201e968bffa757f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61936959"
---
# <a name="icorruntimehostcreatedomainex-method"></a><span data-ttu-id="8dac1-102">Метод ICorRuntimeHost::CreateDomainEx</span><span class="sxs-lookup"><span data-stu-id="8dac1-102">ICorRuntimeHost::CreateDomainEx Method</span></span>
<span data-ttu-id="8dac1-103">Создает домен приложения.</span><span class="sxs-lookup"><span data-stu-id="8dac1-103">Creates an application domain.</span></span> <span data-ttu-id="8dac1-104">Вызывающий объект получает указатель интерфейса типа <xref:System._AppDomain>, чтобы экземпляр типа <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8dac1-104">The caller receives an interface pointer, of type <xref:System._AppDomain>, to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span> <span data-ttu-id="8dac1-105">Этот метод позволяет вызывающей стороне передать экземпляр IAppDomainSetup для настройки дополнительных функций возвращенного <xref:System._AppDomain> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="8dac1-105">This method allows the caller to pass an IAppDomainSetup instance to configure additional features of the returned <xref:System._AppDomain> instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8dac1-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8dac1-106">Syntax</span></span>  
  
```  
HRESULT CreateDomainEx (  
    [in] LPCWSTR     pwzFriendlyName,  
    [in] IUnknown*   pSetup,  
    [in] IUnknown*   pIdentityArray,  
    [out] IUnknown** pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8dac1-107">Параметры</span><span class="sxs-lookup"><span data-stu-id="8dac1-107">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="8dac1-108">[in] Необязательный параметр, используемый нужно присвоить понятное имя домена.</span><span class="sxs-lookup"><span data-stu-id="8dac1-108">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="8dac1-109">Это понятное имя может отображаться в пользовательском интерфейсе, такие как отладчики для определения домена.</span><span class="sxs-lookup"><span data-stu-id="8dac1-109">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pSetup`  
 <span data-ttu-id="8dac1-110">[in] Указатель необязательный интерфейс типа `IAppDomainSetup`достигается путем вызова [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8dac1-110">[in] An optional interface pointer of type `IAppDomainSetup`, obtained by a call to the [ICorRuntimeHost::CreateDomainSetup](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainsetup-method.md) method.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="8dac1-111">[in] Необязательный массив указателей на `IIdentity` экземпляры, представляющие свидетельство, сопоставленное посредством политики безопасности для установления набора разрешений.</span><span class="sxs-lookup"><span data-stu-id="8dac1-111">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a permission set.</span></span> <span data-ttu-id="8dac1-112">`IIdentity` Может быть получен путем вызова [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="8dac1-112">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="8dac1-113">[out] Указатель интерфейса типа <xref:System._AppDomain> к экземпляру <xref:System.AppDomain?displayProperty=nameWithType> , можно использовать для последующего управления домена.</span><span class="sxs-lookup"><span data-stu-id="8dac1-113">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8dac1-114">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="8dac1-114">Return Value</span></span>  
  
|<span data-ttu-id="8dac1-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8dac1-115">HRESULT</span></span>|<span data-ttu-id="8dac1-116">Описание</span><span class="sxs-lookup"><span data-stu-id="8dac1-116">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8dac1-117">S_OK</span><span class="sxs-lookup"><span data-stu-id="8dac1-117">S_OK</span></span>|<span data-ttu-id="8dac1-118">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="8dac1-118">The operation was successful.</span></span>|  
|<span data-ttu-id="8dac1-119">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8dac1-119">S_FALSE</span></span>|<span data-ttu-id="8dac1-120">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="8dac1-120">The operation failed to complete.</span></span>|  
|<span data-ttu-id="8dac1-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8dac1-121">E_FAIL</span></span>|<span data-ttu-id="8dac1-122">Произошла неизвестная, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="8dac1-122">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="8dac1-123">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="8dac1-123">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="8dac1-124">Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8dac1-124">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8dac1-125">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8dac1-125">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8dac1-126">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="8dac1-126">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8dac1-127">Примечания</span><span class="sxs-lookup"><span data-stu-id="8dac1-127">Remarks</span></span>  
 <span data-ttu-id="8dac1-128">`CreateDomainEx` расширяет возможности [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) , позволяя вызывающей стороне передать в `IAppDomainSetup` экземпляр со значениями свойств для настройки домена приложения.</span><span class="sxs-lookup"><span data-stu-id="8dac1-128">`CreateDomainEx` extends the capabilities of [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) by allowing the caller to pass in an `IAppDomainSetup` instance with property values for configuring the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8dac1-129">Требования</span><span class="sxs-lookup"><span data-stu-id="8dac1-129">Requirements</span></span>  
 <span data-ttu-id="8dac1-130">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8dac1-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8dac1-131">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8dac1-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8dac1-132">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8dac1-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8dac1-133">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="8dac1-133">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8dac1-134">См. также</span><span class="sxs-lookup"><span data-stu-id="8dac1-134">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="8dac1-135">Метод CreateDomain</span><span class="sxs-lookup"><span data-stu-id="8dac1-135">CreateDomain Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md)
- [<span data-ttu-id="8dac1-136">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="8dac1-136">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
