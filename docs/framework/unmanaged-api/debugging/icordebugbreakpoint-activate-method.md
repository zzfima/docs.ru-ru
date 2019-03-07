---
title: Метод ICorDebugBreakpoint::Activate
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.Activate
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::Activate
helpviewer_keywords:
- ICorDebugBreakpoint::Activate method [.NET Framework debugging]
- Activate method [.NET Framework debugging]
ms.assetid: e30c29f7-3f19-4081-b572-a731aa14cd44
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2ac37df58762dac4e3a6161361cafd8ea87e2657
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57491364"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="32e4d-102">Метод ICorDebugBreakpoint::Activate</span><span class="sxs-lookup"><span data-stu-id="32e4d-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="32e4d-103">Задает активное состояние `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="32e4d-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32e4d-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="32e4d-104">Syntax</span></span>  
  
```  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="32e4d-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="32e4d-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="32e4d-106">[in] Это значение равно `true` для указания состояния как активный; в противном случае это значение равно `false`.</span><span class="sxs-lookup"><span data-stu-id="32e4d-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="32e4d-107">Требования</span><span class="sxs-lookup"><span data-stu-id="32e4d-107">Requirements</span></span>  
 <span data-ttu-id="32e4d-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="32e4d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="32e4d-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="32e4d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="32e4d-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="32e4d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="32e4d-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="32e4d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
