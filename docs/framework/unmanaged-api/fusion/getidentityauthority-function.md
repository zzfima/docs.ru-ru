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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697606"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="bb5cb-102">Функция GetIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="bb5cb-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="bb5cb-103">Возвращает указатель на [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) экземпляр, который управляет ключами для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="bb5cb-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb5cb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb5cb-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb5cb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb5cb-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="bb5cb-106">[out] Возвращенный `IIdentityAuthority` указатель.</span><span class="sxs-lookup"><span data-stu-id="bb5cb-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb5cb-107">Требования</span><span class="sxs-lookup"><span data-stu-id="bb5cb-107">Requirements</span></span>  
 <span data-ttu-id="bb5cb-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb5cb-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb5cb-109">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="bb5cb-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="bb5cb-110">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb5cb-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb5cb-111">См. также</span><span class="sxs-lookup"><span data-stu-id="bb5cb-111">See also</span></span>

- [<span data-ttu-id="bb5cb-112">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="bb5cb-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)
- [<span data-ttu-id="bb5cb-113">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="bb5cb-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
