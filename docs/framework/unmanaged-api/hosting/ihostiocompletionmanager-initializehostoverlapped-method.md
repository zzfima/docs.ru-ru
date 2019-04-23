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
ms.openlocfilehash: 1dea19a13cd2c741a24695b293ae1c8621ad5688
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157674"
---
# <a name="ihostiocompletionmanagerinitializehostoverlapped-method"></a>Метод IHostIoCompletionManager::InitializeHostOverlapped
Предоставляет возможность инициализировать любые пользовательские данные, добавляемые в Win32 основному `OVERLAPPED` структура, используемая для асинхронных запросов ввода-вывода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT InitializeHostOverlapped (  
    [in] void* pvOverlapped  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `pvOverlapped`  
 [in] Указатель на Win32 `OVERLAPPED` структуры, которые нужно включить в запрос ввода-вывода.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`InitializeHostOverlapped` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. Когда метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|Недостаточно памяти, доступного для выделения запрошенного ресурса.|  
  
## <a name="remarks"></a>Примечания  
 Платформа Windows используют функции `OVERLAPPED` структуру для хранения состояния для асинхронных запросов ввода-вывода. Среда CLR вызывает `InitializeHostOverlapped` метод, чтобы предоставить возможность добавления пользовательских данных для узла `OVERLAPPED` экземпляра.  
  
> [!IMPORTANT]
>  Для перехода в начало пользовательского блока данных, узлов необходимо установить смещение размер `OVERLAPPED` структуры (`sizeof(OVERLAPPED)`).  
  
 Возвращаемое значение E_OUTOFMEMORY указывает, что узел не удалось инициализировать его пользовательские данные. В этом случае среда CLR сообщает об ошибке и считает вызов неудачным.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейс ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [Метод GetHostOverlappedSize](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)
- [Интерфейс IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
