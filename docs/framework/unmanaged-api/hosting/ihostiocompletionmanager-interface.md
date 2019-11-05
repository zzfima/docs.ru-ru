---
title: Интерфейс IHostIoCompletionManager
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager
helpviewer_keywords:
- IHostIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c28d1983-83f7-46e2-990f-dbb9dc07c818
topic_type:
- apiref
ms.openlocfilehash: 51d79c398c94ec355528140325da2c25422cbad9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133851"
---
# <a name="ihostiocompletionmanager-interface"></a>Интерфейс IHostIoCompletionManager
Предоставляет методы, позволяющие среде CLR взаимодействовать с портами завершения ввода-вывода, предоставляемыми узлом.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|Привязывает маркер к порту завершения ввода-вывода.|  
|[Метод CloseIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|Закрывает порт, созданный с помощью предыдущего вызова метода `CreateIoCompletionPort`.|  
|[Метод CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|Запрашивает создание узлом нового порта завершения ввода-вывода.|  
|[Метод GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|Возвращает число потоков завершения ввода-вывода, которые в настоящий момент не обрабатывают запросы.|  
|[Метод GetHostOverlappedSize](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|Возвращает размер любых пользовательских данных, которые узел намеревается добавить к запросам ввода-вывода.|  
|[Метод GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|Возвращает максимальное число потоков, которое узел может выделить для обслуживания запросов ввода-вывода.|  
|[Метод GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|Возвращает минимальное число потоков, предоставляемых узлом для обслуживания запросов ввода-вывода.|  
|[Метод InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|Предоставляет узлу возможность инициализировать любые пользовательские данные о запросе ввода-вывода.|  
|[Метод SetCLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|Предоставляет узлу указатель интерфейса на экземпляр [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) , РЕАЛИЗУЕМый средой CLR.|  
|[Метод SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|Задает максимальное число потоков, которое узел запрашивает для обслуживания запросов ввода-вывода.|  
|[Метод SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|Задает минимальное число потоков, которое узел должен выделить при завершении ввода-вывода.|  
  
## <a name="remarks"></a>Заметки  
 `IHostIoCompletionManager` соответствует интерфейсу `ICLRIoCompletionManager`, реализуемому средой CLR. Среда CLR вызывает методы `IHostIoCompletionManager` для привязки дескрипторов к портам, предоставляемым узлом, и узел вызывает методы `ICLRIoCompletionManager`, чтобы сообщить о завершении запросов ввода-вывода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE. h  
  
 **Библиотека:** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
