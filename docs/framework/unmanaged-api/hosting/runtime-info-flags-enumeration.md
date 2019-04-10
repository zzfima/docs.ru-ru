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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9483cf8671b7d3ad5430081d93925af30b3d8368
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59215694"
---
# <a name="runtimeinfoflags-enumeration"></a>Перечисление RUNTIME_INFO_FLAGS
Содержит значения, указывающие, какие сведения об общеязыковой среде выполнения (CLR) должны быть возвращены.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|Указывает, что сведения о каталоге не будут включены.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|Указывает, что сведения о версии не следует включать.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|Указывает, что диалоговое окно ошибки, не должны быть видны в случае сбоя.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|Указывает, что последствия вызова [SetErrorMode](https://go.microsoft.com/fwlink/p/?LinkId=255242) функция флаг SEM_FAILCRITICALERRORS, следует переопределить. То есть диалоговое окно установки должен отображаться в случае сбоя, а не было подавлено.|  
|`RUNTIME_INFO_REQUEST_AMD64`|Указывает запрос для получения сведений об AMD-64-совместимые версии среды выполнения.|  
|`RUNTIME_INFO_REQUEST_IA64`|Указывает запрос для получения сведений об IA-64-совместимые версии среды выполнения.|  
|`RUNTIME_INFO_REQUEST_X86`|Указывает запрос для получения сведений об x86-совместимой версии среды выполнения.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|Указывает, что сведения об обновлении версии должны быть включены.|  
  
## <a name="remarks"></a>Примечания  
 Далее перечислены флаги архитектуры платформы может быть указанного только один за другим и нельзя использовать вместе:  
  
-   RUNTIME_INFO_REQUEST_IA64  
  
-   RUNTIME_INFO_REQUEST_AMD64  
  
-   RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
