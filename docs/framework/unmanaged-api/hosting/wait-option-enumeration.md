---
title: Перечисление WAIT_OPTION
ms.date: 03/30/2017
api_name:
- WAIT_OPTION
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- WAIT_OPTION
helpviewer_keywords:
- WAIT_OPTION enumeration [.NET Framework hosting]
ms.assetid: 962fc293-8ded-4b3b-90ce-2c21a4f1b244
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fb37394799db39baa406ef332066d5ebb2dbf19d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441933"
---
# <a name="waitoption-enumeration"></a>Перечисление WAIT_OPTION
Содержит значения, указывающие, что необходимо выполнить действия узла, если операцию, запрошенную среды выполнения (CLR) блоками выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Уведомляет основное приложение, задачи должны быть выведены из спящего режима средой CLR [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) метод.|  
|`WAIT_MSGPUMP`|Уведомляет узел, что он должен выдавать сообщения в текущем потоке операционной системы, при блокировании. Среда выполнения определяет это значение только для <xref:System.Threading.ApartmentState.STA> потока.|  
|`WAIT_NOTINDEADLOCK`|Уведомляет узел, что заданный запрос синхронизации не может быть разбит узел. То есть узел не может возвращать `HOST_E_DEADLOCK`.|  
  
## <a name="remarks"></a>Примечания  
 [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) и [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) оба метода принимают параметр типа.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
