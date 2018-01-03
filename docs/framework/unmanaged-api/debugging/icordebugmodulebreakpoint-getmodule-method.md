---
title: "Метод ICorDebugModuleBreakpoint::GetModule"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleBreakpoint.GetModule
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleBreakpoint::GetModule
helpviewer_keywords:
- ICorDebugModuleBreakpoint::GetModule method [.NET Framework debugging]
- GetModule method, ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: ffd5d9ec-4564-4200-b625-b306eec0ebd7
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 91e014a16420ea6790b592efe1ac57df960d2237
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="3216f-102">Метод ICorDebugModuleBreakpoint::GetModule</span><span class="sxs-lookup"><span data-stu-id="3216f-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="3216f-103">Получает указатель интерфейса на «ICorDebugModule», ссылается на модуль, в котором установлена данная точка останова.</span><span class="sxs-lookup"><span data-stu-id="3216f-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3216f-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="3216f-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="3216f-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="3216f-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="3216f-106">[out] Указатель на адрес `ICorDebugModule` интерфейс, который ссылается на модуль, в которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="3216f-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3216f-107">Требования</span><span class="sxs-lookup"><span data-stu-id="3216f-107">Requirements</span></span>  
 <span data-ttu-id="3216f-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3216f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3216f-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3216f-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3216f-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3216f-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3216f-111">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3216f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3216f-112">См. также</span><span class="sxs-lookup"><span data-stu-id="3216f-112">See Also</span></span>  
 
