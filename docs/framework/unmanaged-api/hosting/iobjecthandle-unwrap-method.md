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
ms.openlocfilehash: da25055917743481f5a8314023ed94d552fe49ce
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526422"
---
# <a name="iobjecthandleunwrap-method"></a><span data-ttu-id="e0b3b-102">Метод IObjectHandle::Unwrap</span><span class="sxs-lookup"><span data-stu-id="e0b3b-102">IObjectHandle::Unwrap Method</span></span>
<span data-ttu-id="e0b3b-103">Распаковывает объект маршалинг по значению, косвенного обращения.</span><span class="sxs-lookup"><span data-stu-id="e0b3b-103">Unwraps a marshal-by-value object from indirection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0b3b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e0b3b-104">Syntax</span></span>  
  
```  
HRESULT Unwrap (  
    [out, retval] VARIANT *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e0b3b-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e0b3b-105">Parameters</span></span>  
 `ppv`  
 <span data-ttu-id="e0b3b-106">[out] Указатель на объект, который будет без оболочки.</span><span class="sxs-lookup"><span data-stu-id="e0b3b-106">[out] A pointer to the object to be unwrapped.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0b3b-107">Требования</span><span class="sxs-lookup"><span data-stu-id="e0b3b-107">Requirements</span></span>  
 <span data-ttu-id="e0b3b-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0b3b-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0b3b-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e0b3b-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e0b3b-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e0b3b-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e0b3b-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0b3b-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0b3b-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e0b3b-112">See also</span></span>

