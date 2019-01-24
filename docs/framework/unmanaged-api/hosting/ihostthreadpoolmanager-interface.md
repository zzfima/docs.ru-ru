---
title: Интерфейс IHostThreadPoolManager
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager
helpviewer_keywords:
- IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7fc0a271a9c62406d2942f387a5458e21211116
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54522730"
---
# <a name="ihostthreadpoolmanager-interface"></a>Интерфейс IHostThreadPoolManager
Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для настройки пула потоков и очередь рабочих элементов в пул потоков.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|Получает количество потоков в пуле потоков, который в настоящий момент не обрабатывает рабочие элементы.|  
|[Метод GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|Возвращает максимальное число потоков, ведущий одновременно в пуле потоков.|  
|[Метод GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|Получает минимальное количество свободных потоков, ведущий обработки запросов.|  
|[Метод QueueUserWorkItem](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|Помещает в очередь для выполнения функции и предоставляет объект, содержащий данные, используемые функцией.|  
|[Метод SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|Задает максимальное количество потоков, основное приложение может хранить в пуле потоков.|  
|[Метод SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|Задает минимальное количество свободных потоков, которые необходимо поддерживать узел обработки запросов.|  
  
## <a name="remarks"></a>Примечания  
 Узел не требуется настраивать пул потоков, используя значения, заданные в вызовах `SetMaxThreads` и `SetMinThreads` методы. В этом случае узел должен возвращать значение HRESULT E_NOTIMPL из этих методов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также
- <xref:System.Threading>
- <xref:System.Threading.ThreadPool>
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
