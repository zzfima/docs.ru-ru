---
title: Метод ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
ms.openlocfilehash: 4d9eea8fb5c42002763a0ae52a186bf2c1e6d2ee
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792908"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a>Метод ICorDebugModuleDebugEvent::GetModule
Возвращает объединенный модуль, который только что был загружен или выгружен.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppModule`  
 [out] Указатель на адрес объекта ICorDebugModule, представляющего объединенный модуль, который был только что загружен или выгружен.  
  
## <a name="remarks"></a>Заметки  
 Можно вызвать метод [GetEventKind](icordebugdebugevent-geteventkind-method.md) , чтобы определить, был ли модуль загружен или выгружен.  
  
> [!NOTE]
> Этот метод доступен только в машинном коде .NET.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Интерфейс ICorDebugModuleDebugEvent](icordebugmoduledebugevent-interface.md)
- [Интерфейсы отладки](debugging-interfaces.md)
