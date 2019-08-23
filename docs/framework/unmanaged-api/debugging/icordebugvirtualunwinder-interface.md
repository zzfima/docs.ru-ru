---
title: Интерфейс ICorDebugVirtualUnwinder
ms.date: 03/30/2017
ms.assetid: a09e9ccc-0b37-43e3-95c1-bc5fa7ee5f42
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f78417d613023bb4fb7325560c0c06abe0874aba
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69967941"
---
# <a name="icordebugvirtualunwinder-interface"></a>Интерфейс ICorDebugVirtualUnwinder
Предоставляет методы, помогающие очистить стек.  
  
## <a name="methods"></a>Методы  
  
|Метод|name|  
|------------|----------|  
|[Метод GetContext](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-getcontext-method.md)|Получает текущий контекст этого средства очистки.|  
|[Метод Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvirtualunwinder-next-method.md)|Переходит в контекст вызывающего объекта.|  
  
## <a name="remarks"></a>Примечания  
 Элементы интерфейса `ICorDebugVirtualUnwinder` реализуются отладчиком для упрощения очистки стека.  
  
> [!NOTE]
> Этот интерфейс доступен только в .NET Native. При реализации этого интерфейса для сценариев ICorDebug вне .NET Native среда CLR будет игнорировать этот интерфейс.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug. idl, CorDebug. h  
  
 **Библиотечная** Коргуидс. lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
