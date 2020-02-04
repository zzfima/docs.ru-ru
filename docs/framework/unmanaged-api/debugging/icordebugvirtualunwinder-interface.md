---
title: Интерфейс ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
ms.openlocfilehash: 065f71e45c2a56dbaa16a45f70958ca3dea80c48
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790827"
---
# <a name="icordebugvirtualunwinder-interface"></a>Интерфейс ICorDebugVirtualUnwinder
Предоставляет методы, помогающие очистить стек.  
  
## <a name="methods"></a>Методы  
  
|Метод|Name|  
|------------|----------|  
|[Метод GetContext](icordebugvirtualunwinder-getcontext-method.md)|Получает текущий контекст этого средства очистки.|  
|[Метод Next](icordebugvirtualunwinder-next-method.md)|Переходит в контекст вызывающего объекта.|  
  
## <a name="remarks"></a>Заметки  
 Элементы интерфейса `ICorDebugVirtualUnwinder` реализуются отладчиком для упрощения очистки стека.  
  
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
