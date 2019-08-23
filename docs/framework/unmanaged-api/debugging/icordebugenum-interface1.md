---
title: Интерфейс ICorDebugEnum
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
ms.openlocfilehash: b25c47e101ad0fb8e8cbdbb2718a41c9be6c0c22
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69931985"
---
# <a name="icordebugenum-interface"></a>Интерфейс ICorDebugEnum

Служит абстрактным базовым интерфейсом для перечислителей, используемых приложением отладки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-clone-method.md)|Создает копию этого `ICorDebugEnum` объекта.|  
|[Метод GetCount](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-getcount-method.md)|Возвращает число элементов в перечислении.|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-reset-method.md)|Перемещает курсор в начало перечисления.|  
|[Метод Skip](../../../../docs/framework/unmanaged-api/debugging/icordebugenum-skip-method.md)|Перемещает курсор вперед в перечислении на указанное число элементов.|  
  
## <a name="remarks"></a>Примечания  
 Следующие перечислители являются производными `ICorDebugEnum`от:  
  
- "Икордебугаппдомаиненум"  
  
- ICorDebugAssemblyEnum  
  
- [икордебугблоккингобжектенум](../../../../docs/framework/unmanaged-api/debugging/icordebugblockingobjectenum-interface.md)  
  
- ICorDebugBreakpointEnum  
  
- "Икордебугчаиненум"  
  
- "Икордебугкодинум"  
  
- ICorDebugErrorInfoEnum  
  
- [ICorDebugExceptionObjectCallStackEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)  
  
- ICorDebugFrameEnum  
  
- [ICorDebugGCReferenceEnum](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-interface.md)  
  
- [ICorDebugGuidToTypeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugguidtotypeenum-interface.md)  
  
- [икордебугхеапенум](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md)  
  
- [икордебугхеапсегментенум](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md)  
  
- "Икордебугмодулинум"  
  
- "Икордебугобжектенум"  
  
- "Икордебугпроцессенум"  
  
- "Икордебугстепперенум"  
  
- "Икордебугсреаденум"  
  
- ICorDebugTypeEnum  
  
- ICorDebugValueEnum  
  
- [ICorDebugVariableHomeEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
