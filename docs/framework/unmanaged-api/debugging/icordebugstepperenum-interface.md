---
title: Интерфейс ICorDebugStepperEnum
ms.date: 03/30/2017
api_name:
- ICorDebugStepperEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugStepperEnum
helpviewer_keywords:
- ICorDebugStepperEnum interface [.NET Framework debugging]
ms.assetid: 988718c1-1a4a-40f2-a04c-7d67e5cfe1e2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad6c48b08fbdc660fdaa7ce5bfda3a6c0529662a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2019
ms.locfileid: "56980734"
---
# <a name="icordebugstepperenum-interface"></a>Интерфейс ICorDebugStepperEnum
Реализует методы ICorDebugEnum и выполняет перечисление массивов ICorDebugStepper.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Next](../../../../docs/framework/unmanaged-api/debugging/icordebugstepperenum-next-method.md)|Возвращает заданное число `ICorDebugStepper` экземпляров из перечисления, начиная с текущей позиции.|  
  
## <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
