---
title: Функция GetIdentityAuthority
ms.date: 03/30/2017
api_name:
- GetIdentityAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetIdentityAuthority
helpviewer_keywords:
- GetIdentityAuthority function [.NET Framework fusion]
ms.assetid: 843cd5ab-d2b7-4ff6-86bd-e68c7a91c098
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3090887d3c670b2784b7b40c7d63832715596c3b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59141522"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="827a6-102">Функция GetIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="827a6-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="827a6-103">Возвращает указатель на [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) экземпляр, который управляет ключами для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="827a6-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="827a6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="827a6-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="827a6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="827a6-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="827a6-106">[out] Возвращенный `IIdentityAuthority` указатель.</span><span class="sxs-lookup"><span data-stu-id="827a6-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="827a6-107">Требования</span><span class="sxs-lookup"><span data-stu-id="827a6-107">Requirements</span></span>  
 <span data-ttu-id="827a6-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="827a6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="827a6-109">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="827a6-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="827a6-110">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="827a6-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="827a6-111">См. также</span><span class="sxs-lookup"><span data-stu-id="827a6-111">See also</span></span>

- [<span data-ttu-id="827a6-112">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="827a6-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)
- [<span data-ttu-id="827a6-113">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="827a6-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
