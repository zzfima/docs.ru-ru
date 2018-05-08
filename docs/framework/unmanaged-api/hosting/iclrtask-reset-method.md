---
title: Метод ICLRTask::Reset
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 29267d032f5e38e352592edc50dbded68aaa9f61
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iclrtaskreset-method"></a>Метод ICLRTask::Reset
Информирует общеязыковой среды выполнения (CLR), узел завершения задачи что позволяет повторно использовать текущий CLR [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра для представления другой задачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fFull`  
 [in] `true`, если среда выполнения должна сбросить все связанные с потоками статического значения в дополнение к безопасности и языковой стандарт сведения, связанные с текущим `ICLRTask` экземпляра; в противном случае `false`.  
  
 Если значение равно `true`, среда выполнения сбрасывает данные, хранящиеся с помощью <xref:System.Threading.Thread.AllocateDataSlot%2A> или <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`Reset` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или обработать вызов. успешно|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR может повторно использовать ранее созданную `ICLRTask` экземпляров, чтобы избежать издержек по несколько раз, каждый раз, он должен новой задачи, создание новых экземпляров. Узел включает эту функцию, вызвав `ICLRTask::Reset` вместо [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) после его завершения задачи. В следующем списке перечислены обычный жизненный цикл `ICLRTask` экземпляр:  
  
1.  Среда выполнения создает новый `ICLRTask` экземпляра.  
  
2.  Среда выполнения вызывает метод [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) получить ссылку на текущую задачу узла.  
  
3.  Среда выполнения вызывает метод [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) необходимо связать новый экземпляр с задачей узла.  
  
4.  Задача выполняет и завершается.  
  
5.  Узел уничтожает задачи путем вызова `ICLRTask::ExitTask`.  
  
 `Reset` изменяет этот сценарий следующим образом. В шаге 5 выше, основное приложение вызывает `Reset` для сброса задачи в исходное состояние и затем отсоединяет `ICLRTask` экземпляр, связанный с ним из [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляра. При необходимости также можно кэшировать узла `IHostTask` экземпляра для повторного использования. В шаге 1 выше, среда выполнения извлекает перезапущен `ICLRTask` из кэша вместо создания нового экземпляра.  
  
 Такой подход удобно использовать, когда узел также имеет пул повторно используемых рабочих задач. Когда узел Удаляет один из его `IHostTask` экземпляры, она окончательно удаляет соответствующие `ICLRTask` путем вызова `ExitTask`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
