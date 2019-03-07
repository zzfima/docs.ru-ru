---
title: Метод ICorDebugFrame::GetFunction
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.GetFunction
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::GetFunction
helpviewer_keywords:
- GetFunction method, ICorDebugFrame interface [.NET Framework debugging]
- ICorDebugFrame::GetFunction method [.NET Framework debugging]
ms.assetid: 879d2311-0ff1-4616-a8b3-959ea5868b2e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a48396f8ef668cfe7755b2718180317b465793b6
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475294"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="64791-102">Метод ICorDebugFrame::GetFunction</span><span class="sxs-lookup"><span data-stu-id="64791-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="64791-103">Возвращает функции, которая содержит код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="64791-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64791-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="64791-104">Syntax</span></span>  
  
```  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64791-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="64791-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="64791-106">[out] Указатель на адрес ICorDebugFunction объект, представляющий функцию, содержащую код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="64791-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="64791-107">Примечания</span><span class="sxs-lookup"><span data-stu-id="64791-107">Remarks</span></span>  
 <span data-ttu-id="64791-108">`GetFunction` Может произойти сбой метода, если кадр не связан с каждой функции.</span><span class="sxs-lookup"><span data-stu-id="64791-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64791-109">Требования</span><span class="sxs-lookup"><span data-stu-id="64791-109">Requirements</span></span>  
 <span data-ttu-id="64791-110">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64791-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64791-111">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="64791-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="64791-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="64791-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="64791-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64791-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
