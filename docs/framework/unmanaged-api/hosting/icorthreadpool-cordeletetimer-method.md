---
title: Метод ICorThreadpool::CorDeleteTimer
ms.date: 03/30/2017
api_name:
- ICorThreadpool.CorDeleteTimer
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorDeleteTimer
helpviewer_keywords:
- ICorThreadpool::CorDeleteTimer method [.NET Framework hosting]
- CorDeleteTimer method [.NET Framework hosting]
ms.assetid: 74847c35-7ca1-466a-b750-b25e7b03d100
topic_type:
- apiref
ms.openlocfilehash: 42108f8b51954466a94d735ab9c4e49567b307e6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133291"
---
# <a name="icorthreadpoolcordeletetimer-method"></a><span data-ttu-id="a382a-102">Метод ICorThreadpool::CorDeleteTimer</span><span class="sxs-lookup"><span data-stu-id="a382a-102">ICorThreadpool::CorDeleteTimer Method</span></span>
<span data-ttu-id="a382a-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="a382a-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a382a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a382a-104">Syntax</span></span>  
  
```cpp  
HRESULT CorDeleteTimer (  
    [in]  HANDLE Timer,  
    [in]  HANDLE CompletionEvent,  
    [out] BOOL*  result  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="a382a-105">Требования</span><span class="sxs-lookup"><span data-stu-id="a382a-105">Requirements</span></span>  
 <span data-ttu-id="a382a-106">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a382a-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a382a-107">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a382a-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a382a-108">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="a382a-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a382a-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a382a-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a382a-110">См. также</span><span class="sxs-lookup"><span data-stu-id="a382a-110">See also</span></span>

- [<span data-ttu-id="a382a-111">Интерфейс ICorThreadpool</span><span class="sxs-lookup"><span data-stu-id="a382a-111">ICorThreadpool Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorthreadpool-interface.md)
