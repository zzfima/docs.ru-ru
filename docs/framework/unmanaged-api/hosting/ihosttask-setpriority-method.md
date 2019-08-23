---
title: Метод IHostTask::SetPriority
ms.date: 03/30/2017
api_name:
- IHostTask.SetPriority
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::SetPriority
helpviewer_keywords:
- IHostTask::SetPriority method [.NET Framework hosting]
- SetPriority method [.NET Framework hosting]
ms.assetid: cd8c379b-c7a0-434f-8e23-899bd26be75d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 533e3d715b46b4ef6d473795a010fa3ad297ded2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913753"
---
# <a name="ihosttasksetpriority-method"></a>Метод IHostTask::SetPriority
Запрашивает у узла настройку уровня приоритета потока для задачи, представленной текущим экземпляром [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) .  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetPriority (  
    [in] int newPriority  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `newPriority`  
 окне Целое число, представляющее запрошенное значение приоритета потока для задачи, представленной текущим `IHostTask` экземпляром.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetPriority`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 Потокам предоставляется время обработки с помощью системы циклического перебора, частично основанной на уровне приоритета потока. `SetPriority`позволяет среде CLR устанавливать этот уровень приоритета потока для текущей задачи. Поддерживаются `newPriority` следующие значения.  
  
- THREAD_PRIORITY_ABOVE_NORMAL  
  
- THREAD_PRIORITY_BELOW_NORMAL  
  
- THREAD_PRIORITY_HIGHEST  
  
- THREAD_PRIORITY_IDLE  
  
- THREAD_PRIORITY_LOWEST  
  
- THREAD_PRIORITY_NORMAL  
  
- THREAD_PRIORITY_TIME_CRITICAL  
  
 Среда CLR вызывает `SetPriority` , когда значение <xref:System.Threading.Thread.Priority%2A?displayProperty=nameWithType> изменяется с помощью пользовательского кода. Узел может определять собственные алгоритмы для назначения приоритета потоков и может без необходимости пропускать этот запрос.  
  
> [!NOTE]
> `SetPriority`не сообщает, был ли изменен уровень приоритета потока. Вызовите метод [IHostTask:: предшествовал](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md) , чтобы определить значение уровня приоритета потока задачи.  
  
 Значения уровня приоритета потока определяются функцией Win32 `SetThreadPriority` . Дополнительные сведения о приоритете потоков см. в документации по платформе Windows.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.Thread>
- [Интерфейс ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [Интерфейс ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [Интерфейс IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Метод GetPriority](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)
- [Интерфейс IHostTaskManager](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
