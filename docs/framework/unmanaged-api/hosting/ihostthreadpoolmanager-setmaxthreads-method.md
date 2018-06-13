---
title: Метод IHostThreadPoolManager::SetMaxThreads
ms.date: 03/30/2017
api_name:
- IHostThreadPoolManager.SetMaxThreads
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostThreadPoolManager::SetMaxThreads
helpviewer_keywords:
- IHostThreadPoolManager::SetMaxThreads method [.NET Framework hosting]
- SetMaxThreads method, IHostThreadPoolManager interface [.NET Framework hosting]
ms.assetid: 77cfd347-95c2-4425-b807-4ecc2a8d4578
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f978f565dd93eb10a68942fc463f7d5cc212e6e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442037"
---
# <a name="ihostthreadpoolmanagersetmaxthreads-method"></a>Метод IHostThreadPoolManager::SetMaxThreads
Задает максимальное число потоков, которые основное приложение может хранить в пуле потоков.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT SetMaxThreads (  
    [in] DWORD MaxThreads  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `MaxThreads`  
 Максимальное количество рабочих потоков в пуле потоков.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetMaxThreads` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный, Разрушительный сбой. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|Узел не предоставляет реализацию `SetMaxThreads`.|  
  
## <a name="remarks"></a>Примечания  
 Узел не является обязательным для предоставления среде CLR для настройки размера пула потоков. На некоторых серверах может потребоваться исключительный контроль над пула потоков, для реализации, производительности или масштабирования. В этом случае основное приложение должно возвратить HRESULT со значением E_NOTIMPL.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.Threading.ThreadPool.SetMaxThreads%2A>  
 <xref:System.Threading.ThreadPool>  
 [Метод GetMaxThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-getmaxthreads-method.md)  
 [Метод SetMinThreads](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-setminthreads-method.md)  
 [Интерфейс IHostThreadPoolManager](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
