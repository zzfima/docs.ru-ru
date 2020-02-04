---
title: Метод ICorDebugDebugEvent::GetThread
ms.date: 03/30/2017
ms.assetid: 4f2e9a2c-8369-4a07-a881-ad5422626353
ms.openlocfilehash: 0900ac2ae5bcf2141e720dad6efdf68d4fafaccc
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793534"
---
# <a name="icordebugdebugeventgetthread-method"></a>Метод ICorDebugDebugEvent::GetThread
Получает поток, в котором произошло событие.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetThread(  
        [out]ICorDebugThread **ppThread  
);  
```  
  
## <a name="parameters"></a>Параметры  
 ppThread  
 [выходной] Указатель на адрес объекта ICorDebugThread, представляющего поток, в котором произошло событие.  
  
## <a name="remarks"></a>Заметки  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugDebugEvent](icordebugdebugevent-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
