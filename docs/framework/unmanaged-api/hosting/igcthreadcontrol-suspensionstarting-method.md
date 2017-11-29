---
title: "Метод IGCThreadControl::SuspensionStarting"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCThreadControl.SuspensionStarting
api_location: mscoree.dll
api_type: COM
f1_keywords: SuspensionStarting
helpviewer_keywords:
- IGCThreadControl::SuspensionStarting method [.NET Framework hosting]
- SuspensionStarting method, IGCThreadControl interface [.NET Framework hosting]
ms.assetid: 0af312af-98e9-415e-b182-42e80a1aee51
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d9d5f403c2880d0079a89c6de5c2ad9aa4f8d9fa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="igcthreadcontrolsuspensionstarting-method"></a><span data-ttu-id="af86c-102">Метод IGCThreadControl::SuspensionStarting</span><span class="sxs-lookup"><span data-stu-id="af86c-102">IGCThreadControl::SuspensionStarting Method</span></span>
<span data-ttu-id="af86c-103">Уведомляет узел, что среда выполнения начинает приостановку потока для сборки мусора или по другим причинам.</span><span class="sxs-lookup"><span data-stu-id="af86c-103">Notifies the host that the runtime is beginning a thread suspension for a garbage collection or other suspension.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af86c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="af86c-104">Syntax</span></span>  
  
```  
HRESULT SuspensionStarting ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="af86c-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="af86c-105">Remarks</span></span>  
 <span data-ttu-id="af86c-106">Не следует перепланировать каких-либо потоков во время `SuspensionStarting` обратного вызова.</span><span class="sxs-lookup"><span data-stu-id="af86c-106">Do not reschedule any threads during the `SuspensionStarting` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af86c-107">Требования</span><span class="sxs-lookup"><span data-stu-id="af86c-107">Requirements</span></span>  
 <span data-ttu-id="af86c-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="af86c-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af86c-109">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="af86c-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="af86c-110">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="af86c-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="af86c-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af86c-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af86c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="af86c-112">See Also</span></span>  
 [<span data-ttu-id="af86c-113">Igcthreadcontrol-интерфейс</span><span class="sxs-lookup"><span data-stu-id="af86c-113">IGCThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/igcthreadcontrol-interface.md)
