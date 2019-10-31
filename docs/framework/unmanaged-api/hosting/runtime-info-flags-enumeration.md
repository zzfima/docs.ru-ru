---
title: Перечисление RUNTIME_INFO_FLAGS
ms.date: 03/30/2017
api_name:
- RUNTIME_INFO_FLAGS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- RUNTIME_INFO_FLAGS
helpviewer_keywords:
- RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type:
- apiref
ms.openlocfilehash: 80643187045e7e96b9c18169c5e71287713d711f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73106236"
---
# <a name="runtime_info_flags-enumeration"></a>Перечисление RUNTIME_INFO_FLAGS
Содержит значения, которые указывают, какие сведения о среде CLR должны быть возвращены.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
  
    RUNTIME_INFO_UPGRADE_VERSION             = 0x01,  
    RUNTIME_INFO_REQUEST_IA64                = 0x02,  
    RUNTIME_INFO_REQUEST_AMD64               = 0x04,  
    RUNTIME_INFO_REQUEST_X86                 = 0x08,  
    RUNTIME_INFO_DONT_RETURN_DIRECTORY       = 0x10,  
    RUNTIME_INFO_DONT_RETURN_VERSION         = 0x20,  
    RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG      = 0x40,  
    RUNTIME_INFO_IGNORE_ERROR_MODE           = 0x1000  
  
} RUNTIME_INFO_FLAGS;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|Указывает, что сведения о каталоге не следует включать.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|Указывает, что сведения о версии указывать не следует.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|Указывает, что при сбое не должно отображаться диалоговое окно ошибки.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|Указывает, что эффекты вызова функции [функцию SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) с флагом SEM_FAILCRITICALERRORS должны быть переопределены. То есть диалоговое окно установки должно отображаться при сбое, а не подавлено.|  
|`RUNTIME_INFO_REQUEST_AMD64`|Указывает запрос сведений о версии среды выполнения, совместимой с AMD-64.|  
|`RUNTIME_INFO_REQUEST_IA64`|Указывает запрос сведений о версии среды выполнения, совместимой с IA-64.|  
|`RUNTIME_INFO_REQUEST_X86`|Указывает запрос сведений о версии среды выполнения, совместимой с x86.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|Указывает, что должны быть добавлены сведения об обновлении версии.|  
  
## <a name="remarks"></a>Заметки  
 Следующие флаги архитектуры платформы могут быть указаны только один за раз и не могут быть объединены:  
  
- RUNTIME_INFO_REQUEST_IA64  
  
- RUNTIME_INFO_REQUEST_AMD64  
  
- RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
