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
ms.openlocfilehash: 95cbda3729c02b95557f9f700f1ea7c68aa450a1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438019"
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="3e9b6-102">Метод IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="3e9b6-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="3e9b6-103">Уведомляет узел, что среда выполнения начинает приостановку потока для сборки мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="3e9b6-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e9b6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3e9b6-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="3e9b6-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="3e9b6-105">Remarks</span></span>  
 <span data-ttu-id="3e9b6-106">Не следует перепланировать каких-либо потоков во время `SuspensionStarting` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="3e9b6-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3e9b6-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3e9b6-107">Requirements</span></span>  
 <span data-ttu-id="3e9b6-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e9b6-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e9b6-109">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="3e9b6-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3e9b6-110">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3e9b6-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3e9b6-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e9b6-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e9b6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3e9b6-112">See Also</span></span>  
 [<span data-ttu-id="3e9b6-113">Интерфейс IGCThreadControl</span><span class="sxs-lookup"><span data-stu-id="3e9b6-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
