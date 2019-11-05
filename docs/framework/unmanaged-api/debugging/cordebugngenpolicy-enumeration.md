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
ms.openlocfilehash: 826dfceb28512e4fd3157c432b7a4d94fba704fd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73097863"
---
# <a name="cordebugngenpolicy-enumeration"></a>Перечисление CorDebugNGenPolicy
Предоставляет значение, который определяет, загружает ли отладчик образы в машинном коде (NGen) из кэша образов в машинном коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
enum CorDebugNGENPolicy {  
    DISABLE_LOCAL_NIC = 1  
} CorDebugNGENPolicy;  
```  
  
## <a name="members"></a>Члены  
  
|Имя члена|Описание|  
|-----------------|-----------------|  
|`DISABLE_LOCAL_NIC`|В [!INCLUDE[win8_appname_long](../../../../includes/win8-appname-long-md.md)] приложении использование образов из локального кэша образов в машинном кодах отключено. В классическом приложении этот параметр не действует.|  
  
## <a name="remarks"></a>Заметки  
 Перечисление `CorDebugNGENPolicy` используется методом [метод ICorDebugProcess5:: EnableNGENPolicy](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enablengenpolicy-method.md) . Отключение использования образов из локального кэша образов в машинном код обеспечивает единообразную отладку, гарантируя, что отладчик загружает отладочные скомпилированные КОМПИЛЯТОРом изображения вместо оптимизированных образов в машинном код.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления отладки](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
