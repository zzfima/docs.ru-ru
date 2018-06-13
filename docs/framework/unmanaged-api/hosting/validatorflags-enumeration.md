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
ms.openlocfilehash: 20ce52108c1024ad3e07051b226aa65612580e2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441395"
---
# <a name="validatorflags-enumeration"></a>Перечисление ValidatorFlags
Содержит значения, указывающие тип проверки, которые должны быть выполнены при обращении к [ICLRValidator::Validate](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
|`VALIDATOR_CHECK_ILONLY`|Указывает, что должны быть проверены только промежуточный язык Майкрософт (MSIL) в исполняемом файле.|  
|`VALIDATOR_CHECK_PEFORMAT_ONLY`|Указывает, что должны быть проверены только формат исполняемого файла.|  
|`VALIDATOR_EXTRA_VERBOSE`|Указывает, следует выполнить и на всех типов проверки.|  
|`VALIDATOR_NOCHECK_PEFORMAT`|Указывает, что формат исполняемого файла не должна быть проверена.|  
|`VALIDATOR_SHOW_SOURCE_LINES`|Указывает, что сообщения об ошибках проверки должны содержать строки исходного кода, которые вызывают ошибки проверки. Значение этого поля не поддерживается в .NET Framework версии 2.0.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** IValidator.idl, IValidator.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
