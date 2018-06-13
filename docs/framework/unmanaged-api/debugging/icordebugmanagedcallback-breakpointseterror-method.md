---
title: Метод ICorDebugManagedCallback::BreakpointSetError
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.BreakpointSetError
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::BreakpointSetError
helpviewer_keywords:
- BreakpointSetError method [.NET Framework debugging]
- ICorDebugManagedCallback::BreakpointSetError method [.NET Framework debugging]
ms.assetid: f2b773a4-c4d0-429c-9717-51d6e2ed86af
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cc437f63621c451c0af796513d4646fe0668c00
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33418384"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="5ead3-102">Метод ICorDebugManagedCallback::BreakpointSetError</span><span class="sxs-lookup"><span data-stu-id="5ead3-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="5ead3-103">Уведомляет отладчик, общеязыковая среда выполнения не удалось точно привязать точку останова, который был установлен до функции just-in-time (JIT) компиляции.</span><span class="sxs-lookup"><span data-stu-id="5ead3-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ead3-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5ead3-104">Syntax</span></span>  
  
```  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ead3-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5ead3-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="5ead3-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, который содержит несвязанные точку останова.</span><span class="sxs-lookup"><span data-stu-id="5ead3-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="5ead3-107">[in] Указатель на объект ICorDebugThread, представляющий поток, который содержит несвязанные точку останова.</span><span class="sxs-lookup"><span data-stu-id="5ead3-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="5ead3-108">[in] Указатель на объект ICorDebugBreakpoint, представляющий непривязанные точки останова.</span><span class="sxs-lookup"><span data-stu-id="5ead3-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="5ead3-109">[in] Целое число, указывающее на ошибку.</span><span class="sxs-lookup"><span data-stu-id="5ead3-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ead3-110">Примечания</span><span class="sxs-lookup"><span data-stu-id="5ead3-110">Remarks</span></span>  
 <span data-ttu-id="5ead3-111">Данной точки останова, никогда не сработает.</span><span class="sxs-lookup"><span data-stu-id="5ead3-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="5ead3-112">Отладчик должен отключить и повторно привязать его.</span><span class="sxs-lookup"><span data-stu-id="5ead3-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ead3-113">Требования</span><span class="sxs-lookup"><span data-stu-id="5ead3-113">Requirements</span></span>  
 <span data-ttu-id="5ead3-114">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ead3-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ead3-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ead3-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ead3-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ead3-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ead3-117">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ead3-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ead3-118">См. также</span><span class="sxs-lookup"><span data-stu-id="5ead3-118">See Also</span></span>  
 [<span data-ttu-id="5ead3-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="5ead3-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
