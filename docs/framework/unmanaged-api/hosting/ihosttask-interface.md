---
title: "Интерфейс IHostTask"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTask
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTask
helpviewer_keywords: IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5f072a6550f840550b91473ea4a802ec97611d19
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihosttask-interface"></a>Интерфейс IHostTask
Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для взаимодействия с основным приложением для управления задачами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Запросы, что узел пробуждения задач, представленный текущим `IHostTask` экземпляра, поэтому задача может быть прервана.|  
|[GetPriority-метод](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Возвращает уровень приоритета потока задачи, представленный текущим `IHostTask` экземпляра.|  
|[Метод Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Блокирует вызывающий задачу до выполнения задачи, представленный текущим `IHostTask` завершения экземпляра, истечения заданного интервала, или [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) вызывается.|  
|[SetCLRTask-метод](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Связывает [ICLRTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра с текущим `IHostTask` экземпляра.|  
|[Метод SetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Уровень запросов, настройки, узле приоритет потока для задачи, представленный текущим `IHostTask` экземпляра.|  
|[Start-метод](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Запросы, что узел перемещения задач, представленный текущим `IHostTask` экземпляр из приостановленного состояния к активному состоянию, в котором можно выполнять код.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR вызывает методы, определенные `IHostTask` запустить задачу, установите его приоритет потока уровень, и т. д.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [ICLRTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTaskManager-интерфейс](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
