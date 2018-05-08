---
title: Метод IHostIoCompletionManager::GetHostOverlappedSize
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6713fdb822babf607752c1823a32dae43a7d567e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a>Метод IHostIoCompletionManager::GetHostOverlappedSize
Получает размер любых пользовательских данных, которые должен узла для добавления запросов ввода-вывода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pcbSize`  
 [out] Указатель на число байтов, которые необходимо выделить общеязыковой среды выполнения (CLR) и размера Win32 `OVERLAPPED` объекта.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`GetHostOverlappedSize` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 Все асинхронные вызовы ввода-вывода для API-интерфейсы платформы Windows принимают Win32 `OVERLAPPED` object, который предоставляет сведения, такие как положение указателя файла. Чтобы сохранять состояние, приложений, вызовов асинхронных операций ввода-вывода обычно добавить пользовательские данные в структуру. `GetHostOverlappedSize` и [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) дают возможность для узла включить такие пользовательские данные.  
  
 Среда CLR вызывает `GetHostOverlappedSize` метод для определения размера пользовательских данных, который планирует добавить узел `OVERLAPPED` объекта.  
  
> [!NOTE]
>  `GetHostOverlappedSize` вызывается только один раз. Пользовательские данные узла должны быть одинакового размера для каждого запроса ввода-вывода.  
  
> [!IMPORTANT]
>  Размер `OVERLAPPED` сам объект не включается в значение `pcbSize`.  
  
 Дополнительные сведения о `OVERLAPPED` структуры см. в документации по платформе Windows.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.NativeOverlapped>  
 [Интерфейс ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)  
 [Интерфейс IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
