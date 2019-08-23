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
ms.openlocfilehash: c43f906961b9e76d5f0f34ba5a5b2f656f5b1488
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937508"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a>Метод IHostIoCompletionManager::GetHostOverlappedSize
Возвращает размер любых пользовательских данных, которые узел намеревается добавить к запросам ввода-вывода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pcbSize`  
 заполняет Указатель на число байтов, которое должна выделить среда CLR в дополнение к размеру объекта Win32 `OVERLAPPED` .  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`GetHostOverlappedSize`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 Все асинхронные вызовы операций ввода-вывода в API платформы Windows принимают `OVERLAPPED` объект Win32, который предоставляет такую информацию, как расположение указателя файла. Для поддержания состояния приложения, которые выполняют асинхронные вызовы операций ввода-вывода, обычно добавляют в структуру пользовательские данные. `GetHostOverlappedSize`и [IHostIoCompletionManager:: инитиализехостоверлаппед](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) предоставляют возможность ведущему приложению включать такие пользовательские данные.  
  
 Среда CLR вызывает `GetHostOverlappedSize` метод, чтобы определить размер пользовательских данных, которые узел намеревается добавить `OVERLAPPED` к объекту.  
  
> [!NOTE]
> `GetHostOverlappedSize`вызывается только один раз. Пользовательские данные узла должны иметь одинаковый размер для каждого запроса ввода-вывода.  
  
> [!IMPORTANT]
> Размер `OVERLAPPED` самого объекта не включается в `pcbSize`значение.  
  
 Дополнительные сведения о `OVERLAPPED` структуре см. в документации по платформе Windows.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- <xref:System.Threading.NativeOverlapped>
- [Интерфейс ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [Интерфейс IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
