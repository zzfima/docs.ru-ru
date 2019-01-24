---
title: Интерфейс ICLRDebugManager
ms.date: 03/30/2017
api_name:
- ICLRDebugManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager
helpviewer_keywords:
- ICLRDebugManager interface [.NET Framework hosting]
ms.assetid: e835062c-c7d6-4945-8a44-2de7ebf3928e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 515eb0633c82c3e1386487d1866de79c9898c9cd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54654611"
---
# <a name="iclrdebugmanager-interface"></a>Интерфейс ICLRDebugManager
Предоставляет методы, которые позволяют ведущему приложению связать набор задач с идентификатором и понятное имя.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|Устанавливает новое соединение между узлом и отладчик связывания задачи с идентификатором и понятное имя.|  
|[Метод EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|Удаляет связь между список задач и идентификатора и понятным именем.|  
|[Метод GetDacl](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|Этот метод не реализован.|  
|[Метод IsDebuggerAttached](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|Получает значение, показывающее, присоединен ли отладчик к процессу.|  
|[Метод SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|Связывает список [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляры с идентификатором и понятное имя.|  
|[Метод SetDacl](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|Этот метод не реализован.|  
|[Метод SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|Задает политику для чтения файлов базы данных (PDB). Политика определяет, включаются ли сведения о файлах и номера строк в стеках вызовов.|  
  
## <a name="remarks"></a>Примечания  
 В сценариях отладки, узел может потребоваться сгруппировать задачи в соответствии с собственной логикой программирования. Например группирование позволит разработчику видят только те задачи, необходимые для API разработчика, вместо всего списка задач, выполняемых в процессе. `ICLRDebugManager` позволяет узлу для реализации такого рода группирования.  
  
> [!IMPORTANT]
>  Три `ICLRDebugManager` методы, `BeginConnection`, `SetConnectionTasks` и `EndConnection`, зависят от друг с другом. Они должны вызываться в заданном порядке работала должным образом.  
  
 Группирование, идентификаторы и понятные имена, назначаемые узлом группированию, не имеют смысла для общеязыковой среды выполнения (CLR). Среда CLR передает информацию по отладчику.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
