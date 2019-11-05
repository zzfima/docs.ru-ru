---
title: Перечисление CREATE_ASM_NAME_OBJ_FLAGS
ms.date: 03/30/2017
api_name:
- CREATE_ASM_NAME_OBJ_FLAGS
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords:
- CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type:
- apiref
ms.openlocfilehash: f6abb59c3aaec40a4e7b228b8c69147a2d454431
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108885"
---
# <a name="create_asm_name_obj_flags-enumeration"></a>Перечисление CREATE_ASM_NAME_OBJ_FLAGS
Задает атрибуты объекта [интерфейса IAssemblyName](iassemblyname-interface.md) при создании с помощью функции [креатеассемблинамеобжект](createassemblynameobject-function.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|Указывает, что переданный параметр является текстовым идентификатором.|  
|`CANOF_SET_DEFAULT_VALUES`|Задает несколько значений по умолчанию.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|Проверяет правило дружественной сборки (только имя и открытый ключ). Этот член предназначен только для внутреннего использования.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|Сочетание флагов `CANOF_PARSE_DISPLAY_NAME` и `CANOF_VERIFY_FRIEND_ASSEMBLYNAME`. Этот член предназначен только для внутреннего использования.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../get-started/system-requirements.md).  
  
 **Заголовок:** Fusion. h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyName](iassemblyname-interface.md)
- [Функция CreateAssemblyNameObject](createassemblynameobject-function.md)
- [Перечисления Fusion](fusion-enumerations.md)
