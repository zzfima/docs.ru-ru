---
title: "Перечисление RUNTIME_INFO_FLAGS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: RUNTIME_INFO_FLAGS
api_location: mscoree.dll
api_type: COM
f1_keywords: RUNTIME_INFO_FLAGS
helpviewer_keywords: RUNTIME_INFO_FLAGS enumeration [.NET Framework hosting]
ms.assetid: adba37be-f775-4cdb-8919-5746ce694f33
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d050972857ba652ae0b40727260f681c383208b0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="runtimeinfoflags-enumeration"></a>Перечисление RUNTIME_INFO_FLAGS
Содержит значения, указывающие, какие сведения о среде (CLR) должны возвращаться.  
  
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
  
|Член|Описание:|  
|------------|-----------------|  
|`RUNTIME_INFO_DONT_RETURN_DIRECTORY`|Указывает, что сведения о каталоге не будут включены.|  
|`RUNTIME_INFO_DONT_RETURN_VERSION`|Указывает, что сведения о версии не будут включены.|  
|`RUNTIME_INFO_DONT_SHOW_ERROR_DIALOG`|Указывает, что не нужно отображать диалоговое окно ошибки при сбое.|  
|`RUNTIME_INFO_IGNORE_ERROR_MODE`|Указывает, что результаты вызова [SetErrorMode](http://go.microsoft.com/fwlink/p/?LinkId=255242) функция с флагом SEM_FAILCRITICALERRORS должен быть переопределен. То есть диалоговое окно установки должен отображаться после сбоя, а не блокируются.|  
|`RUNTIME_INFO_REQUEST_AMD64`|Указывает запрос для получения сведений об AMD-64-совместимые версии среды выполнения.|  
|`RUNTIME_INFO_REQUEST_IA64`|Указывает запрос для получения сведений об IA-64-совместимые версии среды выполнения.|  
|`RUNTIME_INFO_REQUEST_X86`|Указывает запрос для получения сведений об x86-совместимой версии среды выполнения.|  
|`RUNTIME_INFO_UPGRADE_VERSION`|Указывает, что сведения об обновлении версии должны быть включены.|  
  
## <a name="remarks"></a>Примечания  
 Следующие флаги архитектуры платформы можно указанного только по одному, а также нельзя использовать вместе:  
  
-   RUNTIME_INFO_REQUEST_IA64  
  
-   RUNTIME_INFO_REQUEST_AMD64  
  
-   RUNTIME_INFO_REQUEST_X86  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
