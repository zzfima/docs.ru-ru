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
ms.openlocfilehash: bce005a677dcb74c176a6dddfb2726f6b1fd0e8a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33436911"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="b9f75-102">Метод IGCHost::Collect</span><span class="sxs-lookup"><span data-stu-id="b9f75-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="b9f75-103">Принудительно вызывает сборку мусора для данного поколения, независимо от состояния текущей сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="b9f75-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9f75-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b9f75-104">Syntax</span></span>  
  
```  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b9f75-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b9f75-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="b9f75-106">[in] Поколение, для которого требуется выполнить сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="b9f75-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="b9f75-107">Значение -1 указывает, что все поколения пройдут сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="b9f75-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9f75-108">Требования</span><span class="sxs-lookup"><span data-stu-id="b9f75-108">Requirements</span></span>  
 <span data-ttu-id="b9f75-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9f75-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9f75-110">**Заголовок:** GCHost.idl, GCHost.h</span><span class="sxs-lookup"><span data-stu-id="b9f75-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="b9f75-111">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b9f75-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b9f75-112">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9f75-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9f75-113">См. также</span><span class="sxs-lookup"><span data-stu-id="b9f75-113">See Also</span></span>  
 [<span data-ttu-id="b9f75-114">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="b9f75-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
