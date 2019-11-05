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
ms.openlocfilehash: 17fca3e5a2d763277d3a5f9f72e2d35be6fc350c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124642"
---
# <a name="iclrtaskreset-method"></a>Метод ICLRTask::Reset
Информирует среду CLR о том, что узел завершил задачу, и позволяет среде CLR повторно использовать текущий экземпляр [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) для представления другой задачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `fFull`  
 [in] `true`, если среда выполнения должна сбрасывать все статические значения, связанные с потоками, в дополнение к сведениям о безопасности и национальной настройке, связанным с текущим экземпляром `ICLRTask`; в противном случае `false`.  
  
 Если значение равно `true`, среда выполнения сбрасывает данные, сохраненные с помощью <xref:System.Threading.Thread.AllocateDataSlot%2A> или <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`Reset` успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или обработать вызов. успешность|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Заметки  
 Среда CLR может перезапустить ранее созданные экземпляры `ICLRTask`, чтобы избежать лишних затрат на создание новых экземпляров каждый раз, когда требуется новая задача. Узел включает эту функцию, вызывая `ICLRTask::Reset` вместо [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) по завершении задачи. В следующем списке приведено краткое описание обычного жизненного цикла экземпляра `ICLRTask`.  
  
1. Среда выполнения создает новый экземпляр `ICLRTask`.  
  
2. Среда выполнения вызывает [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) , чтобы получить ссылку на текущую задачу узла.  
  
3. Среда выполнения вызывает метод [IHostTask:: SetCLRTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) , чтобы связать новый экземпляр с задачей хоста.  
  
4. Задача выполняется и завершается.  
  
5. Узел уничтожает задачу путем вызова `ICLRTask::ExitTask`.  
  
 `Reset` изменяет этот сценарий двумя способами. На шаге 5, приведенном выше, узел вызывает `Reset`, чтобы сбросить задачу до чистого состояния, а затем отделяет экземпляр `ICLRTask` от связанного экземпляра [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) . При необходимости узел также может кэшировать экземпляр `IHostTask` для повторного использования. На шаге 1 выше среда выполнения извлекает из кэша перезапущенный `ICLRTask`, а не создает новый экземпляр.  
  
 Этот подход хорошо работает, когда узел также имеет пул рабочих задач с многократным использованием. Когда узел уничтожает один из экземпляров `IHostTask`, он удаляет соответствующие `ICLRTask`, вызывая `ExitTask`.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
