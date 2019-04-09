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
ms.openlocfilehash: 7613bc744ad4c2e172fc4f6dd7bf282fb3d9072c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59179755"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="28c5f-102">Метод IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="28c5f-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="28c5f-103">Уведомляет основное приложение, то, что среда выполнения начала приостановку потока для сборки мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="28c5f-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28c5f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="28c5f-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="28c5f-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="28c5f-105">Remarks</span></span>  
 <span data-ttu-id="28c5f-106">Не повторного планирования во время обсуждения `SuspensionStarting` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="28c5f-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="28c5f-107">Требования</span><span class="sxs-lookup"><span data-stu-id="28c5f-107">Requirements</span></span>  
 <span data-ttu-id="28c5f-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="28c5f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="28c5f-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="28c5f-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="28c5f-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="28c5f-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="28c5f-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="28c5f-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="28c5f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="28c5f-112">See also</span></span>

- [<span data-ttu-id="28c5f-113">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="28c5f-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
