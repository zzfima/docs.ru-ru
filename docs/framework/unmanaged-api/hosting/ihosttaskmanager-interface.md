---
title: Интерфейс IHostTaskManager
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da30e75bf4a58e66bb0dd8210368b162cf14c3f7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59091269"
---
# <a name="ihosttaskmanager-interface"></a>Интерфейс IHostTaskManager
Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR), для работы с задачами через узел вместо использования функции потоков или волокон стандартной операционной системе.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Уведомляет хост, что управляемый код к периоду, в котором должен не удается прервать текущую задачу.|  
|[Метод BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Уведомляет хост, что управляемый код к периоду, в котором текущей задачи не должен быть перемещена в другой поток операционной системы.|  
|[Метод CallNeedsHostHook](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Ведущее приложение может указать, может ли среда CLR вводить заданный вызов в неуправляемую функцию.|  
|[Метод CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Запросы на создание новой задачи.|  
|[Метод EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Уведомляет хост, что управляемый код завершает работу период, в котором текущей задачи недопустимо, после предыдущего вызова `BeginDelayAbort`.|  
|[Метод EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Уведомляет хост, что управляемый код завершается из-за период, в котором текущую задачу нельзя перемещать в другой поток операционной системы, после предыдущего вызова `BeginThreadAffinity`.|  
|[Метод EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Уведомляет основное приложение, что вызова неуправляемого метода, такие как неуправляемого метода, возвращается управление выполнением в среду CLR.|  
|[Метод GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Получает указатель интерфейса на задачу, которая в данный момент в потоке операционной системы, из которого этот вызов выполняется.|  
|[Метод GetStackGuarantee](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Возвращает объем пространства стека, которое гарантированно будут доступны после завершения операций в стеке, но перед закрытием процесса.|  
|[Метод LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Уведомляет хост, что управляемый код собирается выполнить вызов в неуправляемую функцию.|  
|[Метод ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Уведомляет основное приложение, что вызов в среду (CLR) из неуправляемого кода.|  
|[Метод ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Уведомляет ведущее приложение, что элемент управления является средой CLR и неуправляемой функции, которая, в свою очередь, была вызвана из управляемого кода.|  
|[Метод SetCLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Предоставляет указатель интерфейса на узле [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) экземпляра, реализуемых средой CLR.|  
|[Метод SetLocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Уведомляет основное приложение, что среда CLR был изменен языковой стандарт для текущей задачи.|  
|[Метод SetStackGuarantee](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Зарезервировано только для внутреннего использования.|  
|[Метод SetUILocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Уведомляет основное приложение, что язык интерфейса пользователя был изменен для текущей задачи.|  
|[Метод Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Уведомляет основное приложение, что текущая задача будет в спящий режим.|  
|[Метод SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Уведомляет основное приложение, что он должен исходящего переключения текущей задачи.|  
  
## <a name="remarks"></a>Примечания  
 `IHostTaskManager` позволяет среде CLR для создания и управления задачами, для предоставления обработчиков действия при передаче управления из управляемого в неуправляемый код и обратно, а также указать определенные действия, узел может и не может принимать во время выполнения кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
