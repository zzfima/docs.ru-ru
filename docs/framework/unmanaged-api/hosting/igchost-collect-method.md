---
title: Метод IGCHost::Collect
ms.date: 03/30/2017
api_name:
- IGCHost.Collect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fdacb454783cfb8f90ea5a73807f0a199e16475d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59154782"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="5d339-102">Метод IGCHost::Collect</span><span class="sxs-lookup"><span data-stu-id="5d339-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="5d339-103">Принудительное выполнения сборки для данного поколения, независимо от состояния текущей сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="5d339-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d339-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5d339-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5d339-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5d339-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="5d339-106">[in] Поколение, для которого следует выполнить сбор мусора.</span><span class="sxs-lookup"><span data-stu-id="5d339-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="5d339-107">Значение -1 указывает, что все поколения пройдут сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="5d339-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d339-108">Требования</span><span class="sxs-lookup"><span data-stu-id="5d339-108">Requirements</span></span>  
 <span data-ttu-id="5d339-109">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d339-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d339-110">**Заголовок.** GCHost.idl GCHost.h</span><span class="sxs-lookup"><span data-stu-id="5d339-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="5d339-111">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5d339-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5d339-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d339-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d339-113">См. также</span><span class="sxs-lookup"><span data-stu-id="5d339-113">See also</span></span>

- [<span data-ttu-id="5d339-114">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="5d339-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
