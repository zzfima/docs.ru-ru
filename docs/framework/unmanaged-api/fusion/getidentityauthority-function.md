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
ms.openlocfilehash: 1194ae12710ce9ef6d5f53e584493eec0541f3fd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54569720"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="b0257-102">Функция GetIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="b0257-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="b0257-103">Возвращает указатель на [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) экземпляр, который управляет ключами для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="b0257-103">Gets a pointer to an [IIdentityAuthority](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b0257-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b0257-104">Syntax</span></span>  
  
```  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b0257-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b0257-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="b0257-106">[out] Возвращенный `IIdentityAuthority` указатель.</span><span class="sxs-lookup"><span data-stu-id="b0257-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b0257-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b0257-107">Requirements</span></span>  
 <span data-ttu-id="b0257-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b0257-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b0257-109">**Заголовок.** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="b0257-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="b0257-110">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b0257-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b0257-111">См. также</span><span class="sxs-lookup"><span data-stu-id="b0257-111">See also</span></span>
- [<span data-ttu-id="b0257-112">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="b0257-112">IIdentityAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iidentityauthority-interface.md)
- [<span data-ttu-id="b0257-113">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="b0257-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
