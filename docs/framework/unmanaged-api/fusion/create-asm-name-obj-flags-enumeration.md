---
title: "Перечисление CREATE_ASM_NAME_OBJ_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CREATE_ASM_NAME_OBJ_FLAGS
api_location: fusion.dll
api_type: COM
f1_keywords: CREATE_ASM_NAME_OBJ_FLAGS
helpviewer_keywords: CREATE_ASM_NAME_OBJ_FLAGS enumeration [.NET Framework fusion]
ms.assetid: a5ed2fd0-c7d2-4603-aaca-5d0caad92675
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4982b33643d855be4b8cace59f1c5cac4201d5ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="createasmnameobjflags-enumeration"></a>Перечисление CREATE_ASM_NAME_OBJ_FLAGS
Задает атрибуты [IAssemblyName-интерфейс](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) объекта при построении с [CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md) функции.  
  
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
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`CANOF_PARSE_DISPLAY_NAME`|Указывает, что переданный параметр является текстовым идентификатором.|  
|`CANOF_SET_DEFAULT_VALUES`|Задает несколько значений по умолчанию.|  
|`CANOF_VERIFY_FRIEND_ASSEMBLYNAME`|Проверяет правило дружественной сборки (только имя и открытый ключ). Этот член представляет только для внутреннего использования.|  
|`CANOF_PARSE_FRIEND_DISPLAY_NAME`|Сочетание `CANOF_PARSE_DISPLAY_NAME` и `CANOF_VERIFY_FRIEND_ASSEMBLYNAME` флаги. Этот член представляет только для внутреннего использования.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** Fusion.h  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IAssemblyName-интерфейс](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)  
 [Функция CreateAssemblyNameObject](../../../../docs/framework/unmanaged-api/fusion/createassemblynameobject-function.md)  
 [Перечисления Fusion](../../../../docs/framework/unmanaged-api/fusion/fusion-enumerations.md)
