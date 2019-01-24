---
title: Метод ICorThreadpool::CorSetMaxThreads
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorSetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorSetMaxThreads
helpviewer_keywords:
- ICorThreadpool::CorSetMaxThreads method [.NET Framework hosting]
- CorSetMaxThreads method [.NET Framework hosting]
ms.assetid: 4a846238-df4e-4060-ba3b-5173f6a51e85
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6c7cb97acbf089221f498ce9edcafb114ddeef27
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496902"
---
# <a name="icorthreadpoolcorsetmaxthreads-method"></a><span data-ttu-id="8d311-102">Метод ICorThreadpool::CorSetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="8d311-102">ICorThreadpool::CorSetMaxThreads Method</span></span>
<span data-ttu-id="8d311-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="8d311-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d311-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8d311-104">Syntax</span></span>  
  
```  
HRESULT CorSetMaxThreads (  
    [in] DWORD MaxWorkerThreads,  
    [in] DWORD MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="8d311-105">Требования</span><span class="sxs-lookup"><span data-stu-id="8d311-105">Requirements</span></span>  
 <span data-ttu-id="8d311-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d311-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d311-107">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8d311-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d311-108">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d311-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d311-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d311-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d311-110">См. также</span><span class="sxs-lookup"><span data-stu-id="8d311-110">See also</span></span>
- [<span data-ttu-id="8d311-111">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="8d311-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
