---
title: Метод ICorDebugManagedCallback::Breakpoint
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.Breakpoint
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4f49fac3951c130c3cf06b6861beb06b89c27dfb
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67759891"
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="dd270-102">Метод ICorDebugManagedCallback::Breakpoint</span><span class="sxs-lookup"><span data-stu-id="dd270-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="dd270-103">Уведомляет отладчик о достижении точки останова.</span><span class="sxs-lookup"><span data-stu-id="dd270-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dd270-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dd270-104">Syntax</span></span>  
  
```cpp  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dd270-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="dd270-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="dd270-106">[in] Указатель на объект ICorDebugAppDomain, представляющий домен приложения, содержащего точку останова.</span><span class="sxs-lookup"><span data-stu-id="dd270-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="dd270-107">[in] Указатель на объект ICorDebugThread, представляющий поток, который содержит точку останова.</span><span class="sxs-lookup"><span data-stu-id="dd270-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="dd270-108">[in] Указатель на объект ICorDebugBreakpoint, представляющий точку останова.</span><span class="sxs-lookup"><span data-stu-id="dd270-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dd270-109">Требования</span><span class="sxs-lookup"><span data-stu-id="dd270-109">Requirements</span></span>  
 <span data-ttu-id="dd270-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dd270-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dd270-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="dd270-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="dd270-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="dd270-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="dd270-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dd270-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd270-114">См. также</span><span class="sxs-lookup"><span data-stu-id="dd270-114">See also</span></span>

- [<span data-ttu-id="dd270-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="dd270-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
