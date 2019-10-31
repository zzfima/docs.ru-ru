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
ms.openlocfilehash: 429ce0510162b3256cdf58f4820b04dd80243e29
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139634"
---
# <a name="icorruntimehostcreateevidence-method"></a><span data-ttu-id="6040b-102">Метод ICorRuntimeHost::CreateEvidence</span><span class="sxs-lookup"><span data-stu-id="6040b-102">ICorRuntimeHost::CreateEvidence Method</span></span>
<span data-ttu-id="6040b-103">Возвращает указатель интерфейса типа <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, который позволяет основному приложению создавать доказательства безопасности для передачи в метод [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) или [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6040b-103">Gets an interface pointer of type <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, which allows the host to create security evidence to pass to the [CreateDomain](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomain-method.md) or [CreateDomainEx](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createdomainex-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6040b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6040b-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateEvidence (  
    [out] IUnknown** pEvidence  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6040b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="6040b-105">Parameters</span></span>  
 `pEvidence`  
 <span data-ttu-id="6040b-106">заполняет Указатель интерфейса на экземпляр <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>, используемый для создания свидетельств безопасности.</span><span class="sxs-lookup"><span data-stu-id="6040b-106">[out] A interface pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType> instance used to create security evidence.</span></span> <span data-ttu-id="6040b-107">Этот указатель типизирован `IUnknown`, поэтому вызывающие объекты обычно должны вызывать `QueryInterface` для этого интерфейса, чтобы получить указатель на <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="6040b-107">This pointer is typed `IUnknown`, so callers should typically call `QueryInterface` on this interface to obtain a pointer to an <xref:System.Security.Principal.IIdentity?displayProperty=nameWithType>.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6040b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="6040b-108">Return Value</span></span>  
  
|<span data-ttu-id="6040b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6040b-109">HRESULT</span></span>|<span data-ttu-id="6040b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="6040b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6040b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="6040b-111">S_OK</span></span>|<span data-ttu-id="6040b-112">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="6040b-112">The operation was successful.</span></span>|  
|<span data-ttu-id="6040b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="6040b-113">S_FALSE</span></span>|<span data-ttu-id="6040b-114">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="6040b-114">The operation failed to complete.</span></span>|  
|<span data-ttu-id="6040b-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6040b-115">E_FAIL</span></span>|<span data-ttu-id="6040b-116">Произошла неизвестная фатальная ошибка.</span><span class="sxs-lookup"><span data-stu-id="6040b-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="6040b-117">Если метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="6040b-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="6040b-118">Последующие вызовы любых API размещения возвращают HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6040b-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="6040b-119">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6040b-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6040b-120">Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="6040b-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6040b-121">Заметки</span><span class="sxs-lookup"><span data-stu-id="6040b-121">Remarks</span></span>  
 <span data-ttu-id="6040b-122">Этот метод возвращает пустую коллекцию, которая не может быть заполнена из машинного кода.</span><span class="sxs-lookup"><span data-stu-id="6040b-122">This method returns an empty collection that cannot be populated from native code.</span></span> <span data-ttu-id="6040b-123">Вместо этого следует использовать метод <xref:System.Security.Policy.Evidence>.</span><span class="sxs-lookup"><span data-stu-id="6040b-123">You should use the <xref:System.Security.Policy.Evidence> method instead.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6040b-124">Требования</span><span class="sxs-lookup"><span data-stu-id="6040b-124">Requirements</span></span>  
 <span data-ttu-id="6040b-125">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6040b-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6040b-126">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6040b-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6040b-127">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6040b-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6040b-128">**Версия .NET Framework:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="6040b-128">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6040b-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6040b-129">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="6040b-130">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="6040b-130">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
