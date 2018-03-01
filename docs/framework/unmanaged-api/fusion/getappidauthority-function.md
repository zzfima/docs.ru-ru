---
title: "Функция GetAppIdAuthority"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- GetAppIdAuthority
api_location:
- fusion.dll
- clr.dll
api_type:
- COM
f1_keywords:
- GetAppIdAuthority
helpviewer_keywords:
- GetAppIdAuthority function [.NET Framework fusion]
ms.assetid: 9f968dad-0d09-47fb-bebc-94c39a0d16ad
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 0e89624feb04050534b917b865d5cb53b8c4cf58
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="getappidauthority-function"></a><span data-ttu-id="9d352-102">Функция GetAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="9d352-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="9d352-103">Возвращает указатель на [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) экземпляр, который управляет ключами для идентификаторов и ссылок приложения.</span><span class="sxs-lookup"><span data-stu-id="9d352-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d352-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9d352-104">Syntax</span></span>  
  
```  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d352-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9d352-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="9d352-106">[out] Возвращенный `IAppIdAuthority` указателя.</span><span class="sxs-lookup"><span data-stu-id="9d352-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d352-107">Требования</span><span class="sxs-lookup"><span data-stu-id="9d352-107">Requirements</span></span>  
 <span data-ttu-id="9d352-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d352-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d352-109">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="9d352-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="9d352-110">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d352-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d352-111">См. также</span><span class="sxs-lookup"><span data-stu-id="9d352-111">See Also</span></span>  
 [<span data-ttu-id="9d352-112">Интерфейс IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="9d352-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 [<span data-ttu-id="9d352-113">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="9d352-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
