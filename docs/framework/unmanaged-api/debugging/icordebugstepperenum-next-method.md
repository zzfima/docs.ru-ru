---
title: Метод ICorDebugStepperEnum::Next
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ac3165ab17eb1b4bc55a4bee4d2d2b467f8aefe
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57494601"
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="5f34c-102">Метод ICorDebugStepperEnum::Next</span><span class="sxs-lookup"><span data-stu-id="5f34c-102">ICorDebugStepperEnum::Next Method</span></span>
<span data-ttu-id="5f34c-103">Получает указанное число экземпляров ICorDebugStepper из перечисления, начиная с текущей позиции.</span><span class="sxs-lookup"><span data-stu-id="5f34c-103">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f34c-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5f34c-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5f34c-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="5f34c-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="5f34c-106">[in] Количество `ICorDebugStepper` извлекаемых экземпляров.</span><span class="sxs-lookup"><span data-stu-id="5f34c-106">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="5f34c-107">[out] Массив указателей, каждый из которых указывает `ICorDebugStepper` объекта.</span><span class="sxs-lookup"><span data-stu-id="5f34c-107">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="5f34c-108">[out] Указатель на число `ICorDebugStepper` фактически возвращенных экземпляров.</span><span class="sxs-lookup"><span data-stu-id="5f34c-108">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="5f34c-109">Это значение может иметь значение null Если `celt` — один.</span><span class="sxs-lookup"><span data-stu-id="5f34c-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5f34c-110">Требования</span><span class="sxs-lookup"><span data-stu-id="5f34c-110">Requirements</span></span>  
 <span data-ttu-id="5f34c-111">**Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f34c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f34c-112">**Заголовок.** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5f34c-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5f34c-113">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f34c-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f34c-114">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f34c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
