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
ms.openlocfilehash: 13bf7342157de48e0183537afea2f2e53d1498dd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300311"
---
# <a name="iclrtaskreset-method"></a>Метод ICLRTask::Reset
Информирует общеязыковой среды выполнения (CLR), что узел завершения задачи и обеспечивает работу CLR для повторного использования текущего [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) экземпляра для представления другой задачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `fFull`  
 [in] `true`, если среда выполнения должна Сброс всех связанных с потоком статических значений дополняет сведения о безопасности и языковой стандарт, связанные с текущим `ICLRTask` экземпляра; в противном случае `false`.  
  
 Если значение равно `true`, среда выполнения сбрасывает данные, хранящиеся с помощью <xref:System.Threading.Thread.AllocateDataSlot%2A> или <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`Reset` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не был загружен в процесс или находится в состоянии, в котором он не может выполнять управляемый код или обработать вызов. успешно|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR может повторно использовать ранее созданный `ICLRTask` экземпляры, чтобы избежать создания новых экземпляров каждый раз при выполнении новой задачи. Узел включает эту функцию, вызвав `ICLRTask::Reset` вместо [ICLRTask::ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) после его завершения задачи. В следующем списке перечислены обычный жизненный цикл `ICLRTask` экземпляр:  
  
1. Среда выполнения создает новый `ICLRTask` экземпляра.  
  
2. Среда выполнения вызывает [IHostTaskManager::GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) для получения ссылки на текущую задачу узла.  
  
3. Среда выполнения вызывает [IHostTask::SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) должен быть сопоставлен новому экземпляру задачи.  
  
4. Задача выполняет и завершается.  
  
5. Узел уничтожает задачи путем вызова `ICLRTask::ExitTask`.  
  
 `Reset` изменяет этот сценарий следующим образом. В шаге 5 выше, сервер вызывает функцию `Reset` для сброса задачи в исходное состояние и затем разрывает связь между `ICLRTask` экземпляр из сопоставленного ему [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) экземпляра. При желании также можно кэшировать узла `IHostTask` экземпляра для повторного использования. На шаге 1 выше, среда выполнения извлекает перезапущен `ICLRTask` из кэша вместо создания нового экземпляра.  
  
 Этот подход работает также в том случае, когда узел также имеет пул повторно используемых рабочих задач. Когда узел Удаляет один из его `IHostTask` экземпляры, она окончательно удаляет соответствующие `ICLRTask` путем вызова `ExitTask`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
