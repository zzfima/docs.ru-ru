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
ms.openlocfilehash: 008143c608cd19bee9dd115e97620906fb5b93b9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129409"
---
# <a name="iclrdebugmanager-interface"></a>Интерфейс ICLRDebugManager
Предоставляет методы, позволяющие узлу связать набор задач с идентификатором и понятным именем.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод BeginConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-beginconnection-method.md)|Устанавливает новое соединение между узлом и отладчиком для связывания задач с идентификатором и понятным именем.|  
|[Метод EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)|Удаляет связь между списком задач и идентификатором и понятным именем.|  
|[Метод GetDacl](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-getdacl-method.md)|Этот метод не реализован.|  
|[Метод IsDebuggerAttached](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-isdebuggerattached-method.md)|Получает значение, показывающее, присоединен ли отладчик к процессу.|  
|[Метод SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)|Связывает список экземпляров [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) с идентификатором и понятным именем.|  
|[Метод SetDacl](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setdacl-method.md)|Этот метод не реализован.|  
|[Метод SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md)|Задает политику чтения файлов базы данных программы (PDB). Политика определяет, включаются ли в стеки вызовов сведения о номерах строк и файлах.|  
  
## <a name="remarks"></a>Заметки  
 В сценариях отладки узлу может потребоваться сгруппировать задачи в соответствии с собственной логикой программирования. Например, группирование позволит разработчику видеть только задачи, необходимые API разработчика, а не выполнять все задачи, выполняемые в процессе. `ICLRDebugManager` позволяет узлу реализовать такой тип группирования.  
  
> [!IMPORTANT]
> Три метода `ICLRDebugManager`, `BeginConnection`, `SetConnectionTasks` и `EndConnection`, зависят друг от друга. Их необходимо вызывать в заданном порядке, чтобы работать должным образом.  
  
 Группирование и идентификаторы и понятные имена, которые узел назначает группе, не имеют смысла для среды CLR. CLR просто передает информацию в отладчик.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
