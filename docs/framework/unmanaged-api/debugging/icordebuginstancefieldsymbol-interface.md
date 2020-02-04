---
title: Интерфейс ICorDebugInstanceFieldSymbol
ms.date: 03/30/2017
ms.assetid: a4a8f259-b83a-4425-ae8b-72b067dbc0d9
ms.openlocfilehash: 41258b0eeed5fbf8ab86546f74073f8eeaa3085c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777523"
---
# <a name="icordebuginstancefieldsymbol-interface"></a>Интерфейс ICorDebugInstanceFieldSymbol
Представляет сведения отладочного символа для поля экземпляра.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetName](icordebuginstancefieldsymbol-getname-method.md)|Получает имя поля экземпляра.|  
|[Метод GetOffset](icordebuginstancefieldsymbol-getoffset-method.md)|Возвращает смещение в байтах этого поля экземпляра в его родительском классе.|  
|[Метод GetSize](icordebuginstancefieldsymbol-getsize-method.md)|Получает размер поля экземпляра в байтах.|  
  
## <a name="remarks"></a>Заметки  
 Интерфейс `ICorDebugInstanceFieldSymbol` используется для получения сведений символа отладки для поля экземпляра.  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
