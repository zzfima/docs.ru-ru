---
title: Метод IHostThreadPoolManager::GetMinThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.GetMinThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::GetMinThreads
helpviewer_keywords:
- IHostThreadPoolManager::GetMinThreads method [.NET Framework hosting]
- GetMinThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: dc07232b-b2e4-4dab-87e2-3c955974ab48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2064f134d83e6d410e851d8ea9498b45e36aea37
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442271"
---
# <a name="ihostthreadpoolmanagergetminthreads-method"></a>Метод IHostThreadPoolManager::GetMinThreads
Получает минимальное количество свободных потоков, поддерживаемых основным приложением в пуле потоков обработки запросов.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetMinThreads (  
    [out] DWORD *MinThreads  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `MinThreads`  
 [out] Указатель на минимальное количество свободных рабочих потоков, которые в данный момент основным приложением.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`GetMinThreads` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|Узел не предоставляет реализацию `GetMinThreads`.|  
  
## <a name="remarks"></a>Примечания  
 Узел не требуется предоставлять реализацию `GetMinThreads`. В этом случае он должен возвращать значение HRESULT E_NOTIMPL.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ThreadPool.GetMinThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [Метод GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [Метод SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [Интерфейс IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
