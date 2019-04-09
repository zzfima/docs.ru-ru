---
title: Метод ICorRuntimeHost::EnumDomains
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.EnumDomains
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::EnumDomains
helpviewer_keywords:
- ICorRuntimeHost::EnumDomains method [.NET Framework hosting]
- EnumDomains method [.NET Framework hosting]
ms.assetid: 96b74995-0cde-4876-b6df-7fc164e6a5d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 69fcc862e98e305105a6f17ca49940bd10cef39c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072562"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="2f40d-102">Метод ICorRuntimeHost::EnumDomains</span><span class="sxs-lookup"><span data-stu-id="2f40d-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="2f40d-103">Получает перечислитель для доменов в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="2f40d-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f40d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2f40d-104">Syntax</span></span>  
  
```  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f40d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2f40d-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="2f40d-106">[out] Перечислитель для доменов.</span><span class="sxs-lookup"><span data-stu-id="2f40d-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f40d-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="2f40d-107">Return Value</span></span>  
  
|<span data-ttu-id="2f40d-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2f40d-108">HRESULT</span></span>|<span data-ttu-id="2f40d-109">Описание</span><span class="sxs-lookup"><span data-stu-id="2f40d-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2f40d-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="2f40d-110">S_OK</span></span>|<span data-ttu-id="2f40d-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="2f40d-111">The operation was successful.</span></span>|  
|<span data-ttu-id="2f40d-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="2f40d-112">S_FALSE</span></span>|<span data-ttu-id="2f40d-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="2f40d-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="2f40d-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2f40d-114">E_FAIL</span></span>|<span data-ttu-id="2f40d-115">Произошла неизвестная, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="2f40d-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="2f40d-116">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="2f40d-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="2f40d-117">Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2f40d-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="2f40d-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2f40d-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2f40d-119">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="2f40d-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2f40d-120">Требования</span><span class="sxs-lookup"><span data-stu-id="2f40d-120">Requirements</span></span>  
 <span data-ttu-id="2f40d-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2f40d-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2f40d-122">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2f40d-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2f40d-123">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2f40d-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2f40d-124">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="2f40d-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f40d-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2f40d-125">See also</span></span>

- [<span data-ttu-id="2f40d-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="2f40d-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
