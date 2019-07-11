---
title: Метод ITypeName::GetTypeArguments
ms.date: 03/30/2017
api_name:
- ITypeName.GetTypeArguments
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- GetTypeArguments
helpviewer_keywords:
- ITypeName::GetTypeArguments method [.NET Framework hosting]
- GetTypeArguments method [.NET Framework hosting]
ms.assetid: 638d77df-ff9c-40d9-88ee-930f5f87ada1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f4c56f6a2eecb614d2d8fbc7c402e90a7cb3ff7d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753195"
---
# <a name="itypenamegettypearguments-method"></a><span data-ttu-id="62979-102">Метод ITypeName::GetTypeArguments</span><span class="sxs-lookup"><span data-stu-id="62979-102">ITypeName::GetTypeArguments Method</span></span>
<span data-ttu-id="62979-103">Этот метод поддерживает инфраструктуру .NET Framework и не предназначен для использования непосредственно из программного кода.</span><span class="sxs-lookup"><span data-stu-id="62979-103">This method supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62979-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="62979-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeArguments (  
    [in] DWORD           count,  
    [out] ITypeName**    rgpArguments,  
    [out, retval] DWORD* pCount  
);  
```  
  
## <a name="requirements"></a><span data-ttu-id="62979-105">Требования</span><span class="sxs-lookup"><span data-stu-id="62979-105">Requirements</span></span>  
 <span data-ttu-id="62979-106">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62979-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62979-107">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="62979-107">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="62979-108">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="62979-108">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="62979-109">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62979-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62979-110">См. также</span><span class="sxs-lookup"><span data-stu-id="62979-110">See also</span></span>

- [<span data-ttu-id="62979-111">Интерфейсы размещения</span><span class="sxs-lookup"><span data-stu-id="62979-111">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
