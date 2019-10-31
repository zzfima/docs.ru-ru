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
ms.openlocfilehash: e20ea6addc1ae3f99b4b3d65f532e0128ac160b3
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134970"
---
# <a name="igchostcollect-method"></a><span data-ttu-id="c096f-102">Метод IGCHost::Collect</span><span class="sxs-lookup"><span data-stu-id="c096f-102">IGCHost::Collect Method</span></span>
<span data-ttu-id="c096f-103">Принудительно выполняет сбор данных для данного поколения независимо от состояния текущей сборки мусора.</span><span class="sxs-lookup"><span data-stu-id="c096f-103">Forces a collection to occur for the given generation, regardless of the state of the current garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c096f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c096f-104">Syntax</span></span>  
  
```cpp  
HRESULT Collect (  
    [in] LONG Generation  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c096f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c096f-105">Parameters</span></span>  
 `Generation`  
 <span data-ttu-id="c096f-106">окне Поколение, на котором выполняется сборка мусора.</span><span class="sxs-lookup"><span data-stu-id="c096f-106">[in] The generation on which to perform the garbage collection.</span></span> <span data-ttu-id="c096f-107">Значение-1 указывает, что все поколения проходят сборку мусора.</span><span class="sxs-lookup"><span data-stu-id="c096f-107">A value of -1 indicates that all generations will undergo a garbage collection.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c096f-108">Требования</span><span class="sxs-lookup"><span data-stu-id="c096f-108">Requirements</span></span>  
 <span data-ttu-id="c096f-109">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c096f-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c096f-110">**Заголовок:** Гчост. idl, Гчост. h</span><span class="sxs-lookup"><span data-stu-id="c096f-110">**Header:** GCHost.idl, GCHost.h</span></span>  
  
 <span data-ttu-id="c096f-111">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="c096f-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c096f-112">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c096f-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c096f-113">См. также</span><span class="sxs-lookup"><span data-stu-id="c096f-113">See also</span></span>

- [<span data-ttu-id="c096f-114">Интерфейс IGCHost</span><span class="sxs-lookup"><span data-stu-id="c096f-114">IGCHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igchost-interface.md)
