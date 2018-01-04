---
title: "Метод ICorDebugManagedCallback::Breakpoint"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback.Breakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback::Breakpoint
helpviewer_keywords:
- ICorDebugManagedCallback::Breakpoint method [.NET Framework debugging]
- Breakpoint method [.NET Framework debugging]
ms.assetid: 60b279b0-a726-46d2-8c53-76986a007ebb
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d7b0c521f1b2c5a2c258738239696ad48d4e9350
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmanagedcallbackbreakpoint-method"></a><span data-ttu-id="c6d0c-102">Метод ICorDebugManagedCallback::Breakpoint</span><span class="sxs-lookup"><span data-stu-id="c6d0c-102">ICorDebugManagedCallback::Breakpoint Method</span></span>
<span data-ttu-id="c6d0c-103">Уведомляет отладчик о достижении точки останова.</span><span class="sxs-lookup"><span data-stu-id="c6d0c-103">Notifies the debugger when a breakpoint is encountered.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c6d0c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="c6d0c-104">Syntax</span></span>  
  
```  
HRESULT Breakpoint (  
    [in] ICorDebugAppDomain  *pAppDomain,  
    [in] ICorDebugThread     *pThread,  
    [in] ICorDebugBreakpoint *pBreakpoint  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c6d0c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="c6d0c-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="c6d0c-106">[in] Указатель на объект ICorDebugAppDomain, который представляет домен приложения, который содержит точку останова.</span><span class="sxs-lookup"><span data-stu-id="c6d0c-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain that contains the breakpoint.</span></span>  
  
 `pThread`  
 <span data-ttu-id="c6d0c-107">[in] Указатель на объект ICorDebugThread, представляющий поток, который содержит точку останова.</span><span class="sxs-lookup"><span data-stu-id="c6d0c-107">[in] A pointer to an ICorDebugThread object that represents the thread that contains the breakpoint.</span></span>  
  
 `pBreakpoint`  
 <span data-ttu-id="c6d0c-108">[in] Указатель на объект ICorDebugBreakpoint, который представляет точку останова.</span><span class="sxs-lookup"><span data-stu-id="c6d0c-108">[in] A pointer to an ICorDebugBreakpoint object that represents the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c6d0c-109">Требования</span><span class="sxs-lookup"><span data-stu-id="c6d0c-109">Requirements</span></span>  
 <span data-ttu-id="c6d0c-110">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6d0c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6d0c-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="c6d0c-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="c6d0c-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c6d0c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c6d0c-113">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6d0c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d0c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="c6d0c-114">See Also</span></span>  
 [<span data-ttu-id="c6d0c-115">Интерфейс ICorDebugManagedCallback</span><span class="sxs-lookup"><span data-stu-id="c6d0c-115">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
