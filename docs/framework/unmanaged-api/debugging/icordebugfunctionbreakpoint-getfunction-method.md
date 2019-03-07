---
title: Метод ICorDebugFunctionBreakpoint::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFunctionBreakpoint.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunctionBreakpoint::GetFunction
helpviewer_keywords:
- ICorDebugFunctionBreakpoint::GetFunction method [.NET Framework debugging]
- GetFunction method, ICorDebugFunctionBreakpoint interface [.NET Framework debugging]
ms.assetid: 2a62dae5-dd8a-4696-b817-0e1e586c24a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1da93ea073d6ae9f2e79f251014b2db5282a22c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57496018"
---
# <a name="icordebugfunctionbreakpointgetfunction-method"></a><span data-ttu-id="5e57a-102">Метод ICorDebugFunctionBreakpoint::GetFunction</span><span class="sxs-lookup"><span data-stu-id="5e57a-102">ICorDebugFunctionBreakpoint::GetFunction Method</span></span>
<span data-ttu-id="5e57a-103">Получает указатель на интерфейс ICorDebugFunction, который ссылается на функцию, в которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="5e57a-103">Gets an interface pointer to an ICorDebugFunction that references the function in which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e57a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5e57a-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5e57a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5e57a-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="5e57a-106">[out] Указатель на адрес функции, в которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="5e57a-106">[out] A pointer to the address of the function in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5e57a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="5e57a-107">Requirements</span></span>  
 <span data-ttu-id="5e57a-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e57a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e57a-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5e57a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5e57a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5e57a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5e57a-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e57a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
