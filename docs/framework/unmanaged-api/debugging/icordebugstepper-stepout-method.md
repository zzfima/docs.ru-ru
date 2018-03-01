---
title: "Метод ICorDebugStepper::StepOut"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 1d6462f166e9c734dacc7ebee13cb82e3b12158b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugstepperstepout-method"></a>Метод ICorDebugStepper::StepOut
В результате ICorDebugStepper выполнить один шаг через содержащую и для завершения текущего кадра возвращает управление в вызывающий кадр.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT StepOut ();  
```  
  
## <a name="remarks"></a>Примечания  
 Объект `StepOut` операция будет выполнена после возврата в обычном режиме из текущего кадра вызывающий кадр.  
  
 Если `StepOut` вызывается, когда в неуправляемом коде шаг будет выполнен при возврате текущего кадра в управляемый код, который вызвал его.  
  
 В .NET Framework версии 2.0, не следует использовать `StepOut` с по умолчанию STOP_UNMANAGED значение флага, так как она завершится сбоем. (Используйте [ICorDebugStepper::SetUnmappedStopMask](../../../../docs/framework/unmanaged-api/debugging/icordebugstepper-setunmappedstopmask-method.md) установить флаги для пошагового выполнения.) Отладчики взаимодействия необходимо выйти из машинного кода сами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
