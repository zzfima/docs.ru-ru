---
title: Перечисление CorDebugNGenPolicy
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CorDebugNGenPolicy
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugNGenPolicy
helpviewer_keywords:
- CorDebugNgenPolicy enumeration [.NET Framework debugging]
ms.assetid: edb4e4d2-3166-44d4-8b17-bf302f7ea093
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 1ae40916807a86d1c9828080a6cb9e5c1d14c2ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54671230"
---
# <a name="cordebugngenpolicy-enumeration"></a>Перечисление CorDebugNGenPolicy
Предоставляет значение, который определяет, загружает ли отладчик образы в машинном коде (NGen) из кэша образов в машинном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a>Участники  
  
|Имя члена|Описание|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|В [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] приложению, использование образов из локального кэша машинных образов отключен. В настольном приложении этот параметр не влияет.|  
  
## <a name="remarks"></a>Примечания  
 `CorDebugNGENPolicy` Перечисление, используемое [ICorDebugProcess5::EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) метод. Отключение использования образов из локального кэша машинных образов предоставляет для согласованности, гарантируя, что отладчик загружает отлаживаемых изображений, JIT-компиляции, вместо оптимизированные машинные образы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
