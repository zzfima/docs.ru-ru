---
title: Метод IHostMemoryManager::GetMemoryLoad
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.GetMemoryLoad
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::GetMemoryLoad
helpviewer_keywords:
- IHostMemoryManager::GetMemoryLoad method [.NET Framework hosting]
- GetMemoryLoad method [.NET Framework hosting]
ms.assetid: e8138f6e-a0a4-48d4-8dae-9466b4dc6180
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b92ef3a6d7eb45a3b978c916c406bfa6199f17d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33440152"
---
# <a name="ihostmemorymanagergetmemoryload-method"></a>Метод IHostMemoryManager::GetMemoryLoad
Получает объем физической памяти, в настоящее время используется и следовательно, недоступной, как с отчетом узла.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT GetMemoryLoad (  
    [out] DWORD*  pMemoryLoad,   
    [out] SIZE_T  *pAvailableBytes  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pMemoryLoad`  
 [out] Указатель на примерное процентное соотношение общего объема физической памяти, который используется в настоящий момент.  
  
 `pAvailableBytes`  
 [out] Указатель на число байтов, доступных для общеязыковой среды выполнения (CLR).  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`GetMemoryLoad` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Среда CLR не загружена в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестная Неустранимая ошибка. Если метод вернет значение E_FAIL, среда CLR больше не может использоваться в процессе. Последующие вызовы размещение методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 `GetMemoryLoad` Создает оболочку для Win32 `GlobalMemoryStatus` функции. Значение `pMemoryLoad` является эквивалентом `dwMemoryLoad` в `MEMORYSTATUS` структуры, возвращенный `GlobalMemoryStatus`.  
  
 Среда выполнения использует возвращаемое значение в качестве эвристики для сборщика мусора. Например если узел сообщает, что большая часть памяти используется, сборщик мусора может приступить нескольких поколениях с целью увеличить объем памяти, который потенциально может стать доступным.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 <xref:System.GC?displayProperty=nameWithType>  
 [Интерфейс IHostMemoryManager](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
