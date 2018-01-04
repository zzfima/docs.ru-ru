---
title: "Метод ICorConfiguration::AddDebuggerSpecialThread"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorConfiguration.AddDebuggerSpecialThread
api_location: mscoree.dll
api_type: COM
f1_keywords: AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b2041a45cb80a08b2322f23e820f89b4bb71f845
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="e2a4d-102">Метод ICorConfiguration::AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="e2a4d-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="e2a4d-103">Указывает службы отладки, в определенном потоке, что следует разрешить продолжить выполнение при завершении работы приложения во время отладки сценариев управляемого или неуправляемого отладчика.</span><span class="sxs-lookup"><span data-stu-id="e2a4d-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2a4d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e2a4d-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2a4d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e2a4d-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="e2a4d-106">[in] Идентификатор потока, должны продолжать выполнение.</span><span class="sxs-lookup"><span data-stu-id="e2a4d-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2a4d-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="e2a4d-107">Remarks</span></span>  
 <span data-ttu-id="e2a4d-108">Указанный поток не может выполнить управляемый код или вход в среду выполнения каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="e2a4d-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="e2a4d-109">Примером такого потока может служить поток в процессе, для поддержки сценариев прежних версий отладчики.</span><span class="sxs-lookup"><span data-stu-id="e2a4d-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2a4d-110">Требования</span><span class="sxs-lookup"><span data-stu-id="e2a4d-110">Requirements</span></span>  
 <span data-ttu-id="e2a4d-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2a4d-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2a4d-112">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e2a4d-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e2a4d-113">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2a4d-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2a4d-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2a4d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2a4d-115">См. также</span><span class="sxs-lookup"><span data-stu-id="e2a4d-115">See Also</span></span>  
 [<span data-ttu-id="e2a4d-116">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="e2a4d-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
