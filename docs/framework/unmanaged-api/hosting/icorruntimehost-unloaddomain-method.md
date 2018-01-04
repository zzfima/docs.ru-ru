---
title: "Метод ICorRuntimeHost::UnloadDomain"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.UnloadDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::UnloadDomain
helpviewer_keywords:
- ICorRuntimeHost::UnloadDomain method [.NET Framework hosting]
- UnloadDomain method [.NET Framework hosting]
ms.assetid: dd9e9204-a80d-44f3-8192-779224b35056
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 067b60b9da02300e9e7316712d0058a61ab8a697
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorruntimehostunloaddomain-method"></a><span data-ttu-id="bdfee-102">Метод ICorRuntimeHost::UnloadDomain</span><span class="sxs-lookup"><span data-stu-id="bdfee-102">ICorRuntimeHost::UnloadDomain Method</span></span>
<span data-ttu-id="bdfee-103">Выгружает заданный домен приложения из текущего процесса.</span><span class="sxs-lookup"><span data-stu-id="bdfee-103">Unloads the specified application domain from the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdfee-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bdfee-104">Syntax</span></span>  
  
```  
HRESULT UnloadDomain (  
    [in] IUnknown* pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="bdfee-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bdfee-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="bdfee-106">[in] Указатель типа <xref:System._AppDomain?displayProperty=nameWithType> , представляющий домен, который будет выгружен.</span><span class="sxs-lookup"><span data-stu-id="bdfee-106">[in] A pointer of type <xref:System._AppDomain?displayProperty=nameWithType> that represents the domain to be unloaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bdfee-107">Возвращаемое значение</span><span class="sxs-lookup"><span data-stu-id="bdfee-107">Return Value</span></span>  
  
|<span data-ttu-id="bdfee-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bdfee-108">HRESULT</span></span>|<span data-ttu-id="bdfee-109">Описание</span><span class="sxs-lookup"><span data-stu-id="bdfee-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bdfee-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="bdfee-110">S_OK</span></span>|<span data-ttu-id="bdfee-111">Операция выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="bdfee-111">The operation was successful.</span></span>|  
|<span data-ttu-id="bdfee-112">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="bdfee-112">S_FALSE</span></span>|<span data-ttu-id="bdfee-113">Не удалось завершить операцию.</span><span class="sxs-lookup"><span data-stu-id="bdfee-113">The operation failed to complete.</span></span>|  
|<span data-ttu-id="bdfee-114">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bdfee-114">E_FAIL</span></span>|<span data-ttu-id="bdfee-115">Неизвестный, Разрушительный сбой.</span><span class="sxs-lookup"><span data-stu-id="bdfee-115">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="bdfee-116">Если метод вернет значение E_FAIL, общеязыковой среды выполнения (CLR) больше не может использоваться в процессе.</span><span class="sxs-lookup"><span data-stu-id="bdfee-116">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="bdfee-117">Последующие вызовы любых размещающих интерфейсов API, возвращают значение HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bdfee-117">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bdfee-118">ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bdfee-118">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bdfee-119">Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.</span><span class="sxs-lookup"><span data-stu-id="bdfee-119">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bdfee-120">Требования</span><span class="sxs-lookup"><span data-stu-id="bdfee-120">Requirements</span></span>  
 <span data-ttu-id="bdfee-121">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bdfee-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdfee-122">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bdfee-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bdfee-123">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bdfee-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bdfee-124">**Версия платформы .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="bdfee-124">**.NET Framework Version:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdfee-125">См. также</span><span class="sxs-lookup"><span data-stu-id="bdfee-125">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="bdfee-126">Интерфейс ICorRuntimeHost</span><span class="sxs-lookup"><span data-stu-id="bdfee-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
