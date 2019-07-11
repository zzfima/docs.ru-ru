---
title: Перечисление ValidatorFlags
ms.date: 03/30/2017
api_name:
- ValidatorFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ValidatorFlags
helpviewer_keywords:
- ValidatorFlags enumeration [.NET Framework hosting]
ms.assetid: a3f5c266-3fcc-4ad1-aaf5-4cdbe26304ad
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c5f38231eb6a5911527c21ee3304fc77cfcf8e90
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67776519"
---
# <a name="validatorflags-enumeration"></a>Перечисление ValidatorFlags
Содержит значения, указывающие тип проверки, которое должно выполняться при вызове [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum ValidatorFlags {  
    VALIDATOR_EXTRA_VERBOSE =       0x00000001,  
    VALIDATOR_SHOW_SOURCE_LINES =   0x00000002,  
    VALIDATOR_CHECK_ILONLY =        0x00000004,  
    VALIDATOR_CHECK_PEFORMAT_ONLY = 0x00000008,  
    VALIDATOR_NOCHECK_PEFORMAT =    0x00000010,  
};  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`VALIDATOR_CHECK_ILONLY`|Указывает, что должна быть проверена только промежуточный язык Майкрософт (MSIL) в исполняемом файле.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|Указывает, что должна быть проверена только формат исполняемого файла.|  
|`VALIDATOR_EXTRA_VERBOSE`|Указывает, что выполнены все типы проверки и они будут составляться.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|Указывает, что формат исполняемого файла не должна быть проверена.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|Указывает, что сообщения об ошибках проверки должны содержать строки исходного кода, которые вызывают ошибки проверки. Значение этого поля не допускается в .NET Framework версии 2.0.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** IValidator.idl в файле IValidator.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
