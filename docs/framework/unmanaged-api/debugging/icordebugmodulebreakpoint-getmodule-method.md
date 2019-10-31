---
title: Метод ICorDebugModuleBreakpoint::GetModule
ms.date: 03/30/2017
api_name:
- ICorDebugModuleBreakpoint.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type:
- apiref
ms.openlocfilehash: 6f9d8cd79ac4107817d19fc0632aeaee287d253a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097004"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="941a5-102">Метод ICorDebugModuleBreakpoint::GetModule</span><span class="sxs-lookup"><span data-stu-id="941a5-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="941a5-103">Возвращает указатель интерфейса на "ICorDebugModule", ссылающийся на модуль, в котором задана эта точка останова.</span><span class="sxs-lookup"><span data-stu-id="941a5-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="941a5-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="941a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="941a5-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="941a5-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="941a5-106">заполняет Указатель на адрес интерфейса `ICorDebugModule`, который ссылается на модуль, в котором задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="941a5-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="941a5-107">Требования</span><span class="sxs-lookup"><span data-stu-id="941a5-107">Requirements</span></span>  
 <span data-ttu-id="941a5-108">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="941a5-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="941a5-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="941a5-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="941a5-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="941a5-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="941a5-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="941a5-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="941a5-112">См. также</span><span class="sxs-lookup"><span data-stu-id="941a5-112">See also</span></span>
