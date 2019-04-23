---
title: Метод ICorRuntimeHost::CreateEvidence
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca54f779d257314b843838d90ca9996f1eb3237b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59081838"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="b0c30-102">Метод ICorRuntimeHost::CreateEvidence</span><span class="sxs-lookup"><span data-stu-id="b0c30-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="b0c30-103">Получает указатель интерфейса типа <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, что позволяет сайту создавать свидетельство безопасности для передачи [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) или [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) метод.</span><span class="sxs-lookup"><span data-stu-id="b0c30-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0c30-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0c30-104">Syntax</span></span>  
  
```  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b0c30-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0c30-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="b0c30-106">[out] Указатель интерфейса на <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> экземпляр, используемый для создания свидетельством безопасности.</span><span class="sxs-lookup"><span data-stu-id="b0c30-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="b0c30-107">Этот указатель является типизированным `IUnknown`, поэтому вызывающие объекты обычно следует вызывать `QueryInterface` на этом интерфейсе, чтобы получить указатель на <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b0c30-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b0c30-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="b0c30-108">Return Value</span></span>  
  
|<span data-ttu-id="b0c30-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b0c30-109">HRESULT</span></span>|<span data-ttu-id="b0c30-110">Описание</span><span class="sxs-lookup"><span data-stu-id="b0c30-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b0c30-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="b0c30-111">S_OK</span></span>|<span data-ttu-id="b0c30-112">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="b0c30-112">The operation was successful.</span></span>|  
|<span data-ttu-id="b0c30-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="b0c30-113">S_FALSE</span></span>|<span data-ttu-id="b0c30-114">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="b0c30-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="b0c30-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="b0c30-115">E_FAIL</span></span>|<span data-ttu-id="b0c30-116">Произошла неизвестная, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="b0c30-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="b0c30-117">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="b0c30-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="b0c30-118">Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="b0c30-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="b0c30-119">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="b0c30-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="b0c30-120">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="b0c30-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b0c30-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="b0c30-121">Remarks</span></span>  
 <span data-ttu-id="b0c30-122">Этот метод возвращает пустую коллекцию, не может быть заполнен из машинного кода.</span><span class="sxs-lookup"><span data-stu-id="b0c30-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="b0c30-123">Следует использовать <xref:System.Security.Policy.Evidence> метод вместо этого.</span><span class="sxs-lookup"><span data-stu-id="b0c30-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0c30-124">Требования</span><span class="sxs-lookup"><span data-stu-id="b0c30-124">Requirements</span></span>  
 <span data-ttu-id="b0c30-125">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0c30-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0c30-126">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="b0c30-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="b0c30-127">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b0c30-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b0c30-128">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="b0c30-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0c30-129">См. также</span><span class="sxs-lookup"><span data-stu-id="b0c30-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="b0c30-130">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="b0c30-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
