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
ms.openlocfilehash: 2501461267ff7369cd9c48f4cef6cda42063a48b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="549bb-102">Метод ICorConfiguration::AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="549bb-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="549bb-103">Указывает службы отладки, в определенном потоке, что следует разрешить продолжить выполнение при завершении работы приложения во время отладки сценариев управляемого или неуправляемого отладчика.</span><span class="sxs-lookup"><span data-stu-id="549bb-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="549bb-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="549bb-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="549bb-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="549bb-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="549bb-106">[in] Идентификатор потока, должны продолжать выполнение.</span><span class="sxs-lookup"><span data-stu-id="549bb-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="549bb-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="549bb-107">Remarks</span></span>  
 <span data-ttu-id="549bb-108">Указанный поток не может выполнить управляемый код или вход в среду выполнения каким-либо образом.</span><span class="sxs-lookup"><span data-stu-id="549bb-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="549bb-109">Примером такого потока может служить поток в процессе, для поддержки сценариев прежних версий отладчики.</span><span class="sxs-lookup"><span data-stu-id="549bb-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="549bb-110">Требования</span><span class="sxs-lookup"><span data-stu-id="549bb-110">Requirements</span></span>  
 <span data-ttu-id="549bb-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="549bb-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="549bb-112">**Заголовок:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="549bb-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="549bb-113">**Библиотека:** включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="549bb-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="549bb-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="549bb-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="549bb-115">См. также</span><span class="sxs-lookup"><span data-stu-id="549bb-115">See Also</span></span>  
 [<span data-ttu-id="549bb-116">Icorconfiguration-интерфейс</span><span class="sxs-lookup"><span data-stu-id="549bb-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
