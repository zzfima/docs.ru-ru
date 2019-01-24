---
title: Метод ICorRuntimeHost::CreateDomainSetup
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.CreateDomainSetup
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateDomainSetup
helpviewer_keywords:
- CreateDomainSetup method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomainSetup method [.NET Framework hosting]
ms.assetid: c21dab60-fb65-47d9-8a94-7fd47ca53b48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ab00a93b0bedb8f7ea1425c65c4940b57f11219
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54591604"
---
# <a name="icorruntimehostcreatedomainsetup-method"></a><span data-ttu-id="b3e16-102">Метод ICorRuntimeHost::CreateDomainSetup</span><span class="sxs-lookup"><span data-stu-id="b3e16-102">ICorRuntimeHost::CreateDomainSetup Method</span></span>
<span data-ttu-id="b3e16-103">Возвращает указатель интерфейса типа IAppDomainSetup для <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b3e16-103">Gets an interface pointer of type IAppDomainSetup to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="b3e16-104">`IAppDomainSetup` Предоставляет методы для настройки аспектов домена приложения, прежде чем она создается.</span><span class="sxs-lookup"><span data-stu-id="b3e16-104">`IAppDomainSetup` provides methods to configure aspects of an application domain before it is created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3e16-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b3e16-105">Syntax</span></span>  
  
```  
HRESULT CreateDomainSetup (  
    [out] IUnknown** pAppDomainSetup  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b3e16-106">Параметры</span><span class="sxs-lookup"><span data-stu-id="b3e16-106">Parameters</span></span>  
 `pAppDomainSetup`  
 <span data-ttu-id="b3e16-107">[out] Указатель интерфейса на <xref:System.AppDomainSetup?displayProperty=nameWithType> экземпляра.</span><span class="sxs-lookup"><span data-stu-id="b3e16-107">[out] An interface pointer to an <xref:System.AppDomainSetup?displayProperty=nameWithType> instance.</span></span> <span data-ttu-id="b3e16-108">Этот параметр имеет тип `IUnknown`, поэтому вызывающие объекты обычно должен вызвать `QueryInterface` на этот указатель для получения указателя интерфейса типа `IAppDomainSetup`.</span><span class="sxs-lookup"><span data-stu-id="b3e16-108">This parameter is typed as `IUnknown`, so callers should generally call `QueryInterface` on this pointer to obtain an interface pointer of type `IAppDomainSetup`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b3e16-109">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b3e16-109">Return Value</span></span>  
  
|<span data-ttu-id="b3e16-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b3e16-110">HRESULT</span></span>|<span data-ttu-id="b3e16-111">Описание</span><span class="sxs-lookup"><span data-stu-id="b3e16-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b3e16-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="b3e16-112">S_OK</span></span>|<span data-ttu-id="b3e16-113">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="b3e16-113">The operation was successful.</span></span>|  
|<span data-ttu-id="b3e16-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b3e16-114">S_FALSE</span></span>|<span data-ttu-id="b3e16-115">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="b3e16-115">The operation failed to complete.</span></span>|  
|<span data-ttu-id="b3e16-116">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b3e16-116">E_FAIL</span></span>|<span data-ttu-id="b3e16-117">Произошла неизвестная, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="b3e16-117">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b3e16-118">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b3e16-118">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b3e16-119">Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b3e16-119">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b3e16-120">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b3e16-120">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b3e16-121">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b3e16-121">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b3e16-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="b3e16-122">Remarks</span></span>  
 <span data-ttu-id="b3e16-123">Указатель, возвращенный из этого метода обычно передается в качестве параметра [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="b3e16-123">The pointer returned from this method is typically passed as a parameter to the [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b3e16-124">Требования</span><span class="sxs-lookup"><span data-stu-id="b3e16-124">Requirements</span></span>  
 <span data-ttu-id="b3e16-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3e16-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3e16-126">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b3e16-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b3e16-127">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b3e16-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b3e16-128">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="b3e16-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3e16-129">См. также</span><span class="sxs-lookup"><span data-stu-id="b3e16-129">See also</span></span>
- <xref:System._AppDomain>
- <xref:System.AppDomain>
- <xref:System.AppDomainSetup>
- <xref:System.IAppDomainSetup?displayProperty=nameWithType>
- [<span data-ttu-id="b3e16-130">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b3e16-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
