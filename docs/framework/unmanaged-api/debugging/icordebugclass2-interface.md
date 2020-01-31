---
title: Интерфейс ICorDebugClass2
ms.date: 03/30/2017
api_name:
- ICorDebugClass2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass2
helpviewer_keywords:
- ICorDebugClass2 interface [.NET Framework debugging]
ms.assetid: 5416de70-43f2-4cdf-a11f-d570759c9c0c
topic_type:
- apiref
ms.openlocfilehash: 795e9f4862992d95eeef98a986545cca47d828c6
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784145"
---
# <a name="icordebugclass2-interface"></a>Интерфейс ICorDebugClass2

Представляет универсальный класс или класс параметром метода типа <xref:System.Type>. Этот интерфейс расширяет [ICorDebugClass](icordebugclass-interface.md).  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetParameterizedType](icordebugclass2-getparameterizedtype-method.md)|Возвращает объявление типа для этого класса.|  
|[Метод SetJMCStatus](icordebugclass2-setjmcstatus-method.md)|Для каждого метода этого класса задает значение, указывающее, является ли метод определяемым пользователем кодом.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс не поддерживает удаленные вызовы между компьютерами или между процессами.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugClass](icordebugclass-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
