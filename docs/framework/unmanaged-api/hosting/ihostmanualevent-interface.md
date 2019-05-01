---
title: Интерфейс IHostManualEvent
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad580f7cab81323e09a24dc12db39f223be3aeb4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61973073"
---
# <a name="ihostmanualevent-interface"></a>Интерфейс IHostManualEvent
Предоставляет реализацию главного приложения является представлением событие со сбросом вручную.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Reset](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|Сбрасывает текущий `IHostManualEvent` экземпляра в сигнальное состояние.|  
|[Метод Set](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|Задает текущий `IHostManualEvent` экземпляр сигнальное состояние.|  
|[Метод Wait](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|Вызывает текущий `IHostManualEvent` экземпляр ждать, пока он принадлежал или определенный промежуток времени.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Интерфейс IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [Интерфейс IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [Интерфейс IHostSyncManager](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
