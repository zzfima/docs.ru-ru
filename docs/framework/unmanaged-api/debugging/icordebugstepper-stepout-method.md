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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 36a33b74a692761d772a888ce918aa28a2d92678
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760556"
---
# <a name="icordebugstepperstepout-method"></a>Метод ICorDebugStepper::StepOut
Принуждает ICorDebugStepper выполнить один шаг через содержащую и для завершения текущего кадра возвращает управление в вызывающий кадр.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Примечания  
 Объект `StepOut` операция будет выполнена после возврата в обычном режиме из текущего кадра на вызывающий кадр.  
  
 Если `StepOut` вызывается, когда в неуправляемом коде, шаг будет выполнен при возврате текущего кадра в управляемый код, который вызвал ее.  
  
 В .NET Framework версии 2.0, не используйте `StepOut` с по умолчанию STOP_UNMANAGED флага stateful, так как его не удастся. (Используйте [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) установить флаги для пошагового выполнения.) Отладчики взаимодействия необходимо шаг с выходом в машинный код самостоятельно.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
