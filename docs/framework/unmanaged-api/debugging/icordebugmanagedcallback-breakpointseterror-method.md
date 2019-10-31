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
ms.openlocfilehash: dae04e1809c1bb3260461086a4953b8b4e5cce52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122574"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="fde44-102">Метод ICorDebugManagedCallback::BreakpointSetError</span><span class="sxs-lookup"><span data-stu-id="fde44-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="fde44-103">Уведомляет отладчик о том, что среде CLR не удалось точно привязать точку останова, установленную до JIT-компиляции функции.</span><span class="sxs-lookup"><span data-stu-id="fde44-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fde44-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="fde44-104">Syntax</span></span>  
  
```cpp  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fde44-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="fde44-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="fde44-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который содержит несвязанную точку останова.</span><span class="sxs-lookup"><span data-stu-id="fde44-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="fde44-107">окне Указатель на объект ICorDebugThread, представляющий поток, содержащий несвязанную точку останова.</span><span class="sxs-lookup"><span data-stu-id="fde44-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="fde44-108">окне Указатель на объект Икордебугбреакпоинт, представляющий несвязанную точку останова.</span><span class="sxs-lookup"><span data-stu-id="fde44-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="fde44-109">окне Целое число, указывающее на ошибку.</span><span class="sxs-lookup"><span data-stu-id="fde44-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fde44-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="fde44-110">Remarks</span></span>  
 <span data-ttu-id="fde44-111">Заданная точка останова никогда не будет достигнута.</span><span class="sxs-lookup"><span data-stu-id="fde44-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="fde44-112">Отладчик должен деактивироваться и повторно привязывать его.</span><span class="sxs-lookup"><span data-stu-id="fde44-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fde44-113">Требования</span><span class="sxs-lookup"><span data-stu-id="fde44-113">Requirements</span></span>  
 <span data-ttu-id="fde44-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fde44-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fde44-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fde44-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fde44-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fde44-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fde44-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fde44-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fde44-118">См. также</span><span class="sxs-lookup"><span data-stu-id="fde44-118">See also</span></span>

- [<span data-ttu-id="fde44-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="fde44-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
