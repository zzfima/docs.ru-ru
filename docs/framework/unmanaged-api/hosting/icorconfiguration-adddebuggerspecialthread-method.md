---
title: Метод ICorConfiguration::AddDebuggerSpecialThread
ms.date: 03/30/2017
api_name:
- ICorConfiguration.AddDebuggerSpecialThread
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- AddDebuggerSpecialThread
helpviewer_keywords:
- AddDebuggerSpecialThread method [.NET Framework hosting]
- ICorConfiguration::AddDebuggerSpecialThread method [.NET Framework hosting]
ms.assetid: 1f1e3239-438e-4be9-a3bb-7d0722d3a76d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db1b19c1499f7e8a126933b4d0635a0ab73e72a8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763286"
---
# <a name="icorconfigurationadddebuggerspecialthread-method"></a><span data-ttu-id="20f51-102">Метод ICorConfiguration::AddDebuggerSpecialThread</span><span class="sxs-lookup"><span data-stu-id="20f51-102">ICorConfiguration::AddDebuggerSpecialThread Method</span></span>
<span data-ttu-id="20f51-103">Указывает службы отладки, что определенным потоком должны продолжить выполнение при завершении работы приложения во время сценариев отладки управляемого или неуправляемого отладчика.</span><span class="sxs-lookup"><span data-stu-id="20f51-103">Indicates to the debugging services that a particular thread should be allowed to continue executing while the debugger has an application stopped during managed or unmanaged debugging scenarios.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20f51-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="20f51-104">Syntax</span></span>  
  
```  
HRESULT AddDebuggerSpecialThread (  
    [in] DWORD dwSpecialThreadId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20f51-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="20f51-105">Parameters</span></span>  
 `dwSpecialThreadId`  
 <span data-ttu-id="20f51-106">[in] Идентификатор потока, должны продолжать выполнение.</span><span class="sxs-lookup"><span data-stu-id="20f51-106">[in] The ID of the thread that should be allowed to continue executing.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20f51-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="20f51-107">Remarks</span></span>  
 <span data-ttu-id="20f51-108">Указанный поток не разрешено выполнять управляемый код, или введите среды выполнения любым способом.</span><span class="sxs-lookup"><span data-stu-id="20f51-108">The specified thread will not be allowed to run managed code or enter the runtime in any way.</span></span> <span data-ttu-id="20f51-109">Примером такой поток будет поток в процессе, для поддержки сценариев прежних версий отладчики.</span><span class="sxs-lookup"><span data-stu-id="20f51-109">An example of such a thread would be an in-process thread to support legacy script debuggers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20f51-110">Требования</span><span class="sxs-lookup"><span data-stu-id="20f51-110">Requirements</span></span>  
 <span data-ttu-id="20f51-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="20f51-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20f51-112">**Заголовок.** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="20f51-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="20f51-113">**Библиотека:** Включена как ресурс в MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="20f51-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="20f51-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20f51-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20f51-115">См. также</span><span class="sxs-lookup"><span data-stu-id="20f51-115">See also</span></span>

- [<span data-ttu-id="20f51-116">Интерфейс ICorConfiguration</span><span class="sxs-lookup"><span data-stu-id="20f51-116">ICorConfiguration Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorconfiguration-interface.md)
