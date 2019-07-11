---
title: Перечисление CorDebugCodeInvokePurpose
ms.date: 03/30/2017
api_name:
- CorDebugInvokePurpose
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 31833a2d-a0d6-48a1-b05f-995ca307a08f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 593644802fa490c80b361bfdad3473abe4e82922
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67740280"
---
# <a name="cordebugcodeinvokepurpose-enumeration"></a>Перечисление CorDebugCodeInvokePurpose
Описывает, почему экспортируемая функция вызывает управляемый код.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum CorDebugCodeInvokePurpose  
{  
    CODE_INVOKE_PURPOSE_NONE,  
    CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION,    
    CODE_INVOKE_PURPOSE_CLASS_INIT,  
    CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH,  
} CorDebugCodeInvokePurpose;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`CODE_INVOKE_PURPOSE_NONE`|Отсутствует или неизвестно.|  
|`CODE_INVOKE_PURPOSE_NATIVE_TO_MANAGED_TRANSITION`|Управляемый код будет выполнять любую управляемую точку входа, например, обратный p-invoke. Любые дополнительные цели неизвестны среде выполнения.|  
|`CODE_INVOKE_PURPOSE_CLASS_INIT`|Управляемый код будет выполнять статический конструктор.|  
|`CODE_INVOKE_PURPOSE_INTERFACE_DISPATCH`|Управляемый код будет выполнять реализацию некоторого метода интерфейса, который был вызван.|  
  
## <a name="remarks"></a>Примечания  
 Это перечисление используется с [ICorDebugProcess6::GetExportStepInfo](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess6-getexportstepinfo-method.md) метод, чтобы предоставить сведения о пошаговом выполнении управляемого кода.  
  
> [!NOTE]
>  Это перечисление предназначено для использования только в сценариях отладки .NET Native.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [Отладка](../../../../docs/framework/unmanaged-api/debugging/index.md)
