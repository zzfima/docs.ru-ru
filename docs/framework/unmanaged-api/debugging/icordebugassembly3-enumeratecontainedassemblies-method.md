---
title: Метод ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
ms.openlocfilehash: 616675f839e562227558ece440bdfdf497747572
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76784563"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a>Метод ICorDebugAssembly3::EnumerateContainedAssemblies
Получает перечислитель для сборок, содержащихся в этой сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppAssemblies`  
 [выходной] Указатель на адрес объекта интерфейса ICorDebugAssemblyEnum, который является перечислителем.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если этот объект `ICorDebugAssembly3` является контейнером; в противном случае — `S_FALSE`, и перечисление будет пустым.  
  
## <a name="remarks"></a>Заметки  
 Символы необходимы для перечисления вложенных сборок. Если они отсутствуют, метод возвращает `S_FALSE`, и действительный перечислитель отсутствует.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugAssembly3](icordebugassembly3-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
