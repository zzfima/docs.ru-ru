---
title: "Метод IGCHost::Collect"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost.Collect
api_location: mscoree.dll
api_type: COM
f1_keywords: Collect
helpviewer_keywords:
- Collect method, IGCHost interface [.NET Framework hosting]
- IGCHost::Collect method [.NET Framework hosting]
ms.assetid: fc7d9448-3186-494d-9f0d-ea39717e9a82
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d97a988db48cc9bfdf8cf1e260c28e0169eb73f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="igchostcollect-method"></a><span data-ttu-id="8cbdd-102">Метод IGCHost::Collect</span><span class="sxs-lookup"><span data-stu-id="8cbdd-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="8cbdd-103">Принудительно вызывает сборку мусора для данного поколения, независимо от состояния текущей сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="8cbdd-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cbdd-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8cbdd-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8cbdd-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8cbdd-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="8cbdd-106">[in] Поколение, для которого требуется выполнить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="8cbdd-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="8cbdd-107">Значение -1 указывает, что все поколения пройдут сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="8cbdd-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cbdd-108">Требования</span><span class="sxs-lookup"><span data-stu-id="8cbdd-108">Requirements</span></span>  
 <span data-ttu-id="8cbdd-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cbdd-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cbdd-110">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="8cbdd-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="8cbdd-111">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8cbdd-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8cbdd-112">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cbdd-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cbdd-113">См. также</span><span class="sxs-lookup"><span data-stu-id="8cbdd-113">See Also</span></span>  
 [<span data-ttu-id="8cbdd-114">Igchost-интерфейс</span><span class="sxs-lookup"><span data-stu-id="8cbdd-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
