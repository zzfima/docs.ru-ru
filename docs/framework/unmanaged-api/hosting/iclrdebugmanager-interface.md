---
title: "Интерфейс ICLRDebugManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDebugManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDebugManager
helpviewer_keywords: ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0e537b955524f2721868ddf5da9fccf68f9d4efd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="iclrdebugmanager-interface"></a>Интерфейс ICLRDebugManager
Предоставляет методы, позволяющие ведущему приложению связать набор задач с идентификатором и понятным именем.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Beginconnection-метод](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|Устанавливает новое соединение между узлом и отладчик связывания задачи с идентификатором и понятным именем.|  
|[EndConnection-метод](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|Удаляет связь между список задач и идентификатором и понятным именем.|  
|[Getdacl-метод](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|Этот метод не реализован.|  
|[Метод IsDebuggerAttached](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|Получает значение, показывающее, присоединен ли отладчик к процессу.|  
|[SetConnectionTasks-метод](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|Связывает список [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляры с идентификатором и понятное имя.|  
|[Setdacl-метод](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|Этот метод не реализован.|  
|[Setsymbolreadingpolicy-метод](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|Задает политику для чтения файлов базы данных (PDB). Политика определяет, включены ли сведения о номерах строк и файлах в стеки вызовов.|  
  
## <a name="remarks"></a>Примечания  
 В сценариях отладки узлу может потребоваться для группирования задач в соответствии с собственной логикой программирования. Например группирование позволит разработчику видеть только действия, необходимые для API разработчика, вместо всего списка задач, выполняемых в процессе. `ICLRDebugManager`Позволяет ведущему приложению реализовать этот вид группировки.  
  
> [!IMPORTANT]
>  Три `ICLRDebugManager` методы, `BeginConnection`, `SetConnectionTasks` и `EndConnection`, зависящие от друг с другом. Они должны вызываться в определенном порядке для правильной работы.  
  
 Группирование, идентификаторы и понятные имена, назначаемые узлом группированию, не имеют смысла для общеязыковой среды выполнения (CLR). Среда CLR передает информацию по отладчику.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
