---
title: Метод ICorDebugBreakpointEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpointEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpointEnum::Next
helpviewer_keywords:
- Next method, ICorDebugBreakpointEnum interface [.NET Framework debugging]
- ICorDebugBreakpointEnum::Next method [.NET Framework debugging]
ms.assetid: 2e6bbaea-79ba-448c-a0e3-7c90fc7c2939
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 18b65eb3e733fa7970e4c0e7de09755598eaf149
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57474986"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="9c9c0-102">Метод ICorDebugBreakpointEnum::Next</span><span class="sxs-lookup"><span data-stu-id="9c9c0-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="9c9c0-103">Получает указанное число экземпляров ICorDebugBreakpoint из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="9c9c0-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9c9c0-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9c9c0-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9c9c0-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="9c9c0-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="9c9c0-106">[in] Количество `ICorDebugBreakpoint` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="9c9c0-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="9c9c0-107">[out] Массив указателей, каждый из которых указывает `ICorDebugBreakpoint` , представляющий точку останова.</span><span class="sxs-lookup"><span data-stu-id="9c9c0-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9c9c0-108">[out] Указатель на число `ICorDebugBreakpoint` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="9c9c0-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="9c9c0-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="9c9c0-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9c9c0-110">Требования</span><span class="sxs-lookup"><span data-stu-id="9c9c0-110">Requirements</span></span>  
 <span data-ttu-id="9c9c0-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9c9c0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9c9c0-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9c9c0-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9c9c0-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9c9c0-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9c9c0-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9c9c0-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
