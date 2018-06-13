---
title: ICorDebugEnum интерфейс1
ms.date: 03/30/2017
api_name:
- ICorDebugEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEnum
helpviewer_keywords:
- ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: 80be7efe-2c32-4b9f-8c52-40c6f6268219
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a4659bbc9c2e3c71a6cf85e51a06bee4f789356b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422309"
---
# <a name="icordebugenum-interface1"></a>ICorDebugEnum интерфейс1
Служит абстрактным базовым интерфейсом для перечислителей, которые используются приложением для отладки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|Создает копию объекта `ICorDebugEnum` объекта.|  
|[Метод GetCount](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|Получает число элементов в перечислении.|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|Перемещает курсор в начало перечисления.|  
|[Метод Skip](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|Перемещение курсора вперед в перечислении указанное число элементов.|  
  
## <a name="remarks"></a>Примечания  
 Следующие перечислители являются производными от `ICorDebugEnum`:  
  
-   «ICorDebugAppDomainEnum»  
  
-   «ICorDebugAssemblyEnum»  
  
-   [ICorDebugBlockingObjectEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
-   «ICorDebugBreakpointEnum»  
  
-   «ICorDebugChainEnum»  
  
-   «ICorDebugCodeEnum»  
  
-   «ICorDebugErrorInfoEnum»  
  
-   [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
-   «ICorDebugFrameEnum»  
  
-   [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
-   [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
-   [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
-   [ICorDebugHeapSegmentEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
-   «ICorDebugModuleEnum»  
  
-   «ICorDebugObjectEnum»  
  
-   «ICorDebugProcessEnum»  
  
-   «ICorDebugStepperEnum»  
  
-   «ICorDebugThreadEnum»  
  
-   «ICorDebugTypeEnum»  
  
-   «ICorDebugValueEnum»  
  
-   [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
>  Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
