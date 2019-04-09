---
title: Метод ICorRuntimeHost::UnloadDomain
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.UnloadDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 492a60d3c8d18bec4e99ae778686fec6e8724248
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140573"
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="c96e0-102">Метод ICorRuntimeHost::UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="c96e0-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="c96e0-103">Выгружает указанный домен приложения из текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="c96e0-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c96e0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c96e0-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c96e0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c96e0-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c96e0-106">[in] Указатель типа <xref:System._AppDomain?displayProperty=nameWithType> , представляющий домен, к выгрузке.</span><span class="sxs-lookup"><span data-stu-id="c96e0-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c96e0-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="c96e0-107">Return Value</span></span>  
  
|<span data-ttu-id="c96e0-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c96e0-108">HRESULT</span></span>|<span data-ttu-id="c96e0-109">Описание</span><span class="sxs-lookup"><span data-stu-id="c96e0-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c96e0-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="c96e0-110">S_OK</span></span>|<span data-ttu-id="c96e0-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="c96e0-111">The operation was successful.</span></span>|  
|<span data-ttu-id="c96e0-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="c96e0-112">S_FALSE</span></span>|<span data-ttu-id="c96e0-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="c96e0-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="c96e0-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="c96e0-114">E_FAIL</span></span>|<span data-ttu-id="c96e0-115">Произошла неизвестная, разрушительного сбоя.</span><span class="sxs-lookup"><span data-stu-id="c96e0-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="c96e0-116">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="c96e0-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="c96e0-117">Последующие вызовы для любого API хостинга, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="c96e0-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="c96e0-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="c96e0-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="c96e0-119">Среда CLR не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="c96e0-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c96e0-120">Требования</span><span class="sxs-lookup"><span data-stu-id="c96e0-120">Requirements</span></span>  
 <span data-ttu-id="c96e0-121">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c96e0-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c96e0-122">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c96e0-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c96e0-123">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c96e0-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c96e0-124">**Версии платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="c96e0-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c96e0-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c96e0-125">See also</span></span>

- <xref:System._AppDomain>
- <xref:System.AppDomain>
- [<span data-ttu-id="c96e0-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="c96e0-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
