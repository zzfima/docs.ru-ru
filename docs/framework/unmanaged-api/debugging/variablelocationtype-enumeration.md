---
title: Перечисление VariableLocationType
ms.date: 03/30/2017
api_name:
- VariableLocationType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- VariableLocationType
helpviewer_keywords:
- VariableLocationType enumeration [.NET Framework debugging]
ms.assetid: 8635ee3a-c84b-4626-876c-416bee54f787
topic_type:
- apiref
ms.openlocfilehash: 1aa59ee559abff8006f0ac63a812e4315aa48154
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790312"
---
# <a name="variablelocationtype-enumeration"></a>Перечисление VariableLocationType
Указывает тип собственного расположения переменной.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum VariableLocationType  
{  
    VLT_REGISTER,               
    VLT_REGISTER_RELATIVE,      
    VLT_INVALID  
} VariableLocationType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`VLT_REGISTER`|Переменная находится в регистре.|  
|`VLT_REGISTER_RELATIVE`|Переменная находится в расположении в памяти относительно регистра.|  
|`VLT_INVALID`|Переменная не хранится в регистре или расположении в памяти относительно регистра.|  
  
## <a name="remarks"></a>Заметки  
 Член перечисления `VariableLocationType` возвращается методом [ICorDebugVariableHome:: жетлокатионтипе](icordebugvariablehome-getlocationtype-method.md) .  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** CorDebug.idl, CorDebug.h  
  
 **Библиотека:** CorGuids.lib  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>См. также:

- [Перечисления отладки](debugging-enumerations.md)
