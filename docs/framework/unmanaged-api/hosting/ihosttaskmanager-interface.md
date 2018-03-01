---
title: "Интерфейс IHostTaskManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9573891a2c27a2a92eccd0522f84175effa8037a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanager-interface"></a>Интерфейс IHostTaskManager
Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR), для работы с задачами через узел, вместо того чтобы использовать функции работы с потоками или волокон стандартной операционной системе.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание:|  
|------------|-----------------|  
|[Метод BeginDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Уведомляет хост, что управляемый код к периоду, в котором текущей задачи недопустимо.|  
|[Метод BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Уведомляет хост, что управляемый код к периоду, в котором текущую задачу нельзя перемещать в другой поток операционной системы.|  
|[Метод CallNeedsHostHook](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Ведущее приложение может указать, сможет ли среда вводить заданный вызов в неуправляемую функцию.|  
|[Метод CreateTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Запросы на создание новой задачи.|  
|[Метод EndDelayAbort](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Уведомляет хост, что управляемый код завершается из-за период, в котором текущей задачи недопустимо, после любого вызова для `BeginDelayAbort`.|  
|[Метод EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Уведомляет хост, что управляемый код завершается из-за период, в котором текущую задачу нельзя перемещать в другой поток операционной системы после предыдущего вызова для `BeginThreadAffinity`.|  
|[Метод EnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Уведомляет основное приложение, вызов неуправляемого метода, такие как неуправляемого метода возвращает управление выполнением в среду CLR.|  
|[Метод GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Получает указатель интерфейса на задачу, которая в данный момент в потоке операционной системы, из которого этот вызов.|  
|[Метод GetStackGuarantee](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Возвращает объем места в стеке, гарантированно будут доступны после завершения операций в стеке, но до закрытия процесса.|  
|[Метод LeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Уведомляет хост, что управляемый код является вызова неуправляемой функции.|  
|[Метод ReverseEnterRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Уведомляет узел, что вызов в среде (CLR) из неуправляемого кода.|  
|[Метод ReverseLeaveRuntime](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Уведомляет основное приложение, что элемент управления средой CLR и неуправляемой функции, которая, в свою очередь, была вызвана из управляемого кода.|  
|[Метод SetCLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Предоставляет основному указатель интерфейса [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) экземпляра, реализуемых средой CLR.|  
|[Метод SetLocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Уведомляет узел, что среда CLR изменила языковой стандарт для текущей задачи.|  
|[Метод SetStackGuarantee](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Зарезервировано только для внутреннего использования.|  
|[Метод SetUILocale](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Уведомляет основное приложение, что язык интерфейса пользователя был изменен для текущей задачи.|  
|[Метод Sleep](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Уведомляет основное приложение, текущая задача будет в спящий режим.|  
|[Метод SwitchToTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Уведомляет узел, что необходимости отключения текущей задачи.|  
  
## <a name="remarks"></a>Примечания  
 `IHostTaskManager`позволяет среде CLR создавать задачи и управлять ими, чтобы обеспечить обработчиков предпринять действия при передаче управления из управляемого в неуправляемый код и обратно, а также указать определенные действия узла может и не может принимать во время выполнения кода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
