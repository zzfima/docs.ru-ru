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
ms.openlocfilehash: 0f056e4ae233e70223755c1961cd3ee5da68ec90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745176"
---
# <a name="icordebugbreakpointactivate-method"></a><span data-ttu-id="45c50-102">Метод ICorDebugBreakpoint::Activate</span><span class="sxs-lookup"><span data-stu-id="45c50-102">ICorDebugBreakpoint::Activate Method</span></span>
<span data-ttu-id="45c50-103">Задает активное состояние `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="45c50-103">Sets the active state of this `ICorDebugBreakpoint`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="45c50-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="45c50-104">Syntax</span></span>  
  
```cpp  
HRESULT Activate (  
    [in] BOOL bActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="45c50-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="45c50-105">Parameters</span></span>  
 `bActive`  
 <span data-ttu-id="45c50-106">[in] Это значение равно `true` для указания состояния как активный; в противном случае это значение равно `false`.</span><span class="sxs-lookup"><span data-stu-id="45c50-106">[in] Set this value to `true` to specify the state as active; otherwise, set this value to `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="45c50-107">Требования</span><span class="sxs-lookup"><span data-stu-id="45c50-107">Requirements</span></span>  
 <span data-ttu-id="45c50-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45c50-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="45c50-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="45c50-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="45c50-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="45c50-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="45c50-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45c50-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
