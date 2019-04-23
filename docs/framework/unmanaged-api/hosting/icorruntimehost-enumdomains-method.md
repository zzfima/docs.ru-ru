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
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59072562"
---
# <a name="icorruntimehostenumdomains-method"></a><span data-ttu-id="e3ca4-102">Метод ICorRuntimeHost::EnumDomains</span><span class="sxs-lookup"><span data-stu-id="e3ca4-102">ICorRuntimeHost::EnumDomains Method</span></span>
<span data-ttu-id="e3ca4-103">Получает перечислитель для доменов в текущем процессе.</span><span class="sxs-lookup"><span data-stu-id="e3ca4-103">Gets an enumerator for the domains in the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3ca4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e3ca4-104">Syntax</span></span>  
  
```  
HRESULT EnumDomains (  
    [out] HCORENUM *hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3ca4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e3ca4-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="e3ca4-106">[out] Перечислитель для доменов.</span><span class="sxs-lookup"><span data-stu-id="e3ca4-106">[out] An enumerator for the domains.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e3ca4-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="e3ca4-107">Return Value</span></span>  
  
|<span data-ttu-id="e3ca4-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e3ca4-108">HRESULT</span></span>|<span data-ttu-id="e3ca4-109">Описание</span><span class="sxs-lookup"><span data-stu-id="e3ca4-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e3ca4-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="e3ca4-110">S_OK</span></span>|<span data-ttu-id="e3ca4-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="e3ca4-111">The operation was successful.</span></span>|  
|<span data-ttu-id="e3ca4-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e3ca4-112">S_FALSE</span></span>|<span data-ttu-id="e3ca4-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="e3ca4-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e3ca4-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e3ca4-114">E_FAIL</span></span>|<span data-ttu-id="e3ca4-115">Произошла неизвестная, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="e3ca4-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e3ca4-116">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="e3ca4-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="e3ca4-117">Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e3ca4-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e3ca4-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e3ca4-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e3ca4-119">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="e3ca4-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3ca4-120">Требования</span><span class="sxs-lookup"><span data-stu-id="e3ca4-120">Requirements</span></span>  
 <span data-ttu-id="e3ca4-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3ca4-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3ca4-122">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e3ca4-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e3ca4-123">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e3ca4-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e3ca4-124">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="e3ca4-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3ca4-125">См. также</span><span class="sxs-lookup"><span data-stu-id="e3ca4-125">See also</span></span>

- [<span data-ttu-id="e3ca4-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="e3ca4-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
