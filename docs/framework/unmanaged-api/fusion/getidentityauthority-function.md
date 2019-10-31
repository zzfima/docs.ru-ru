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
ms.openlocfilehash: acb80f3cc199d4d9f774cb3898335d26fe44b807
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127148"
---
# <a name="getidentityauthority-function"></a><span data-ttu-id="432e5-102">Функция GetIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="432e5-102">GetIdentityAuthority Function</span></span>
<span data-ttu-id="432e5-103">Возвращает указатель на экземпляр [IIdentityAuthority](iidentityauthority-interface.md) , который управляет ключами для объектов кода.</span><span class="sxs-lookup"><span data-stu-id="432e5-103">Gets a pointer to an [IIdentityAuthority](iidentityauthority-interface.md) instance that manages keys for code objects.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="432e5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="432e5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetIdentityAuthority (  
    [out] IIdentityAuthority   **ppIIdentityAuthority  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="432e5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="432e5-105">Parameters</span></span>  
 `ppIIdentityAuthority`  
 <span data-ttu-id="432e5-106">заполняет Возвращаемый указатель `IIdentityAuthority`.</span><span class="sxs-lookup"><span data-stu-id="432e5-106">[out] The returned `IIdentityAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="432e5-107">Требования</span><span class="sxs-lookup"><span data-stu-id="432e5-107">Requirements</span></span>  
 <span data-ttu-id="432e5-108">**Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="432e5-108">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="432e5-109">**Заголовок:** Изоляция. h</span><span class="sxs-lookup"><span data-stu-id="432e5-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="432e5-110">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="432e5-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="432e5-111">См. также</span><span class="sxs-lookup"><span data-stu-id="432e5-111">See also</span></span>

- [<span data-ttu-id="432e5-112">Интерфейс IIdentityAuthority</span><span class="sxs-lookup"><span data-stu-id="432e5-112">IIdentityAuthority Interface</span></span>](iidentityauthority-interface.md)
- [<span data-ttu-id="432e5-113">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="432e5-113">Fusion Global Static Functions</span></span>](fusion-global-static-functions.md)
