---
title: Интерфейс IHostTask
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df1fb24c4003f77523ef01a4029fd19cc55a3fef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442225"
---
# <a name="ihosttask-interface"></a>Интерфейс IHostTask
Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для взаимодействия с основным приложением для управления задачами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Запросы, что узел пробуждения задач, представленный текущим `IHostTask` экземпляра, поэтому задача может быть прервана.|  
|[Метод GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Возвращает уровень приоритета потока задачи, представленный текущим `IHostTask` экземпляра.|  
|[Метод Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Блокирует вызывающий задачу до выполнения задачи, представленный текущим `IHostTask` завершения экземпляра, истечения заданного интервала, или [IHostTask::Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) вызывается.|  
|[Метод SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Связывает [ICLRTask-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра с текущим `IHostTask` экземпляра.|  
|[Метод SetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Уровень запросов, настройки, узле приоритет потока для задачи, представленный текущим `IHostTask` экземпляра.|  
|[Метод Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Запросы, что узел перемещения задач, представленный текущим `IHostTask` экземпляр из приостановленного состояния к активному состоянию, в котором можно выполнять код.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR вызывает методы, определенные `IHostTask` запустить задачу, установите его приоритет потока уровень, и т. д.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
