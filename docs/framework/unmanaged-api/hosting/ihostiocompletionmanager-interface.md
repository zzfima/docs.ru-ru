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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c3bebe8eabd4d5fd5faec21e0b0efc408353bc2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197273"
---
# <a name="ihostiocompletionmanager-interface"></a>Интерфейс IHostIoCompletionManager
Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для взаимодействия с помощью портов завершения ввода-вывода, предоставленный средой размещения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md)|Привязывает дескриптор к порту завершения ввода-вывода.|  
|[Метод CloseIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-closeiocompletionport-method.md)|Закрывает порт, который был создан при помощи предыдущими вызовами `CreateIoCompletionPort`.|  
|[Метод CreateIoCompletionPort](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-createiocompletionport-method.md)|Запросы на создание нового порта завершения ввода-вывода.|  
|[Метод GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getavailablethreads-method.md)|Получает количество потоков завершения ввода-вывода, которые в настоящий момент не обрабатывает запросы.|  
|[Метод GetHostOverlappedSize](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-gethostoverlappedsize-method.md)|Получает размер любых пользовательских данных, которые узел должен добавить запросы ввода-вывода.|  
|[Метод GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getmaxthreads-method.md)|Возвращает максимальное число потоков, которые основное приложение может выделить для обслуживания запросов ввода-вывода.|  
|[Метод GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-getminthreads-method.md)|Получает минимальное количество потоков, предоставляемых хостом для обслуживания запросов ввода-вывода.|  
|[Метод InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md)|Узел предоставляет пользователям возможность инициализировать любые пользовательские данные о запрос ввода-вывода.|  
|[Метод SetCLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setclriocompletionmanager-method.md)|Предоставляет указатель интерфейса на узле [ICLRIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md) экземпляра, реализуемых средой CLR.|  
|[Метод SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setmaxthreads-method.md)|Задает максимальное количество потоков, выделяемых основным приложением для обслуживания запросов ввода-вывода.|  
|[Метод SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-setminthreads-method.md)|Задает минимальное количество потоков, которые основное приложение должно выделить для завершения ввода-вывода.|  
  
## <a name="remarks"></a>Примечания  
 `IHostIoCompletionManager` соответствует `ICLRIoCompletionManager` интерфейс, реализованный средой CLR. Среда CLR вызывает методы `IHostIoCompletionManager` для привязки к портам, которые предоставляет узел и узел вызывает методы дескрипторы `ICLRIoCompletionManager` для сообщает о завершении запросов ввода-вывода.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
