---
title: Метод IDebuggerThreadControl::StartBlockingForDebugger
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl.StartBlockingForDebugger
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StartBlockingForDebugger
helpviewer_keywords:
- IDebuggerThreadControl::StartBlockingForDebugger method [.NET Framework hosting]
- StartBlockingForDebugger method [.NET Framework hosting]
ms.assetid: 5c8f11b4-35d3-4c39-9bbd-58b896ba5ba6
topic_type:
- apiref
ms.openlocfilehash: 72f7bee79e74c69acff90861ceada8a91afe2157
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134915"
---
# <a name="idebuggerthreadcontrolstartblockingfordebugger-method"></a><span data-ttu-id="df1ba-102">Метод IDebuggerThreadControl::StartBlockingForDebugger</span><span class="sxs-lookup"><span data-stu-id="df1ba-102">IDebuggerThreadControl::StartBlockingForDebugger Method</span></span>
<span data-ttu-id="df1ba-103">Уведомляет узел о том, что служба отладки собирается начать блокирование всех потоков.</span><span class="sxs-lookup"><span data-stu-id="df1ba-103">Notifies the host that the debugging services are about to start blocking all threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df1ba-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="df1ba-104">Syntax</span></span>  
  
```cpp  
HRESULT StartBlockingForDebugger (  
    [in] DWORD dwUnused  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="df1ba-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="df1ba-105">Parameters</span></span>  
 `dwUnused`  
 <span data-ttu-id="df1ba-106">окне Зарезервировано для будущего использования.</span><span class="sxs-lookup"><span data-stu-id="df1ba-106">[in] Reserved for future use.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df1ba-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="df1ba-107">Remarks</span></span>  
 <span data-ttu-id="df1ba-108">Метод `StartBlockingForDebugger` может быть вызван в потоке среды выполнения.</span><span class="sxs-lookup"><span data-stu-id="df1ba-108">The `StartBlockingForDebugger` method could be called on a runtime thread.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="df1ba-109">Требования</span><span class="sxs-lookup"><span data-stu-id="df1ba-109">Requirements</span></span>  
 <span data-ttu-id="df1ba-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="df1ba-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="df1ba-111">**Заголовок:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="df1ba-111">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="df1ba-112">**Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="df1ba-112">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="df1ba-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="df1ba-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df1ba-114">См. также</span><span class="sxs-lookup"><span data-stu-id="df1ba-114">See also</span></span>

- [<span data-ttu-id="df1ba-115">Интерфейс IDebuggerThreadControl</span><span class="sxs-lookup"><span data-stu-id="df1ba-115">IDebuggerThreadControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-interface.md)
