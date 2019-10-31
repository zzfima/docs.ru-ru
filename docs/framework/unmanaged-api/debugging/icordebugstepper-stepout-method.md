---
title: Метод ICorDebugStepper::StepOut
ms.date: 03/30/2017
api_name:
- ICorDebugStepper.StepOut
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepper::StepOut
helpviewer_keywords:
- ICorDebugStepper::StepOut method [.NET Framework debugging]
- StepOut method [.NET Framework debugging]
ms.assetid: aae0f48c-4ede-4256-9251-a7fc85a229dc
topic_type:
- apiref
ms.openlocfilehash: 6c1d7db8aacaf81d47abd4a9cd972b44f56a3bb1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137510"
---
# <a name="icordebugstepperstepout-method"></a>Метод ICorDebugStepper::StepOut
Приводит к тому, что данный ICorDebugStepper пошаговым путем через содержащий его поток и завершается, когда текущий кадр возвращает управление вызывающему кадру.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Заметки  
 Операция `StepOut` будет завершена после возврата в обычном режиме из текущего кадра в вызывающий кадр.  
  
 Если `StepOut` вызывается в неуправляемом коде, шаг завершится, когда текущий кадр вернется в управляемый код, вызвавший его.  
  
 В .NET Framework версии 2,0 не используйте `StepOut` с установленным флагом STOP_UNMANAGED, так как он завершится ошибкой. (Используйте [ICorDebugStepper:: сетунмаппедстопмаск](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) для установки флагов для пошагового выполнения.) Отладчики взаимодействия должны выполнять шаг с заходом в собственный код.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
