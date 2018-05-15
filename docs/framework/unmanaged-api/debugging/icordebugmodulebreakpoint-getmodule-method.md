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
ms.openlocfilehash: 5cbb1aa9c81101eb818a9e7829c777efd3923b5f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmodulebreakpointgetmodule-method"></a><span data-ttu-id="769e4-102">Метод ICorDebugModuleBreakpoint::GetModule</span><span class="sxs-lookup"><span data-stu-id="769e4-102">ICorDebugModuleBreakpoint::GetModule Method</span></span>
<span data-ttu-id="769e4-103">Получает указатель интерфейса на «ICorDebugModule», ссылается на модуль, в котором установлена данная точка останова.</span><span class="sxs-lookup"><span data-stu-id="769e4-103">Gets an interface pointer to an "ICorDebugModule" that references the module in which this breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="769e4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="769e4-104">Syntax</span></span>  
  
```  
HRESULT GetModule (  
    [out] ICorDebugModule   **ppModule  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="769e4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="769e4-105">Parameters</span></span>  
 `ppModule`  
 <span data-ttu-id="769e4-106">[out] Указатель на адрес `ICorDebugModule` интерфейс, который ссылается на модуль, в которой задана точка останова.</span><span class="sxs-lookup"><span data-stu-id="769e4-106">[out] A pointer to the address of an `ICorDebugModule` interface that references the module in which the breakpoint is set.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="769e4-107">Требования</span><span class="sxs-lookup"><span data-stu-id="769e4-107">Requirements</span></span>  
 <span data-ttu-id="769e4-108">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="769e4-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="769e4-109">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="769e4-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="769e4-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="769e4-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="769e4-111">**Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="769e4-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="769e4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="769e4-112">See Also</span></span>  
 
