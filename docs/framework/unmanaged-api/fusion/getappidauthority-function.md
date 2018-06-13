---
title: Функция GetAppIdAuthority
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 419884cfd4cbcbcdaa999c221b56ee9873a90241
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429112"
---
# <a name="getappidauthority-function"></a><span data-ttu-id="c09bf-102">Функция GetAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="c09bf-102">GetAppIdAuthority Function</span></span>
<span data-ttu-id="c09bf-103">Возвращает указатель на [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) экземпляр, который управляет ключами для идентификаторов и ссылок приложения.</span><span class="sxs-lookup"><span data-stu-id="c09bf-103">Gets a pointer to an [IAppIdAuthority](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md) instance that manages keys for application identities and references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c09bf-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c09bf-104">Syntax</span></span>  
  
```  
HRESULT GetAppIdAuthority (  
    [out] IAppIdAuthority **ppIAppIdAuthority  
 );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c09bf-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c09bf-105">Parameters</span></span>  
 `ppIAppIdAuthority`  
 <span data-ttu-id="c09bf-106">[out] Возвращенный `IAppIdAuthority` указателя.</span><span class="sxs-lookup"><span data-stu-id="c09bf-106">[out] The returned `IAppIdAuthority` pointer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c09bf-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c09bf-107">Requirements</span></span>  
 <span data-ttu-id="c09bf-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c09bf-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c09bf-109">**Заголовок:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="c09bf-109">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c09bf-110">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c09bf-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c09bf-111">См. также</span><span class="sxs-lookup"><span data-stu-id="c09bf-111">See Also</span></span>  
 [<span data-ttu-id="c09bf-112">Интерфейс IAppIdAuthority</span><span class="sxs-lookup"><span data-stu-id="c09bf-112">IAppIdAuthority Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iappidauthority-interface.md)  
 [<span data-ttu-id="c09bf-113">Глобальные статические функции Fusion</span><span class="sxs-lookup"><span data-stu-id="c09bf-113">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
