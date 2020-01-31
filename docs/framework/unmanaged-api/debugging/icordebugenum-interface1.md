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
ms.openlocfilehash: cc5598f9cbec4b97bb75f83fb18ccf8742904272
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76783007"
---
# <a name="icordebugenum-interface"></a>Интерфейс ICorDebugEnum

Служит абстрактным базовым интерфейсом для перечислителей, используемых приложением отладки.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Clone](icordebugenum-clone-method.md)|Создает копию этого объекта `ICorDebugEnum`.|  
|[Метод GetCount](icordebugenum-getcount-method.md)|Возвращает число элементов в перечислении.|  
|[Метод Reset](icordebugenum-reset-method.md)|Перемещает курсор в начало перечисления.|  
|[Метод Skip](icordebugenum-skip-method.md)|Перемещает курсор вперед в перечислении на указанное число элементов.|  
  
## <a name="remarks"></a>Заметки  
 Следующие перечислители являются производными от `ICorDebugEnum`:  
  
- "Икордебугаппдомаиненум"  
  
- ICorDebugAssemblyEnum  
  
- [икордебугблоккингобжектенум](icordebugblockingobjectenum-interface.md)  
  
- ICorDebugBreakpointEnum  
  
- "Икордебугчаиненум"  
  
- "Икордебугкодинум"  
  
- ICorDebugErrorInfoEnum  
  
- [ICorDebugExceptionObjectCallStackEnum](icordebugexceptionobjectcallstackenum-interface.md)  
  
- ICorDebugFrameEnum  
  
- [ICorDebugGCReferenceEnum](icordebuggcreferenceenum-interface.md)  
  
- [ICorDebugGuidToTypeEnum](icordebugguidtotypeenum-interface.md)  
  
- [икордебугхеапенум](icordebugheapenum-interface.md)  
  
- [икордебугхеапсегментенум](icordebugheapsegmentenum-interface.md)  
  
- "Икордебугмодулинум"  
  
- "Икордебугобжектенум"  
  
- "Икордебугпроцессенум"  
  
- "Икордебугстепперенум"  
  
- "Икордебугсреаденум"  
  
- ICorDebugTypeEnum  
  
- ICorDebugValueEnum  
  
- [ICorDebugVariableHomeEnum](icordebugvariablehomeenum-interface.md)  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
