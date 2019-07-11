---
title: Метод ICorDebugFunctionBreakpoint::GetOffset
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetOffset
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetOffset
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetOffset method [.NET Framework debugging]
- GetOffset method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: e619eae4-3ac3-4c37-bba4-55e59989b9cb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 67e71002a78023ad6e8ef89c7a57d484a65aaeb3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67756379"
---
# <a name="icordebugfunctionbreakpointgetoffset-method"></a><span data-ttu-id="bb1cc-102">Метод ICorDebugFunctionBreakpoint::GetOffset</span><span class="sxs-lookup"><span data-stu-id="bb1cc-102">ICorDebugFunctionBreakpoint::GetOffset Method</span></span>
<span data-ttu-id="bb1cc-103">Получает смещение точки останова в функции.</span><span class="sxs-lookup"><span data-stu-id="bb1cc-103">Gets the offset of the breakpoint within the function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb1cc-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="bb1cc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetOffset (  
    [out] ULONG32  *pnOffset  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bb1cc-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="bb1cc-105">Parameters</span></span>  
 `pnOffset`  
 <span data-ttu-id="bb1cc-106">[out] Указатель на смещение точки останова.</span><span class="sxs-lookup"><span data-stu-id="bb1cc-106">[out] A pointer to the offset of the breakpoint.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb1cc-107">Требования</span><span class="sxs-lookup"><span data-stu-id="bb1cc-107">Requirements</span></span>  
 <span data-ttu-id="bb1cc-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bb1cc-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bb1cc-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bb1cc-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bb1cc-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bb1cc-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bb1cc-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bb1cc-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
