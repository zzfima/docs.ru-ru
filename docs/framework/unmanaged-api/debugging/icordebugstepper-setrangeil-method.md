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
ms.openlocfilehash: b3153a88867d249aad8365bb774348fb8c9d57d5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791751"
---
# <a name="icordebugsteppersetrangeil-method"></a><span data-ttu-id="a0948-102">Метод ICorDebugStepper::SetRangeIL</span><span class="sxs-lookup"><span data-stu-id="a0948-102">ICorDebugStepper::SetRangeIL Method</span></span>
<span data-ttu-id="a0948-103">Задает значение, указывающее, будут ли вызовы метода [ICorDebugStepper:: степранже](icordebugstepper-steprange-method.md) передавать значения аргумента, которые относятся к машинному коду или по коду языка MSIL в методе, через который выполняется пошаговое выполнение.</span><span class="sxs-lookup"><span data-stu-id="a0948-103">Sets a value that specifies whether calls to [ICorDebugStepper::StepRange](icordebugstepper-steprange-method.md) pass argument values that are relative to the native code or relative to Microsoft intermediate language (MSIL) code of the method that is being stepped through.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0948-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="a0948-104">Syntax</span></span>  
  
```cpp  
HRESULT SetRangeIL (  
    [in] BOOL    bIL  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a0948-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="a0948-105">Parameters</span></span>  
 `bIL`  
 <span data-ttu-id="a0948-106">окне Задайте значение `true`, чтобы указать, что диапазоны относительны по коду MSIL.</span><span class="sxs-lookup"><span data-stu-id="a0948-106">[in] Set to `true` to specify that the ranges are relative to the MSIL code.</span></span> <span data-ttu-id="a0948-107">Задайте значение `false`, чтобы указать, что диапазоны относятся к машинному коду.</span><span class="sxs-lookup"><span data-stu-id="a0948-107">Set to `false` to specify that the ranges are relative to the native code.</span></span> <span data-ttu-id="a0948-108">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="a0948-108">The default value is `true`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a0948-109">Требования</span><span class="sxs-lookup"><span data-stu-id="a0948-109">Requirements</span></span>  
 <span data-ttu-id="a0948-110">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a0948-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a0948-111">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a0948-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a0948-112">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a0948-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a0948-113">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a0948-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
