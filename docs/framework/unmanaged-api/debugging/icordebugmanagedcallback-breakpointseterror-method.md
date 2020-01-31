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
ms.openlocfilehash: 67d4972ee38a54d43b4a096847cc61fa3402b042
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788439"
---
# <a name="icordebugmanagedcallbackbreakpointseterror-method"></a><span data-ttu-id="f3e59-102">Метод ICorDebugManagedCallback::BreakpointSetError</span><span class="sxs-lookup"><span data-stu-id="f3e59-102">ICorDebugManagedCallback::BreakpointSetError Method</span></span>
<span data-ttu-id="f3e59-103">Уведомляет отладчик о том, что среде CLR не удалось точно привязать точку останова, установленную до JIT-компиляции функции.</span><span class="sxs-lookup"><span data-stu-id="f3e59-103">Notifies the debugger that the common language runtime was unable to accurately bind a breakpoint that was set before a function was just-in-time (JIT) compiled.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3e59-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f3e59-104">Syntax</span></span>  
  
```cpp  
HRESULT BreakpointSetError (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint,  
    [in] DWORD                dwError  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3e59-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="f3e59-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f3e59-106">окне Указатель на объект ICorDebugAppDomain, представляющий домен приложения, который содержит несвязанную точку останова.</span><span class="sxs-lookup"><span data-stu-id="f3e59-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the unbound breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="f3e59-107">окне Указатель на объект ICorDebugThread, представляющий поток, содержащий несвязанную точку останова.</span><span class="sxs-lookup"><span data-stu-id="f3e59-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the unbound breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="f3e59-108">окне Указатель на объект Икордебугбреакпоинт, представляющий несвязанную точку останова.</span><span class="sxs-lookup"><span data-stu-id="f3e59-108">[in] A pointer to an ICorDebugBreakpoint object that represents the unbound breakpoint.</span></span>  
  
 `dwError`  
 <span data-ttu-id="f3e59-109">окне Целое число, указывающее на ошибку.</span><span class="sxs-lookup"><span data-stu-id="f3e59-109">[in] An integer that indicates the error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f3e59-110">Заметки</span><span class="sxs-lookup"><span data-stu-id="f3e59-110">Remarks</span></span>  
 <span data-ttu-id="f3e59-111">Заданная точка останова никогда не будет достигнута.</span><span class="sxs-lookup"><span data-stu-id="f3e59-111">The given breakpoint will never be hit.</span></span> <span data-ttu-id="f3e59-112">Отладчик должен деактивироваться и повторно привязывать его.</span><span class="sxs-lookup"><span data-stu-id="f3e59-112">The debugger should deactivate and rebind it.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3e59-113">Требования</span><span class="sxs-lookup"><span data-stu-id="f3e59-113">Requirements</span></span>  
 <span data-ttu-id="f3e59-114">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3e59-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3e59-115">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f3e59-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f3e59-116">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3e59-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3e59-117">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3e59-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3e59-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="f3e59-118">See also</span></span>

- [<span data-ttu-id="f3e59-119">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="f3e59-119">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
