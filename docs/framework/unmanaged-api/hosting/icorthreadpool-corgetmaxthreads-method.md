---
title: Метод ICorThreadpool::CorGetMaxThreads
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorGetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorGetMaxThreads
helpviewer_keywords:
- CorGetMaxThreads method [.NET Framework hosting]
- ICorThreadpool::CorGetMaxThreads method [.NET Framework hosting]
ms.assetid: 2861533a-cda0-47b3-b716-0d363505289b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bbf5c02972a8331b3dd5e35ffcc4213e094e532d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59175738"
---
# <a name="icorthreadpoolcorgetmaxthreads-method"></a><span data-ttu-id="2bb0f-102">Метод ICorThreadpool::CorGetMaxThreads</span><span class="sxs-lookup"><span data-stu-id="2bb0f-102">ICorThreadpool::CorGetMaxThreads Method</span></span>
<span data-ttu-id="2bb0f-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="2bb0f-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2bb0f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2bb0f-104">Syntax</span></span>  
  
```  
HRESULT CorGetMaxThreads (  
    [out] DWORD *MaxWorkerThreads,  
    [out] DWORD *MaxIOCompletionThreads  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="2bb0f-105">Требования</span><span class="sxs-lookup"><span data-stu-id="2bb0f-105">Requirements</span></span>  
 <span data-ttu-id="2bb0f-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2bb0f-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2bb0f-107">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2bb0f-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2bb0f-108">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2bb0f-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="2bb0f-109">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="2bb0f-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="2bb0f-110">См. также</span><span class="sxs-lookup"><span data-stu-id="2bb0f-110">See also</span></span>

- [<span data-ttu-id="2bb0f-111">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="2bb0f-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
