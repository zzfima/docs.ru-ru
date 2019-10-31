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
ms.openlocfilehash: 39175e338e4fd98dd4af1325138da732ed81c764
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137923"
---
# <a name="icordebugframegetfunction-method"></a><span data-ttu-id="901f6-102">Метод ICorDebugFrame::GetFunction</span><span class="sxs-lookup"><span data-stu-id="901f6-102">ICorDebugFrame::GetFunction Method</span></span>
<span data-ttu-id="901f6-103">Возвращает функцию, содержащую код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="901f6-103">Gets the function that contains the code associated with this stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="901f6-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="901f6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunction (  
    [out] ICorDebugFunction  **ppFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="901f6-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="901f6-105">Parameters</span></span>  
 `ppFunction`  
 <span data-ttu-id="901f6-106">заполняет Указатель на адрес объекта ICorDebugFunction, представляющего функцию, содержащую код, связанный с данным кадром стека.</span><span class="sxs-lookup"><span data-stu-id="901f6-106">[out] A pointer to the address of an ICorDebugFunction object that represents the function containing the code associated with this stack frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="901f6-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="901f6-107">Remarks</span></span>  
 <span data-ttu-id="901f6-108">Метод `GetFunction` может завершиться ошибкой, если фрейм не связан с какой-либо определенной функцией.</span><span class="sxs-lookup"><span data-stu-id="901f6-108">The `GetFunction` method may fail if the frame is not associated with any particular function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="901f6-109">Требования</span><span class="sxs-lookup"><span data-stu-id="901f6-109">Requirements</span></span>  
 <span data-ttu-id="901f6-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="901f6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="901f6-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="901f6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="901f6-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="901f6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="901f6-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="901f6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
