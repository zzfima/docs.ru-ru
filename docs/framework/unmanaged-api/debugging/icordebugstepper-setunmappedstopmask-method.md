---
title: Метод ICorDebugStepper::SetUnmappedStopMask
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.SetUnmappedStopMask
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type:
- apiref
ms.openlocfilehash: ff393b119c349e34898b781c3185cc82f2dba11f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137554"
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="00bf1-102">Метод ICorDebugStepper::SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="00bf1-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="00bf1-103">Задает значение, указывающее тип несопоставленного кода, в котором выполнение будет остановлено.</span><span class="sxs-lookup"><span data-stu-id="00bf1-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00bf1-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="00bf1-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="00bf1-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="00bf1-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="00bf1-106">окне Значение перечисления Кордебугунмаппедстоп, указывающее тип несопоставленного кода, в котором отладчик остановит выполнение.</span><span class="sxs-lookup"><span data-stu-id="00bf1-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="00bf1-107">Значение по умолчанию — STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="00bf1-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="00bf1-108">Значение STOP_UNMANAGED допустимо только при отладке взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="00bf1-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="00bf1-109">Заметки</span><span class="sxs-lookup"><span data-stu-id="00bf1-109">Remarks</span></span>  
 <span data-ttu-id="00bf1-110">Когда отладчик находит JIT-компиляцию, которая не имеет соответствующего сопоставления с MSIL, он прекращает выполнение, если установлен флаг, указывающий этот тип несопоставленного кода. в противном случае выполнение по шагам прозрачно продолжится.</span><span class="sxs-lookup"><span data-stu-id="00bf1-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="00bf1-111">Если отладчик не использует средство многошагового режима для входа в метод, он не обязательно будет выполнять шаг с обходом несопоставленного кода.</span><span class="sxs-lookup"><span data-stu-id="00bf1-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00bf1-112">Требования</span><span class="sxs-lookup"><span data-stu-id="00bf1-112">Requirements</span></span>  
 <span data-ttu-id="00bf1-113">**Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00bf1-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00bf1-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="00bf1-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="00bf1-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00bf1-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00bf1-116">**Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00bf1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
