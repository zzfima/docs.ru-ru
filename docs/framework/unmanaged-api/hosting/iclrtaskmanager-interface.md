---
title: "Интерфейс ICLRTaskManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRTaskManager
helpviewer_keywords: ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3144338ddce262aaa6772f588a4f1a652cc57e01
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrtaskmanager-interface"></a>Интерфейс ICLRTaskManager
Предоставляет методы, позволяющие основному приложению явным образом запросить общеязыковой среды выполнения (CLR) создайте новую задачу, выполняемую задачу и задать географического язык и региональные параметры для задачи.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод CreateTask](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|Явно запрашивает, создайте новый том, что среда CLR [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра.|  
|[Метод GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|Возвращает `ICLRTask` экземпляр, представляющий выполняющийся в данный момент задачу.|  
|[Getcurrenttasktype-метод](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|Получает тип задачи, выполняемой в данный момент.|  
|[SetLocale-метод](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|Уведомляет среду CLR, узла изменило идентификатор языкового стандарта в текущей выполняемой задаче.|  
|[Метод SetUILocale](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|Уведомляет общеязыковая среда выполнения о том, что узел изменил идентификатор языкового стандарта интерфейса пользователя в текущей выполняемой задачи.|  
  
## <a name="remarks"></a>Примечания  
 Каждая задача, на котором работает в размещенной среде имеет оба представления на стороне узла (экземпляр [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) и на стороне среды CLR (экземпляр [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)). Узел или среда CLR может инициировать создание задачи, но представление главного узла должен быть связан с соответствующей представление на стороне среды CLR для обеспечения успешного обмена данными между узлом и CLR связи с этой задачей. Два объекта должно быть создано и создать ее экземпляр перед управляемый код может выполнять в потоке операционной системы.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICLRTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [IHostTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
