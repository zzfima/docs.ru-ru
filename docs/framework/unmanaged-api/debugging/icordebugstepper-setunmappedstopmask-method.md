---
title: "Метод ICorDebugStepper::SetUnmappedStopMask"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepper.SetUnmappedStopMask
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepper::SetUnmappedStopMask
helpviewer_keywords:
- ICorDebugStepper::SetUnmappedStopMask method [.NET Framework debugging]
- SetUnmappedStopMask method [.NET Framework debugging]
ms.assetid: b1211981-e90c-4e05-8def-fa18d85ad9ab
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2fffd523caef6bba1b495f9b8a257f57bd8955af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugsteppersetunmappedstopmask-method"></a><span data-ttu-id="e7c4e-102">Метод ICorDebugStepper::SetUnmappedStopMask</span><span class="sxs-lookup"><span data-stu-id="e7c4e-102">ICorDebugStepper::SetUnmappedStopMask Method</span></span>
<span data-ttu-id="e7c4e-103">Задает значение, которое указывает тип несопоставимого кода, в котором выполнение будет остановлено.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-103">Sets a value that specifies the type of unmapped code in which execution will halt.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7c4e-104">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="e7c4e-104">Syntax</span></span>  
  
```  
HRESULT SetUnmappedStopMask (  
    [in] CorDebugUnmappedStop   mask  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e7c4e-105">Параметры</span><span class="sxs-lookup"><span data-stu-id="e7c4e-105">Parameters</span></span>  
 `mask`  
 <span data-ttu-id="e7c4e-106">[in] Значение перечисления CorDebugUnmappedStop, которое указывает тип несопоставимого кода, в котором отладчик остановится выполнения.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-106">[in] A value of the CorDebugUnmappedStop enumeration that specifies the type of unmapped code in which the debugger will halt execution.</span></span>  
  
 <span data-ttu-id="e7c4e-107">Значение по умолчанию — STOP_OTHER_UNMAPPED.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-107">The default value is STOP_OTHER_UNMAPPED.</span></span> <span data-ttu-id="e7c4e-108">Значение по умолчанию STOP_UNMANAGED допустимо только при отладке взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-108">The value STOP_UNMANAGED is only valid with interop debugging.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e7c4e-109">Примечания</span><span class="sxs-lookup"><span data-stu-id="e7c4e-109">Remarks</span></span>  
 <span data-ttu-id="e7c4e-110">Когда отладчик обнаруживает компиляции just-in-time (JIT), в которой отсутствует сопоставление в промежуточный язык Microsoft (MSIL), он прерывает выполнение, если установлен флаг, указывающий, что тип несопоставимого кода; в противном случае проверка прозрачно продолжается.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-110">When the debugger finds a just-in-time (JIT) compilation that has no corresponding mapping to Microsoft intermediate language (MSIL), it halts execution if the flag specifying that type of unmapped code has been set; otherwise, stepping transparently continues.</span></span>  
  
 <span data-ttu-id="e7c4e-111">Если отладчик не использует средство организации пошагового режима для входа в метод, затем он не будет обходить обязательно неуправляемого кода.</span><span class="sxs-lookup"><span data-stu-id="e7c4e-111">If the debugger doesn't use a stepper to enter a method, then it won't necessarily step over unmapped code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7c4e-112">Требования</span><span class="sxs-lookup"><span data-stu-id="e7c4e-112">Requirements</span></span>  
 <span data-ttu-id="e7c4e-113">**Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7c4e-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7c4e-114">**Заголовок:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e7c4e-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e7c4e-115">**Библиотека:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7c4e-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7c4e-116">**Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7c4e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
