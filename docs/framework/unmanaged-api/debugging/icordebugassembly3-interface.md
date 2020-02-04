---
title: Интерфейс ICorDebugAssembly3
ms.date: 03/30/2017
ms.assetid: 17fc5d76-75a9-4933-83f0-594de7f973f3
ms.openlocfilehash: deb300ced2ff7a116bd443c9a7b10dcc0b7955ac
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784530"
---
# <a name="icordebugassembly3-interface"></a>Интерфейс ICorDebugAssembly3
Логически расширяет интерфейс ICorDebugAssembly для обеспечения поддержки контейнерных сборок и их вложенных сборок.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод EnumerateContainedAssemblies](icordebugassembly3-enumeratecontainedassemblies-method.md)|Получает перечислитель для сборок, содержащихся в этой сборке.|  
|[Метод GetContainerAssembly](icordebugassembly3-getcontainerassembly-method.md)|Возвращает контейнерную сборку этого объекта `ICorDebugAssembly3`.|  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот интерфейс доступен только в машинном коде .NET. Попытка вызова метода `QueryInterface` для получения указателя интерфейса возвращает `E_NOINTERFACE` для сценариев ICorDebug вне .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейсы отладки](debugging-interfaces.md)
- [Отладка](index.md)
