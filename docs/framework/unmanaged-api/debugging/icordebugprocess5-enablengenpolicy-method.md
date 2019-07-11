---
title: Метод ICorDebugProcess5::EnableNGENPolicy
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5::EnableNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::EnableNGENPolicy
helpviewer_keywords:
- ICorDebugProcess5::EnableNGENPolicy method [.NET Framework debugging]
- EnableNGENPolicy method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 3b8e15ca-3c72-4685-a937-da4c739cb9e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 38ff08fa7e7db986006c4e0e09b1ac9cf1be801e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767146"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a>Метод ICorDebugProcess5::EnableNGENPolicy
Задает значение, определяющее, каким образом приложение загружает образы в машинном коде во время работы под контролем управляемого отладчика.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ePolicy`  
 [in] Объект [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) константа, определяющая, как приложение загружает образы в машинном коде во время работы под контролем управляемого отладчика.  
  
## <a name="remarks"></a>Примечания  
 Если политики установлено успешно, метод возвращает `S_OK`. Если `ePolicy` находится вне диапазона значений перечисления, определенных в [CorDebugNGenPolicy](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), метод возвращает `E_INVALIDARG` и вызов метода не оказывает влияния. Если невозможно обновить политику генератором машинных образов (Ngen.exe), метод возвращает `E_FAIL`.  
  
 `ICorDebugProcess5::EnableNGenPolicy` Метод может вызываться в любое время в течение времени существования процесса. Политика действует для каких-либо модулей, которые будут загружены после набора политик.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
