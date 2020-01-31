---
title: Интерфейс ICorDebugMergedAssemblyRecord
ms.date: 03/30/2017
ms.assetid: fe280b11-9479-4e34-a07c-0d1ea8088422
ms.openlocfilehash: 6d5d862110cd91e8ac81c96e50486be10c579903
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793058"
---
# <a name="icordebugmergedassemblyrecord-interface"></a>Интерфейс ICorDebugMergedAssemblyRecord
Предоставляет сведения о сборке после слияния.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetCulture](icordebugmergedassemblyrecord-getculture-method.md)|Возвращает строку с названием языка и региональных параметров сборки.|  
|[Метод GetIndex](icordebugmergedassemblyrecord-getindex-method.md)|Возвращает индекс префикса сборки.|  
|[Метод GetPublicKey](icordebugmergedassemblyrecord-getpublickey-method.md)|Возвращает открытый ключ сборки.|  
|[Метод GetPublicKeyToken](icordebugmergedassemblyrecord-getpublickeytoken-method.md)|Возвращает токен открытого ключа сборки.|  
|[Метод GetSimpleName](icordebugmergedassemblyrecord-getsimplename-method.md)|Получает простое имя сборки.|  
|[Метод GetVersion](icordebugmergedassemblyrecord-getversion-method.md)|Возвращает сведения о версии сборки.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
