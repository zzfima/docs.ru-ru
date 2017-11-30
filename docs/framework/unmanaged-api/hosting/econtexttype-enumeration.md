---
title: "Перечисление EContextType"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EContextType
api_location: mscoree.dll
api_type: COM
f1_keywords: EContextType
helpviewer_keywords: EContextType enumeration [.NET Framework hosting]
ms.assetid: 92b926a9-b87e-408a-9036-df7b752c9492
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 73e6e9a1f1118a524b86b3711c0c7a6af4777f2d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="econtexttype-enumeration"></a>Перечисление EContextType
Описывает контекст безопасности текущего потока.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    eCurrentContext    = 0x00,  
    eRestrictedContext = 0x01  
} EContextType;  
```  
  
## <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|`eCurrentContext`|Указывает контекст в текущем потоке во время общеязыковая среда выполнения (CLR) вызывает [IHostSecurityManager::GetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-getsecuritycontext-method.md) метода или контекста, запрошенный средой CLR в вызове [ IHostSecurityManager::SetSecurityContext](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-setsecuritycontext-method.md) метод.|  
|`eRestrictedContext`|Указывает контекст, в течение которого узел должен иметь привилегии более низкого уровня, таких как сборщик мусора или конструктор класса или модуля.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR предоставляет один из `EContextType` значения как значение параметра в вызовах `IHostSecurityManager::GetSecurityContext` и `IHostSecurityManager::SetSecurityContext` методы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [IHostSecurityContext-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritycontext-interface.md)  
 [IHostSecurityManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)  
 [Перечисления размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
