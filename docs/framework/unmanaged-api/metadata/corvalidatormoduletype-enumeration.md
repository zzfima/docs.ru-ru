---
title: Перечисление CorValidatorModuleType
ms.date: 03/30/2017
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 04bed418d96658e29328cf2ce6bba445639b437f
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750755"
---
# <a name="corvalidatormoduletype-enumeration"></a>Перечисление CorValidatorModuleType
Указывает тип модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|Модуль является недопустимым типом.|  
|`ValidatorModuleTypeMin`|Минимальное значение `CorValidatorModuleType` перечисления.|  
|`ValidatorModuleTypePE`|Модуль — это файл переносимого исполняемого (PE).|  
|`ValidatorModuleTypeObj`|Модуль является OBJ-файле.|  
|`ValidatorModuleTypeEnc`|Модуль является сеанс отладчика, изменить и продолжить.|  
|`ValidatorModuleTypeIncr`|Модуль — это приложения, пошаговое построение.|  
|`ValidatorModuleTypeMax`|Максимальное значение `CorValidatorModuleType` перечисления.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Cor.h  
  
 **Библиотека:** Включена как ресурс в MsCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Перечисления метаданных](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
