---
title: "Метод IDebuggerThreadControl::ThreadIsBlockingForDebugger"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDebuggerThreadControl.ThreadIsBlockingForDebugger
api_location: mscoree.dll
api_type: COM
f1_keywords: ThreadIsBlockingForDebugger
helpviewer_keywords:
- ThreadIsBlockingForDebugger method [.NET Framework hosting]
- IDebuggerThreadControl::ThreadIsBlockingForDebugger method [.NET Framework hosting]
ms.assetid: d4d7cb2d-69da-48b3-879a-1a8a68c9bfa8
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5b14818f06fec78cfc2cff9ea66548c9ee87bb4a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="idebuggerthreadcontrolthreadisblockingfordebugger-method"></a><span data-ttu-id="4b99b-102">Метод IDebuggerThreadControl::ThreadIsBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="4b99b-102">IDebuggerThreadControl::ThreadIsBlockingForDebugger Method</span></span>
<span data-ttu-id="4b99b-103">Уведомляет узел, что поток, передающий данный обратный вызов о блок в службах отладки.</span><span class="sxs-lookup"><span data-stu-id="4b99b-103">Notifies the host that the thread that is sending this callback is about to block within the debugging services.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b99b-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="4b99b-104">Syntax</span></span>  
  
```  
HRESULT ThreadIsBlockingForDebugger ( );  
```  
  
## <a name="remarks"></a><span data-ttu-id="4b99b-105">Примечания</span><span class="sxs-lookup"><span data-stu-id="4b99b-105">Remarks</span></span>  
 <span data-ttu-id="4b99b-106">`ThreadIsBlockingForDebugger` Метод всегда будет вызываться в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="4b99b-106">The `ThreadIsBlockingForDebugger` method will always be called on a runtime thread.</span></span>  
  
 <span data-ttu-id="4b99b-107">`ThreadIsBlockingForDebugger` Метод дает узлу возможность выполнения другого действия, когда поток блокируется.</span><span class="sxs-lookup"><span data-stu-id="4b99b-107">The `ThreadIsBlockingForDebugger` method gives the host an opportunity to perform another action while the thread blocks.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b99b-108">Требования</span><span class="sxs-lookup"><span data-stu-id="4b99b-108">Requirements</span></span>  
 <span data-ttu-id="4b99b-109">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b99b-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b99b-110">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4b99b-110">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4b99b-111">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b99b-111">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4b99b-112">**Версии платформы .NET Framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b99b-112">**NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b99b-113">См. также</span><span class="sxs-lookup"><span data-stu-id="4b99b-113">See Also</span></span>  
 [<span data-ttu-id="4b99b-114">Idebuggerthreadcontrol-интерфейс</span><span class="sxs-lookup"><span data-stu-id="4b99b-114">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
