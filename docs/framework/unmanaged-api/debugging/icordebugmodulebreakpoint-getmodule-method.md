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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51403c52d7f8a216e83b817f157979f4af1c433a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59162872"
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="b4ca9-102">Метод ICorDebugModuleBreakpoint::GetModule</span><span class="sxs-lookup"><span data-stu-id="b4ca9-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="b4ca9-103">Получает указатель интерфейса на «ICorDebugModule», ссылается на модуль, в котором установлена данная точка останова.</span><span class="sxs-lookup"><span data-stu-id="b4ca9-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4ca9-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b4ca9-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4ca9-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="b4ca9-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="b4ca9-106">[out] Указатель на адрес `ICorDebugModule` интерфейс, который ссылается на модуль, в котором задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="b4ca9-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4ca9-107">Требования</span><span class="sxs-lookup"><span data-stu-id="b4ca9-107">Requirements</span></span>  
 <span data-ttu-id="b4ca9-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4ca9-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4ca9-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4ca9-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4ca9-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4ca9-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4ca9-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4ca9-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4ca9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="b4ca9-112">See also</span></span>
