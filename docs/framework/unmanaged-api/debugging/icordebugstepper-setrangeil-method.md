---
title: Метод ICorDebugStepper::SetRangeIL
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetRangeIL
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetRangeIL
helpviewer_keywords:
- SetRangeIL method [.NET Framework debugging]
- ICorDebugStepper::SetRangeIL method [.NET Framework debugging]
ms.assetid: a20c95f0-6da7-4b41-b27f-584211cebb92
topic_type:
- apiref
ms.openlocfilehash: 88270cb73515cc1a671bfb3fb5c479697ad7b359
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137546"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="89642-102">Метод ICorDebugStepper::SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="89642-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="89642-103">Задает значение, указывающее, будут ли вызовы метода [ICorDebugStepper:: степранже](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) передавать значения аргумента, которые относятся к машинному коду или по коду языка MSIL в методе, через который выполняется пошаговое выполнение.</span><span class="sxs-lookup"><span data-stu-id="89642-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89642-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89642-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89642-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="89642-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="89642-106">окне Задайте значение `true`, чтобы указать, что диапазоны относительны по коду MSIL.</span><span class="sxs-lookup"><span data-stu-id="89642-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="89642-107">Задайте значение `false`, чтобы указать, что диапазоны относятся к машинному коду.</span><span class="sxs-lookup"><span data-stu-id="89642-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="89642-108">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="89642-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89642-109">Требования</span><span class="sxs-lookup"><span data-stu-id="89642-109">Requirements</span></span>  
 <span data-ttu-id="89642-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89642-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89642-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="89642-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="89642-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89642-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89642-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89642-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
