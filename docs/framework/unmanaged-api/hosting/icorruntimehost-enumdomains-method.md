---
title: "Метод ICorRuntimeHost::EnumDomains"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.EnumDomains
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: f12135134e38b3f52c66aa951d61a3da7cf5fa50
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="c6133-102">Метод ICorRuntimeHost::EnumDomains</span><span class="sxs-lookup"><span data-stu-id="c6133-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="c6133-103">Получает перечислитель для доменов в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="c6133-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6133-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6133-104">Syntax</span></span>  
  
```  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6133-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6133-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="c6133-106">[out] Перечислитель для доменов.</span><span class="sxs-lookup"><span data-stu-id="c6133-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c6133-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c6133-107">Return Value</span></span>  
  
|<span data-ttu-id="c6133-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c6133-108">HRESULT</span></span>|<span data-ttu-id="c6133-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c6133-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c6133-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c6133-110">S_OK</span></span>|<span data-ttu-id="c6133-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="c6133-111">The operation was successful.</span></span>|  
|<span data-ttu-id="c6133-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c6133-112">S_FALSE</span></span>|<span data-ttu-id="c6133-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="c6133-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="c6133-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c6133-114">E_FAIL</span></span>|<span data-ttu-id="c6133-115">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="c6133-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="c6133-116">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c6133-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="c6133-117">Последующие вызовы любых размещающих интерфейсов API, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c6133-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c6133-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c6133-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c6133-119">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c6133-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6133-120">Требования</span><span class="sxs-lookup"><span data-stu-id="c6133-120">Requirements</span></span>  
 <span data-ttu-id="c6133-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6133-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6133-122">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c6133-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c6133-123">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c6133-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c6133-124">**Версия платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="c6133-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6133-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c6133-125">See Also</span></span>  
 [<span data-ttu-id="c6133-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c6133-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
