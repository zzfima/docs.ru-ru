---
title: Перечисление EApiCategories
ms.date: 03/30/2017
api_name:
- EApiCategories
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EApiCategories
helpviewer_keywords:
- EApiCategories enumeration [.NET Framework hosting]
ms.assetid: 3c4a8a5a-8a46-4ac9-947f-4959bc9d6ac6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3debd3f13d78841188dd8c900f51c0110e1d4c67
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59086459"
---
# <a name="eapicategories-enumeration"></a>Перечисление EApiCategories
Описывает категории возможностей, которые узел может блокировать при выполнении в частично доверенным кодом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    eNoCategory               = 0,  
    eSynchronization          = 0x1,  
    eSharedState              = 0x2,  
    eExternalProcessMgmt      = 0x4,  
    eSelfAffectingProcessMgmt = 0x8,  
    eExternalThreading        = 0x10,  
    eSelfAffectingThreading   = 0x20,  
    eSecurityInfrastructure   = 0x40,  
    eUI                       = 0x80,  
    eMayLeakOnAbort           = 0x100,  
    eAll                      = 0x1ff  
} EHostProtectionCategories;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`eAll`|Указывает, что все управляемые классы и члены, которые покрыты другие `EApiCategories` поля будет блокироваться в частично доверенным кодом.|  
|`eExternalProcessMgmt`|Указывает, что управляемые классы и члены, позволяющие создания, обработки и деструкция внешних процессов заблокирован для выполнения в частично доверенным кодом.|  
|`eExternalThreading`|Указывает, что управляемые классы и члены, позволяющие создания, обработки и уничтожение потоков внешних заблокирован для выполнения в частично доверенным кодом.|  
|`eMayLeakOnAbort`|Указывает, что управляемые типы и члены, которые потенциально могут привести к утечке памяти при прерывании работы заблокирован для выполнения в частично доверенным кодом.|  
|`eNoCategory`|Указывает, что категории управляемого кода не будет блокироваться в частично доверенным кодом.|  
|`eSecurityInfrastructure`|Указывает, что заблокирован инфраструктуре безопасности среды выполнения (CLR) не могут использоваться частично доверенным кодом.|  
|`eSelfAffectingProcessMgmt`|Указывает, что управляемых классов и членов, возможности которых могут повлиять на размещенный процесс заблокирован для выполнения в частично доверенным кодом.|  
|`eSelfAffectingThreading`|Указывает, что выполнение управляемых классов и членов, возможности которых могут повлиять на потоки в размещенном процессе будет блокироваться в частично доверенным кодом.|  
|`eSharedState`|Указывает, что управляемые классы и члены, предоставляющие доступ к общему состоянию заблокирован для выполнения в частично доверенным кодом.|  
|`eSynchronization`|Указывает, что общие классы CLR и члены, позволяющие код для удержания блокировок заблокирован для выполнения в частично доверенным кодом.|  
|`eUI`|Указывает, что управляемых классов и членов, которые разрешают или требуется участие пользователя заблокирован для выполнения в частично доверенным кодом.|  
  
## <a name="remarks"></a>Примечания  
 [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) метод принимает параметр типа `EApiCategories`.  
  
 `EApiCategories` Перечисления и `SetProtectedCategories` метод непосредственно связаны в управляемый <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> класса. Управляемый класс используется с <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> перечисления, значения которых соответствуют `EApiCategories` значения, чтобы пометить управляемых типов и членов, которые предоставляют возможности, соответствующие категории, описанные по `EApiCategories`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
