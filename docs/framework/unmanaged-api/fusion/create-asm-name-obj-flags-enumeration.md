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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: aebc6dfe4830e6477cda8fd279b8ef2a8040895c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914567"
---
# <a name="createasmnameobjflags-enumeration"></a>Перечисление CREATE_ASM_NAME_OBJ_FLAGS
Указывает атрибуты [IAssemblyName-интерфейс](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта при построении с [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) функции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
  
    CANOF_PARSE_DISPLAY_NAME            = 0x1,  
    CANOF_SET_DEFAULT_VALUES            = 0x2,  
    CANOF_VERIFY_FRIEND_ASSEMBLYNAME    = 0x4,  
    CANOF_PARSE_FRIEND_DISPLAY_NAME     =   
        CANOF_PARSE_DISPLAY_NAME | CANOF_VERIFY_FRIEND_ASSEMBLYNAME  
  
} CREATE_ASM_NAME_OBJ_FLAGS;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|Указывает, что переданный параметр является текстовым идентификатором.|  
|`CANOF_SET_DEFAULT_VALUES`|Задает несколько значений по умолчанию.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|Проверяет правило дружественной сборки (только имя и открытый ключ). Этот член является только для внутреннего использования.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|Сочетание `CANOF_PARSE_DISPLAY_NAME` и `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` флаги. Этот член является только для внутреннего использования.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Fusion.h  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [Функция CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)
- [Перечисления Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
