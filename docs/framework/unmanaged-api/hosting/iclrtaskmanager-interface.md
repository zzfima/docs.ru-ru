---
title: Интерфейс ICLRTaskManager
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14c2c9b70ac2e57983ea4b16772add6a1dff5ff4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438071"
---
# <a name="iclrtaskmanager-interface"></a>Интерфейс ICLRTaskManager
Предоставляет методы, позволяющие основному приложению явным образом запросить общеязыковой среды выполнения (CLR) создайте новую задачу, выполняемую задачу и задать географического язык и региональные параметры для задачи.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateTask](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|Явно запрашивает, создайте новый том, что среда CLR [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра.|  
|[Метод GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|Возвращает `ICLRTask` экземпляр, представляющий выполняющийся в данный момент задачу.|  
|[Метод GetCurrentTaskType](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|Получает тип задачи, выполняемой в данный момент.|  
|[Метод SetLocale](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|Уведомляет среду CLR, узла изменило идентификатор языкового стандарта в текущей выполняемой задаче.|  
|[Метод SetUILocale](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|Уведомляет общеязыковая среда выполнения о том, что узел изменил идентификатор языкового стандарта интерфейса пользователя в текущей выполняемой задачи.|  
  
## <a name="remarks"></a>Примечания  
 Каждая задача, на котором работает в размещенной среде имеет оба представления на стороне узла (экземпляр [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) и на стороне среды CLR (экземпляр [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)). Узел или среда CLR может инициировать создание задачи, но представление главного узла должен быть связан с соответствующей представление на стороне среды CLR для обеспечения успешного обмена данными между узлом и CLR связи с этой задачей. Два объекта должно быть создано и создать ее экземпляр перед управляемый код может выполнять в потоке операционной системы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
