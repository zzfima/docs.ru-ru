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
ms.openlocfilehash: 583819e8e7ab16a8ac1ce72892f4353e3043ce3d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129690"
---
# <a name="icordebugprocess5enablengenpolicy-method"></a>Метод ICorDebugProcess5::EnableNGENPolicy
Задает значение, определяющее, как приложение загружает образы в машинном кодах при выполнении в управляемом отладчике.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT EnableNGENPolicy(  
    [in] CorDebugNGENPolicy ePolicy  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ePolicy`  
 окне Константа [кордебугнженполици](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md) , определяющая, как приложение загружает образы в машинном кодах при работе в управляемом отладчике.  
  
## <a name="remarks"></a>Заметки  
 Если политика успешно установлена, метод возвращает `S_OK`. Если `ePolicy` находится за пределами диапазона перечисляемых значений, определенных параметром [кордебугнженполици](../../../../docs/framework/unmanaged-api/debugging/cordebugngenpolicy-enumeration.md), метод возвращает `E_INVALIDARG` и вызов метода не оказывает никакого влияния. Если не удается обновить политику генератора образов в машинном код (Ngen. exe), метод возвращает `E_FAIL`.  
  
 Метод `ICorDebugProcess5::EnableNGenPolicy` можно вызвать в любое время во время существования процесса. Политика действует для всех модулей, загруженных после установки политики.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
