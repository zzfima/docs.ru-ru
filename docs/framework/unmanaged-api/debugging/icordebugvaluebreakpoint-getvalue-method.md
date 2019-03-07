---
title: Метод ICorDebugValueBreakpoint::GetValue
ms.date: 03/30/2017
api_name:
- ICorDebugValueBreakpoint.GetValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValueBreakpoint::GetValue
helpviewer_keywords:
- GetValue method, ICorDebugValueBreakpoint interface [.NET Framework debugging]
- ICorDebugValueBreakpoint::GetValue method [.NET Framework debugging]
ms.assetid: 52a73654-bc47-48b6-b2b1-a4456b10140c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da23c7da7869c9190b8ce4ad94553a1cb8fc958d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495134"
---
# <a name="icordebugvaluebreakpointgetvalue-method"></a><span data-ttu-id="a6b11-102">Метод ICorDebugValueBreakpoint::GetValue</span><span class="sxs-lookup"><span data-stu-id="a6b11-102">ICorDebugValueBreakpoint::GetValue Method</span></span>
<span data-ttu-id="a6b11-103">Получает указатель интерфейса на объект «ICorDebugValue», который представляет значение объекта, на котором установлена точка останова.</span><span class="sxs-lookup"><span data-stu-id="a6b11-103">Gets an interface pointer to an "ICorDebugValue" object that represents the value of the object on which the breakpoint is set.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a6b11-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a6b11-104">Syntax</span></span>  
  
```  
HRESULT GetValue (  
    [out] ICorDebugValue   **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a6b11-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a6b11-105">Parameters</span></span>  
 `ppValue`  
 <span data-ttu-id="a6b11-106">[out] Указатель на адрес `ICorDebugValue` объекта.</span><span class="sxs-lookup"><span data-stu-id="a6b11-106">[out] A pointer to the address of an `ICorDebugValue` object.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a6b11-107">Требования</span><span class="sxs-lookup"><span data-stu-id="a6b11-107">Requirements</span></span>  
 <span data-ttu-id="a6b11-108">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a6b11-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a6b11-109">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a6b11-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a6b11-110">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a6b11-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a6b11-111">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a6b11-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6b11-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a6b11-112">See also</span></span>

