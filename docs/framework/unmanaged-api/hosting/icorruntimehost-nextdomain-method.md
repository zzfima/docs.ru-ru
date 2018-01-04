---
title: "Метод ICorRuntimeHost::NextDomain"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.NextDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::NextDomain
helpviewer_keywords:
- ICorRuntimeHost::NextDomain method [.NET Framework hosting]
- NextDomain method [.NET Framework hosting]
ms.assetid: fe07a05b-f6d6-44b5-ab01-b9a6eb15c350
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0e539cd4071fe9713ed53f66c2f67b24b787d259
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostnextdomain-method"></a><span data-ttu-id="acb5b-102">Метод ICorRuntimeHost::NextDomain</span><span class="sxs-lookup"><span data-stu-id="acb5b-102">ICorRuntimeHost::NextDomain Method</span></span>
<span data-ttu-id="acb5b-103">Получает указатель интерфейса на следующий домен в перечислении.</span><span class="sxs-lookup"><span data-stu-id="acb5b-103">Gets an interface pointer to the next domain in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="acb5b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="acb5b-104">Syntax</span></span>  
  
```  
HRESULT NextDomain (  
    [in] HCORENUM hEnum,  
    [out] void** pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="acb5b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="acb5b-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="acb5b-106">[in] Перечислитель, который был получен с помощью вызова [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span><span class="sxs-lookup"><span data-stu-id="acb5b-106">[in] The enumerator that was obtained through a call to [EnumDomains](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-enumdomains-method.md).</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="acb5b-107">[out] Указатель интерфейса <xref:System._AppDomain?displayProperty=nameWithType> тип, представляющий следующий домен в перечислении, или значение null, если дополнительные домены не существует.</span><span class="sxs-lookup"><span data-stu-id="acb5b-107">[out] An interface pointer to the <xref:System._AppDomain?displayProperty=nameWithType> type that represents the next domain in the enumeration, or null, if no more domains exist.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="acb5b-108">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="acb5b-108">Return Value</span></span>  
  
|<span data-ttu-id="acb5b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="acb5b-109">HRESULT</span></span>|<span data-ttu-id="acb5b-110">Описание</span><span class="sxs-lookup"><span data-stu-id="acb5b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="acb5b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="acb5b-111">S_OK</span></span>|<span data-ttu-id="acb5b-112">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="acb5b-112">The operation was successful.</span></span>|  
|<span data-ttu-id="acb5b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="acb5b-113">S_FALSE</span></span>|<span data-ttu-id="acb5b-114">Не удалось завершить операцию, или отсутствуют дополнительные домены в перечислении.</span><span class="sxs-lookup"><span data-stu-id="acb5b-114">The operation failed to complete, or there are no more domains in the enumeration.</span></span>|  
|<span data-ttu-id="acb5b-115">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="acb5b-115">E_FAIL</span></span>|<span data-ttu-id="acb5b-116">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="acb5b-116">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="acb5b-117">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="acb5b-117">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="acb5b-118">Последующие вызовы любых размещающих интерфейсов API, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="acb5b-118">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="acb5b-119">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="acb5b-119">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="acb5b-120">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="acb5b-120">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="acb5b-121">Требования</span><span class="sxs-lookup"><span data-stu-id="acb5b-121">Requirements</span></span>  
 <span data-ttu-id="acb5b-122">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="acb5b-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="acb5b-123">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="acb5b-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="acb5b-124">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="acb5b-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="acb5b-125">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="acb5b-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acb5b-126">См. также</span><span class="sxs-lookup"><span data-stu-id="acb5b-126">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="acb5b-127">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="acb5b-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
