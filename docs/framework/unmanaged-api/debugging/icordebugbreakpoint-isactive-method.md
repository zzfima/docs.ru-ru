---
title: Метод ICorDebugBreakpoint::IsActive
ms.date: 03/30/2017
api_name:
- ICorDebugBreakpoint.IsActive
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugBreakpoint::IsActive
helpviewer_keywords:
- ICorDebugBreakpoint::IsActive method [.NET Framework debugging]
- IsActive method, ICorDebugBreakpoint interface [.NET Framework debugging]
ms.assetid: 06e583d6-d88a-4ff5-bb95-5c48618a461c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6d78208c180638e9048ae39664b8ce8f57be90da
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67745170"
---
# <a name="icordebugbreakpointisactive-method"></a><span data-ttu-id="91c5a-102">Метод ICorDebugBreakpoint::IsActive</span><span class="sxs-lookup"><span data-stu-id="91c5a-102">ICorDebugBreakpoint::IsActive Method</span></span>
<span data-ttu-id="91c5a-103">Получает значение, указывающее, является ли это `ICorDebugBreakpoint` активен.</span><span class="sxs-lookup"><span data-stu-id="91c5a-103">Gets a value that indicates whether this `ICorDebugBreakpoint` is active.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91c5a-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="91c5a-104">Syntax</span></span>  
  
```cpp  
HRESULT IsActive (  
    [out] BOOL *pbActive  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91c5a-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="91c5a-105">Parameters</span></span>  
 `pbActive`  
 <span data-ttu-id="91c5a-106">[out] `true` в противном случае — active, в противном случае — `false`.</span><span class="sxs-lookup"><span data-stu-id="91c5a-106">[out] `true` if this breakpoint is active; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91c5a-107">Требования</span><span class="sxs-lookup"><span data-stu-id="91c5a-107">Requirements</span></span>  
 <span data-ttu-id="91c5a-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91c5a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91c5a-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="91c5a-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="91c5a-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91c5a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91c5a-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91c5a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
