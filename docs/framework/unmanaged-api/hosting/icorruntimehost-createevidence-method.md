---
title: "Метод ICorRuntimeHost::CreateEvidence"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorRuntimeHost.CreateEvidence
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::CreateEvidence
helpviewer_keywords:
- CreateEvidence method [.NET Framework hosting]
- ICorRuntimeHost::CreateEvidence method [.NET Framework hosting]
ms.assetid: e235ea80-b84c-4442-a4c3-fc96c25a8eb9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 754b254fb9a41ab8bb900fdb5d0c10a126b804c7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="eb888-102">Метод ICorRuntimeHost::CreateEvidence</span><span class="sxs-lookup"><span data-stu-id="eb888-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="eb888-103">Получает указатель интерфейса типа <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, что позволяет узлу создавать свидетельством безопасности для передачи [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) или [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="eb888-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb888-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="eb888-104">Syntax</span></span>  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb888-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="eb888-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="eb888-106">[out] Указатель на интерфейс для <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> экземпляр, используемый для создания свидетельством безопасности.</span><span class="sxs-lookup"><span data-stu-id="eb888-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="eb888-107">Этот указатель является типизированным `IUnknown`, поэтому обычно следует вызывать вызывающим объектам `QueryInterface` на этот интерфейс для получения указателя на <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eb888-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="eb888-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="eb888-108">Return Value</span></span>  
  
|<span data-ttu-id="eb888-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="eb888-109">HRESULT</span></span>|<span data-ttu-id="eb888-110">Описание</span><span class="sxs-lookup"><span data-stu-id="eb888-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="eb888-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="eb888-111">S_OK</span></span>|<span data-ttu-id="eb888-112">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="eb888-112">The operation was successful.</span></span>|  
|<span data-ttu-id="eb888-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="eb888-113">S_FALSE</span></span>|<span data-ttu-id="eb888-114">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="eb888-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="eb888-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="eb888-115">E_FAIL</span></span>|<span data-ttu-id="eb888-116">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="eb888-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="eb888-117">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="eb888-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="eb888-118">Последующие вызовы любых размещающих интерфейсов API, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="eb888-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="eb888-119">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="eb888-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="eb888-120">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="eb888-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="eb888-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="eb888-121">Remarks</span></span>  
 <span data-ttu-id="eb888-122">Этот метод возвращает пустую коллекцию, которую нельзя заполнить из машинного кода.</span><span class="sxs-lookup"><span data-stu-id="eb888-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="eb888-123">Следует использовать <xref:System.Security.Policy.Evidence> метод вместо него.</span><span class="sxs-lookup"><span data-stu-id="eb888-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb888-124">Требования</span><span class="sxs-lookup"><span data-stu-id="eb888-124">Requirements</span></span>  
 <span data-ttu-id="eb888-125">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb888-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb888-126">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="eb888-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="eb888-127">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="eb888-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="eb888-128">**Версия платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="eb888-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb888-129">См. также</span><span class="sxs-lookup"><span data-stu-id="eb888-129">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="eb888-130">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="eb888-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
