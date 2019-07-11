---
title: Метод IAppDomainBinding::OnAppDomain
ms.date: 03/30/2017
api_name:
- IAppDomainBinding.OnAppDomain
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- OnAppDomain
helpviewer_keywords:
- IAppDomainBinding::OnAppDomain method [.NET Framework hosting]
- OnAppDomain method [.NET Framework hosting]
ms.assetid: b419dcc9-e8aa-484b-af0d-0f40358edb99
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 523f90966501e06994fb0e11b3c77aa62c378eef
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770464"
---
# <a name="iappdomainbindingonappdomain-method"></a><span data-ttu-id="e9f59-102">Метод IAppDomainBinding::OnAppDomain</span><span class="sxs-lookup"><span data-stu-id="e9f59-102">IAppDomainBinding::OnAppDomain Method</span></span>
<span data-ttu-id="e9f59-103">Вызывается общеязыковой среды выполнения (CLR), для уведомления узла о том, что домен приложения был создан.</span><span class="sxs-lookup"><span data-stu-id="e9f59-103">Called by the common language runtime (CLR) to notify the host that an application domain has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9f59-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e9f59-104">Syntax</span></span>  
  
```cpp  
HRESULT OnAppDomain (  
    [in] IUnknown* pAppdomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e9f59-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e9f59-105">Parameters</span></span>  
 `pAppdomain`  
 <span data-ttu-id="e9f59-106">[in] Указатель на [IUnknown](/cpp/atl/iunknown) объект интерфейса, представляющий новый домен приложения.</span><span class="sxs-lookup"><span data-stu-id="e9f59-106">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) interface object that represents the new application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e9f59-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e9f59-107">Requirements</span></span>  
 <span data-ttu-id="e9f59-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e9f59-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e9f59-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e9f59-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e9f59-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e9f59-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e9f59-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e9f59-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9f59-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e9f59-112">See also</span></span>

- [<span data-ttu-id="e9f59-113">Интерфейс IAppDomainBinding</span><span class="sxs-lookup"><span data-stu-id="e9f59-113">IAppDomainBinding Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iappdomainbinding-interface.md)
