---
title: Метод ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aa99e7289e0e86032f7bb85bbe209932f5c50d16
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627581"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a>Метод ICorDebugAssembly3::EnumerateContainedAssemblies
Получает перечислитель для сборок, содержащихся в этой сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `ppAssemblies`  
 [out] Указатель на адрес объекта интерфейса ICorDebugAssemblyEnum, который является перечислителем.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK`, если этот объект `ICorDebugAssembly3` является контейнером; в противном случае — `S_FALSE`, и перечисление будет пустым.  
  
## <a name="remarks"></a>Примечания  
 Символы необходимы для перечисления вложенных сборок. Если они отсутствуют, метод возвращает `S_FALSE`, и действительный перечислитель отсутствует.  
  
> [!NOTE]
>  Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebugAssembly3](../../../../docs/framework/unmanaged-api/debugging/icordebugassembly3-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
