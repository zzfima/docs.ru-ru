---
title: Метод IHostThreadPoolManager::GetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMaxThreads method [.NET Framework hosting]
- GetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: db268876-6178-4a81-aca3-318ee7f96001
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa6e0e2447cc3ff6766bb33bb603388f37ec3ce0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443775"
---
# <a name="ihostthreadpoolmanagergetmaxthreads-method"></a>Метод IHostThreadPoolManager::GetMaxThreads
Возвращает максимальное число потоков, поддерживаемых основным приложением одновременно в пуле потоков.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetMaxThreads (  
    [out] DWORD *pdwMaxWorkerThreads  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pdwMaxWorkerThreads`  
 [out] Указатель на максимальное число потоков, поддерживаемых основным приложением в пуле потоков.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`GetMaxThreads` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR (не была загружена в процесс или находится в состоянии, в котором она не удается запустить процесс вызова или неуправляемый код.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|Узел не предоставляет реализацию `GetMaxThreads`.|  
  
## <a name="remarks"></a>Примечания  
 Среда CLR вызывает `GetMaxThreads` определить общее число потоков в пуле потоков. [GetAvailableThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getavailablethreads-method.md) метод возвращает количество потоков, которые в настоящий момент не обрабатывает рабочие элементы. Все запросы, превышающие возвращаемым значением `pdwMaxWorkerThreads` параметр остаются в очереди до появления доступных потоков.  
  
 Если узел не предоставляет реализацию `GetMaxThreads`, он должен возвращать значение HRESULT E_NOTIMPL.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ThreadPool.GetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [Метод GetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getminthreads-method.md)  
 [Метод SetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setmaxthreads-method.md)  
 [Интерфейс IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
