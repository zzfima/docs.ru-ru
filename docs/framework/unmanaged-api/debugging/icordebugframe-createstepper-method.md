---
title: Метод ICorDebugFrame::CreateStepper
ms.date: 03/30/2017
api_name:
- ICorDebugFrame.CreateStepper
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFrame::CreateStepper
helpviewer_keywords:
- ICorDebugFrame::CreateStepper method [.NET Framework debugging]
- CreateStepper method, ICorDebugFrame interface [.NET Framework debugging]
ms.assetid: 689e7f28-20c1-4d5c-9baa-17441cd63a88
topic_type:
- apiref
ms.openlocfilehash: 6ea2b24d37f56a5cb9e6b3dea0d666c8acc719dc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091032"
---
# <a name="icordebugframecreatestepper-method"></a><span data-ttu-id="ebfc4-102">Метод ICorDebugFrame::CreateStepper</span><span class="sxs-lookup"><span data-stu-id="ebfc4-102">ICorDebugFrame::CreateStepper Method</span></span>
<span data-ttu-id="ebfc4-103">Возвращает средство, позволяющее отладчику выполнять операции пошагового выполнения по отношению к этому ICorDebugFrame.</span><span class="sxs-lookup"><span data-stu-id="ebfc4-103">Gets a stepper that allows the debugger to perform stepping operations relative to this ICorDebugFrame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebfc4-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="ebfc4-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateStepper (  
    [out] ICorDebugStepper   **ppStepper  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebfc4-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="ebfc4-105">Parameters</span></span>  
 `ppStepper`  
 <span data-ttu-id="ebfc4-106">заполняет Указатель на адрес объекта ICorDebugStepper, который позволяет отладчику выполнять операции пошагового выполнения по отношению к текущему кадру.</span><span class="sxs-lookup"><span data-stu-id="ebfc4-106">[out] A pointer to the address of an ICorDebugStepper object that allows the debugger to perform stepping operations relative to the current frame.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebfc4-107">Заметки</span><span class="sxs-lookup"><span data-stu-id="ebfc4-107">Remarks</span></span>  
 <span data-ttu-id="ebfc4-108">Если кадр неактивен, объект средства Организации, как правило, должен вернуться к кадру до завершения этого шага.</span><span class="sxs-lookup"><span data-stu-id="ebfc4-108">If the frame is not active, the stepper object will typically have to return to the frame before the step is completed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebfc4-109">Требования</span><span class="sxs-lookup"><span data-stu-id="ebfc4-109">Requirements</span></span>  
 <span data-ttu-id="ebfc4-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebfc4-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebfc4-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ebfc4-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ebfc4-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebfc4-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebfc4-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebfc4-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
