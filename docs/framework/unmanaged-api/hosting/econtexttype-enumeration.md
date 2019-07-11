---
title: Перечисление EContextType
ms.date: 03/30/2017
api_name:
- EContextType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- EContextType
helpviewer_keywords:
- EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f93f36a78ff5579e131ef4bb3d48f04e806c14de
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779392"
---
# <a name="econtexttype-enumeration"></a>Перечисление EContextType
Описывает контекст безопасности текущего потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`eCurrentContext`|Указывает контекст в текущем потоке во время общеязыковой среды выполнения (CLR) вызывает [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) метода или контекста, запрошенный в среде CLR при вызове [ IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) метод.|  
|`eRestrictedContext`|Указывает контекст, в течение которого узел имеет привилегии более низкого уровня, таких как сборщик мусора, то есть конструктор класса или модуля.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR предоставляет один из `EContextType` значения как значение параметра в вызовах `IHostSecurityManager::GetSecurityContext` и `IHostSecurityManager::SetSecurityContext` методы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс IHostSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)
- [Интерфейс IHostSecurityManager](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
