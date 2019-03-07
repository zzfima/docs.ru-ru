---
title: Метод ICorDebugModuleDebugEvent::GetModule
ms.date: 03/30/2017
ms.assetid: b1141c35-4253-4e34-b3e4-ed406a9dea4f
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e99477bd8750f79ae711d47f295b6b39b90c92c3
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/06/2019
ms.locfileid: "57492131"
---
# <a name="icordebugmoduledebugeventgetmodule-method"></a>Метод ICorDebugModuleDebugEvent::GetModule
Возвращает объединенный модуль, который только что был загружен или выгружен.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetModule(  
   [out]ICorDebugModule **ppModule  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `ppModule`  
 [out] Указатель на адрес ICorDebugModule объект, представляющий объединенный модуль, который был только что загружен или выгружен.  
  
## <a name="remarks"></a>Примечания  
 Можно вызвать [GetEventKind](../../../../docs/framework/unmanaged-api/debugging/icordebugdebugevent-geteventkind-method.md) метод, чтобы определить, был ли модуль загрузке или выгрузке.  
  
> [!NOTE]
>  Этот метод доступен только в .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейс ICorDebugModuleDebugEvent](../../../../docs/framework/unmanaged-api/debugging/icordebugmoduledebugevent-interface.md)
- [Интерфейсы отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
