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
ms.openlocfilehash: f25348410387a7b0e03ef897e8534336baeb126a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432213"
---
# <a name="eapicategories-enumeration"></a>Перечисление EApiCategories
Описывает категории возможностей, которые узел может блокировать при выполнении в частично доверенном коде.  
  
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
|`eAll`|Указывает, что все управляемые классы и члены, которые рассматриваются другими `EApiCategories` поля будет блокироваться в частично доверенном коде.|  
|`eExternalProcessMgmt`|Указывает, что управляемых классов и членов, которые позволяют создания, изменения и удаления из внешних процессов блокироваться в частично доверенном коде.|  
|`eExternalThreading`|Указывает, что управляемые классы и члены, позволяющие создания, изменения и удаления внешние потоки блокироваться в частично доверенном коде.|  
|`eMayLeakOnAbort`|Указывает, что управляемые типы и члены, которые потенциально могут вызвать утечку памяти при прерывании блокироваться в частично доверенном коде.|  
|`eNoCategory`|Указывает, что категории управляемого кода не будет блокироваться в частично доверенном коде.|  
|`eSecurityInfrastructure`|Блокировка инфраструктуру безопасности среды выполнения (CLR) от использования кодом с частичным доверием.|  
|`eSelfAffectingProcessMgmt`|Указывает, что управляемых классов и членов, возможности которых могут повлиять на размещенный процесс блокироваться в частично доверенном коде.|  
|`eSelfAffectingThreading`|Указывает, что управляемых классов и членов, возможности которых могут повлиять на потоки в размещенном процессе блокироваться в частично доверенном коде.|  
|`eSharedState`|Указывает, заблокирован управляемых классов и членов, которые предоставляют общее состояние при выполнении в частично доверенный код.|  
|`eSynchronization`|Указывает, что общие классы CLR и члены, позволяющие код для удержания блокировок блокироваться в частично доверенном коде.|  
|`eUI`|Указывает, что управляемых классов и членов, которые разрешают или требующих такого взаимодействия блокироваться в частично доверенном коде.|  
  
## <a name="remarks"></a>Примечания  
 [ICLRHostProtectionManager::SetProtectedCategories](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md) метод принимает параметр типа `EApiCategories`.  
  
 `EApiCategories` Перечисления и `SetProtectedCategories` метод непосредственно связаны в управляемом <xref:System.Security.Permissions.HostProtectionAttribute?displayProperty=nameWithType> класса. Управляемый класс используется с <xref:System.Security.Permissions.HostProtectionResource?displayProperty=nameWithType> перечисления, значения которого соответствуют непосредственно `EApiCategories` значения, чтобы пометить управляемых типов и членов, которые предоставляют возможности, соответствующие категориям, описываемого `EApiCategories`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md)  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
