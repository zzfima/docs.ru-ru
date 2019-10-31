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
ms.openlocfilehash: d29576c6f073f1d0e8e0aea417fc38c09a8327c1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73122747"
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="2b672-102">Метод ICorDebugBreakpointEnum::Next</span><span class="sxs-lookup"><span data-stu-id="2b672-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="2b672-103">Возвращает указанное число экземпляров Икордебугбреакпоинт из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="2b672-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b672-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2b672-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b672-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="2b672-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="2b672-106">окне Число извлекаемых экземпляров `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="2b672-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="2b672-107">заполняет Массив указателей, каждый из которых указывает на объект `ICorDebugBreakpoint`, представляющий точку останова.</span><span class="sxs-lookup"><span data-stu-id="2b672-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="2b672-108">заполняет Указатель на число фактически возвращаемых экземпляров `ICorDebugBreakpoint`.</span><span class="sxs-lookup"><span data-stu-id="2b672-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="2b672-109">Это значение может быть равно null, если `celt` является одним.</span><span class="sxs-lookup"><span data-stu-id="2b672-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2b672-110">Требования</span><span class="sxs-lookup"><span data-stu-id="2b672-110">Requirements</span></span>  
 <span data-ttu-id="2b672-111">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b672-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b672-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2b672-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2b672-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b672-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2b672-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b672-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
