---
title: "Метод ICorDebugBreakpointEnum::Next"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: b81da25a630b034d4ec2f277f738a5337bdbec3e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugbreakpointenumnext-method"></a><span data-ttu-id="a406e-102">Метод ICorDebugBreakpointEnum::Next</span><span class="sxs-lookup"><span data-stu-id="a406e-102">ICorDebugBreakpointEnum::Next Method</span></span>
<span data-ttu-id="a406e-103">Получает заданное число экземпляров ICorDebugBreakpoint из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="a406e-103">Gets the specified number of ICorDebugBreakpoint instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a406e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a406e-104">Syntax</span></span>  
  
```  
HRESULT Next (  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugBreakpoint *breakpoints[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="a406e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a406e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="a406e-106">[in] Количество `ICorDebugBreakpoint` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="a406e-106">[in] The number of `ICorDebugBreakpoint` instances to be retrieved.</span></span>  
  
 `breakpoints`  
 <span data-ttu-id="a406e-107">[out] Массив указателей, каждый из которых указывает на `ICorDebugBreakpoint` объект, который представляет точку останова.</span><span class="sxs-lookup"><span data-stu-id="a406e-107">[out] An array of pointers, each of which points to an `ICorDebugBreakpoint` object that represents a breakpoint.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="a406e-108">[out] Указатель на число `ICorDebugBreakpoint` фактически возвращаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="a406e-108">[out] A pointer to the number of `ICorDebugBreakpoint` instances actually returned.</span></span> <span data-ttu-id="a406e-109">Это значение может быть значение null, если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="a406e-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a406e-110">Требования</span><span class="sxs-lookup"><span data-stu-id="a406e-110">Requirements</span></span>  
 <span data-ttu-id="a406e-111">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a406e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a406e-112">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a406e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a406e-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a406e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a406e-114">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a406e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
