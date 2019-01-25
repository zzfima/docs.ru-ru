---
title: Метод IGCThreadControl::SuspensionStarting
ms.date: 03/30/2017
api_name:
- IGCThreadControl.SuspensionStarting
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ff0c95ea79978c0b58057ec06fea231f5632c941
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54702656"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="ad568-102">Метод IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="ad568-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="ad568-103">Уведомляет основное приложение, то, что среда выполнения начала приостановку потока для сборки мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="ad568-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad568-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ad568-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="ad568-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="ad568-105">Remarks</span></span>  
 <span data-ttu-id="ad568-106">Не повторного планирования во время обсуждения `SuspensionStarting` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="ad568-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad568-107">Требования</span><span class="sxs-lookup"><span data-stu-id="ad568-107">Requirements</span></span>  
 <span data-ttu-id="ad568-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad568-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad568-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ad568-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ad568-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ad568-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ad568-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad568-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad568-112">См. также</span><span class="sxs-lookup"><span data-stu-id="ad568-112">See also</span></span>
- [<span data-ttu-id="ad568-113">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="ad568-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
