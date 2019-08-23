---
title: Метод IHostIoCompletionManager::InitializeHostOverlapped
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.InitializeHostOverlapped
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped
helpviewer_keywords:
- IHostIoCompletionManager::InitializeHostOverlapped method [.NET Framework hosting]
- InitializeHostOverlapped method [.NET Framework hosting]
ms.assetid: c35199bf-bc47-4901-b467-4e8a37644bbb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ac7014962b99ac167e8192c13b2bae5ca92470f0
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69948516"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>Метод IHostIoCompletionManager::InitializeHostOverlapped
Предоставляет узлу возможность инициализировать любые пользовательские данные, добавляемые в структуру Win32 `OVERLAPPED` , которая используется для асинхронных запросов ввода-вывода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pvOverlapped`  
 окне Указатель на структуру Win32 `OVERLAPPED` , которая будет включена в запрос ввода-вывода.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped`успешно возвращено.|  
|HOST_E_CLRNOTAVAILABLE|Среда CLR не была загружена в процесс, или среда CLR находится в состоянии, в котором она не может выполнить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Время ожидания вызова истекло.|  
|HOST_E_NOT_OWNER|Вызывающий объект не владеет блокировкой.|  
|HOST_E_ABANDONED|Событие было отменено, пока заблокированный поток или волокно ожидают его.|  
|E_FAIL|Произошла неизвестная фатальная ошибка. Когда метод возвращает значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы методов размещения возвращают HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти для выделения запрошенного ресурса.|  
  
## <a name="remarks"></a>Примечания  
 Функции платформы Windows используют `OVERLAPPED` структуру для хранения состояния асинхронных запросов ввода-вывода. Среда CLR вызывает `InitializeHostOverlapped` метод, чтобы предоставить узлу возможность добавлять пользовательские данные `OVERLAPPED` в экземпляр.  
  
> [!IMPORTANT]
> Чтобы перейти к началу пользовательского блока данных, узлы должны задать смещение до размера `OVERLAPPED` структуры (`sizeof(OVERLAPPED)`).  
  
 Возвращаемое значение E_OUTOFMEMORY указывает на то, что узлу не удалось инициализировать свои пользовательские данные. В этом случае среда CLR сообщает об ошибке и вызове завершается ошибкой.  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [Метод GetHostOverlappedSize](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [Интерфейс IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
