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
ms.openlocfilehash: 0f6a369691ab2e4e9fd2e5d9731fb1dc0a42ba11
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127797"
---
# <a name="icorconfigurationsetdebuggerthreadcontrol-method"></a><span data-ttu-id="8be46-102">Метод ICorConfiguration::SetDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="8be46-102">ICorConfiguration::SetDebuggerThreadControl Method</span></span>
<span data-ttu-id="8be46-103">Задает интерфейс обратного вызова, который службы отладки будут вызывать, так как потоки среды CLR блокируются и разблокируются для отладки.</span><span class="sxs-lookup"><span data-stu-id="8be46-103">Sets the callback interface that the debugging services will call as common language runtime (CLR) threads are blocked and unblocked for debugging.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8be46-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="8be46-104">Syntax</span></span>  
  
```cpp  
HRESULT SetDebuggerThreadControl (  
    [in] IDebuggerThreadControl* pDebuggerThreadControl  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8be46-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="8be46-105">Parameters</span></span>  
 `pDebuggerThreadControl`  
 <span data-ttu-id="8be46-106">окне Указатель на объект [идебугжерсреадконтрол](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) , который уведомляет узел о блокировании и разблокировке потоков службами отладки.</span><span class="sxs-lookup"><span data-stu-id="8be46-106">[in] A pointer to an [IDebuggerThreadControl](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md) object that notifies the host about the blocking and unblocking of threads by the debugging services.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8be46-107">Требования</span><span class="sxs-lookup"><span data-stu-id="8be46-107">Requirements</span></span>  
 <span data-ttu-id="8be46-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8be46-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8be46-109">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8be46-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8be46-110">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="8be46-110">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8be46-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8be46-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8be46-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8be46-112">See also</span></span>

- [<span data-ttu-id="8be46-113">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="8be46-113">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
