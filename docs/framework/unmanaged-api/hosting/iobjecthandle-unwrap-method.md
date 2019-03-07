---
title: Метод IObjectHandle::Unwrap
ms.date: 03/30/2017
api_name:
- IObjectHandle.Unwrap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- Unwrap
helpviewer_keywords:
- Unwrap method [.NET Framework hosting]
- IObjectHandle::Unwrap method [.NET Framework hosting]
ms.assetid: 794c6f8e-ed58-416b-b756-e864f2c958f7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5539d77b93be1f56102970e9febe6f63599d78e7
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57502973"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="c51d4-102">Метод IObjectHandle::Unwrap</span><span class="sxs-lookup"><span data-stu-id="c51d4-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="c51d4-103">Распаковывает объект маршалинг по значению, косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="c51d4-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c51d4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c51d4-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c51d4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c51d4-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="c51d4-106">[out] Указатель на объект, который будет без оболочки.</span><span class="sxs-lookup"><span data-stu-id="c51d4-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c51d4-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c51d4-107">Requirements</span></span>  
 <span data-ttu-id="c51d4-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c51d4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c51d4-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c51d4-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c51d4-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c51d4-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c51d4-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c51d4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c51d4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c51d4-112">See also</span></span>

