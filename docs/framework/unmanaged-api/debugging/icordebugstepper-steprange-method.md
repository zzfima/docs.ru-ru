---
title: Метод ICorDebugStepper::StepRange
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepRange
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepRange
helpviewer_keywords:
- StepRange method [.NET Framework debugging]
- ICorDebugStepper::StepRange method [.NET Framework debugging]
ms.assetid: b9776112-6e6d-4708-892a-8873db02e16f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7b18474aeaa79224de5371df3ff0cac5ed9bf4ff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61994291"
---
# <a name="icordebugsteppersteprange-method"></a>Метод ICorDebugStepper::StepRange
Принуждает ICorDebugStepper выполнить один шаг через содержащую и должны быть возвращены при достижении кода за последним из указанных диапазонов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT StepRange (  
    [in] BOOL     bStepIn,  
    [in, size_is(cRangeCount)] COR_DEBUG_STEP_RANGE ranges[],  
    [in] ULONG32  cRangeCount  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `bStepIn`  
 [in] Значение `true` на шаг с заходом в функцию, которая вызывается в потоке. Значение `false` на шаг с обходом функции.  
  
 `ranges`  
 [in] Массив структур COR_DEBUG_STEP_RANGE, каждый из которых задает диапазон.  
  
 `cRangeCount`  
 [in] Размер массива `ranges`.  
  
## <a name="remarks"></a>Примечания  
 `StepRange` Метод работает подобно [ICorDebugStepper::Step](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-step-method.md) метода, за исключением того, что она не завершается до кода за пределами данного диапазона будет достигнут.  
  
 Это может быть более эффективным, чем пошаговое выполнение одной инструкции одновременно. Диапазоны задаются в виде списка пар смещения от начала несопоставимого кадра.  
  
 Диапазоны указываются относительно кода промежуточного языка MSIL Microsoft метода. Вызовите [ICorDebugStepper::SetRangeIL](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setrangeil-method.md) с `false` вносить диапазоны машинному коду метода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
