---
title: Метод IHostTaskManager::CreateTask
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
ms.openlocfilehash: fef2f56fd000a8610a40661a30aa306ae5a7884e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177991"
---
# <a name="ihosttaskmanagercreatetask-method"></a>Метод IHostTaskManager::CreateTask
Запросы на создание узла новой задачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `stacksize`  
 (в) Запрошенный размер, в байтах, запрашиваемого стека, или 0 (ноль) для размера по умолчанию.  
  
 `pStartAddress`  
 (в) Указатель на функцию, которую выполняет задача.  
  
 `pParameter`  
 (в) Указатель на пользовательские данные, которые должны быть переданы функции, или нулевые, если функция не принимает никаких параметров.  
  
 `ppTask`  
 (ваут) Указатель на адрес экземпляра [IHostTask,](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) созданный унизатом, или нулевый, если задача не может быть создана. Задача остается в приостановленном состоянии до тех пор, пока она явно не запущена вызовом на [IHostTask::Start](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`CreateTask`вернулся успешно.|  
|HOST_E_CLRNOTAVAILABLE|Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Вызов приурочен.|  
|HOST_E_NOT_OWNER|Звонящее не владеет замком.|  
|HOST_E_ABANDONED|Событие было отменено в то время как заблокированный поток или волокно ждало на нем.|  
|E_FAIL|Произошел неизвестный катастрофический сбой. Когда метод возвращается E_FAIL, CLR больше не используется в процессе. Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти было доступно для создания запрашиваемых задач.|  
  
## <a name="remarks"></a>Remarks  
 CLR требует, `CreateTask` чтобы ухтабыла создала новую задачу. Хост возвращает указатель `IHostTask` интерфейса в экземпляр. Возвращалась задача должна оставаться `IHostTask::Start`приостановленной до тех пор, пока она явно не будет запущена вызовом.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
