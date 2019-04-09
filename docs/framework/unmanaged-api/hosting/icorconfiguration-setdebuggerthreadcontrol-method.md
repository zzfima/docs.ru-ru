---
title: Метод ICorConfiguration::SetDebuggerThreadControl
ms.date: 03/30/2017
api_name:
- ICorConfiguration.SetDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- SetDebuggerThreadControl
helpviewer_keywords:
- SetDebuggerThreadControl method [.NET Framework hosting]
- ICorConfiguration::SetDebuggerThreadControl method [.NET Framework hosting]
ms.assetid: 1ded7639-dacb-4db1-961c-d1ceaec01959
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6fc141cbebe08f8d0974788409d5aef0f68d2878
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205125"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="c3039-102">Метод ICorConfiguration::SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="c3039-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="c3039-103">Задает интерфейс обратного вызова, который будет вызывать службы отладки при блокировании и разблокировании общие потоки среды выполнения (CLR) языка для отладки.</span><span class="sxs-lookup"><span data-stu-id="c3039-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3039-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c3039-104">Syntax</span></span>  
  
```  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3039-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c3039-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="c3039-106">[in] Указатель на [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) объект, который уведомляет основное приложение о блокировании и разблокировании потоков службами отладки.</span><span class="sxs-lookup"><span data-stu-id="c3039-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3039-107">Требования</span><span class="sxs-lookup"><span data-stu-id="c3039-107">Requirements</span></span>  
 <span data-ttu-id="c3039-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3039-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3039-109">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="c3039-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="c3039-110">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c3039-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="c3039-111">Версии платформы .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="c3039-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c3039-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c3039-112">See also</span></span>

- [<span data-ttu-id="c3039-113">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="c3039-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
