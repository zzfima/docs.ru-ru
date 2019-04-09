---
title: Метод ICorDebugAssembly3::EnumerateContainedAssemblies
ms.date: 03/30/2017
ms.assetid: 98f15b05-afad-4616-9e2a-1a9af31948b6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54ccb52468a530280527252e0e0c43cc9edbb2c3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59080960"
---
# <a name="icordebugassembly3enumeratecontainedassemblies-method"></a>Метод ICorDebugAssembly3::EnumerateContainedAssemblies
Получает перечислитель для сборок, содержащихся в этой сборке.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT EnumerateContainedAssemblies(  
    ICorDebugAssemblyEnum **ppAssemblies  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppAssemblies`  
 [out] Указатель на адрес объекта интерфейса ICorDebugAssemblyEnum, который является перечислителем.  
  
## <a name="return-value"></a>Возвращаемое значение  
 `S_OK` Если этот `ICorDebugAssembly3` объект является контейнером; в противном случае `S_FALSE`, и перечисление будет пустым.  
  
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
