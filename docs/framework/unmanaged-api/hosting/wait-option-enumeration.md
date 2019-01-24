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
ms.openlocfilehash: 793d3996f9cbcb1a38a728ade06f775784166123
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745900"
---
# <a name="waitoption-enumeration"></a>Перечисление WAIT_OPTION
Содержит значения, указывающие, что действия узла следует предпринять операцию, запрошенную общих блоков языковой среды исполнения (CLR).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typedef enum {  
    WAIT_MSGPUMP       = 0x1,  
    WAIT_ALERTABLE     = 0x2,  
    WAIT_NOTINDEADLOCK = 0x4,  
} WAIT_OPTION;  
```  
  
## <a name="members"></a>Участники  
  
|Член|Описание:|  
|------------|-----------------|  
|`WAIT_ALERTABLE`|Уведомляет основное приложение, что задачи должны пробуждения, если среда CLR вызывает [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) метод.|  
|`WAIT_MSGPUMP`|Уведомляет основное приложение, что его необходимо передавать сообщения в текущем потоке операционной системы, если поток блокируется. Среда выполнения задает это значение только в <xref:System.Threading.ApartmentState.STA> потока.|  
|`WAIT_NOTINDEADLOCK`|Уведомляет основное приложение, что узел не может блокировать заданный запрос синхронизации. То есть узел не может возвращать `HOST_E_DEADLOCK`.|  
  
## <a name="remarks"></a>Примечания  
 [IHostTaskManager::Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md) и [IHostTaskManager::SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md) оба метода принимают параметр этого типа.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Размещение перечислений](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
