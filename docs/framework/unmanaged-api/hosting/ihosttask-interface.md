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
ms.openlocfilehash: 18dfee606f3d41229aa58a5b4bb9380b87c4efa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121393"
---
# <a name="ihosttask-interface"></a>Интерфейс IHostTask
Предоставляет методы, позволяющие среде CLR взаимодействовать с узлом для управления задачами.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Запрашивает выход узла из задачи, представленной текущим экземпляром `IHostTask`, поэтому задачу можно прервать.|  
|[Метод GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Возвращает уровень приоритета потока задачи, представленной текущим экземпляром `IHostTask`.|  
|[Метод Join](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Блокирует вызывающую задачу до тех пор, пока задача, представленная текущим экземпляром `IHostTask`, не завершится, заданный интервал времени истечет или будет вызван метод [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) .|  
|[Метод SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Связывает экземпляр [интерфейса ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) с текущим экземпляром `IHostTask`.|  
|[Метод SetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Запрашивает у узла настройку уровня приоритета потока для задачи, представленной текущим экземпляром `IHostTask`.|  
|[Метод Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Запрашивает, что узел перемещает задачу, представленную текущим экземпляром `IHostTask`, из приостановленного состояния в активное состояние, в котором можно выполнить код.|  
  
## <a name="remarks"></a>Заметки  
 Среда CLR вызывает методы, определенные `IHostTask`, для запуска задачи, установки ее уровня приоритета и т. д.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
