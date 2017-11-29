---
title: "Интерфейс IHostThreadPoolManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostThreadPoolManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostThreadPoolManager
helpviewer_keywords: IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: c3a2cd90-7c4e-4374-bb87-b41befb8344f
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2773042c695320ab1e90d4c5d341e2df5f0f778f
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ihostthreadpoolmanager-interface"></a>Интерфейс IHostThreadPoolManager
Предоставляет методы, позволяющие общеязыковой среды выполнения (CLR) для настройки пула потоков и очередь рабочих элементов в пуле потоков.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md)|Возвращает количество потоков в пуле потоков, который в настоящий момент не обрабатывает рабочие элементы.|  
|[Метод GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)|Возвращает максимальное число потоков, поддерживаемых основным приложением одновременно в пуле потоков.|  
|[Метод GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)|Получает минимальное количество свободных потоков, поддерживаемых основным приложением обработки запросов.|  
|[QueueUserWorkItem-метод](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-queueuserworkitem-method.md)|Ставит в очередь для выполнения функции и предоставляет объект, содержащий данные для использования функцией.|  
|[Метод SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)|Задает максимальное число потоков, которые основное приложение может хранить в пуле потоков.|  
|[Метод SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)|Задает минимальное количество свободных потоков, которые должен поддерживать узла обработки запросов.|  
  
## <a name="remarks"></a>Примечания  
 Узел не требуется настраивать пул потоков, используя значения, заданные в вызовах `SetMaxThreads` и `SetMinThreads` методы. В этом случае узел должен возвращать значение HRESULT E_NOTIMPL из этих методов.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading>  
 <xref:System.Threading.ThreadPool>  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
