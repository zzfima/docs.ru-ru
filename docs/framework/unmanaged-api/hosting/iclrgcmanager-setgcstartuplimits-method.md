---
title: Метод ICLRGCManager::SetGCStartupLimits
ms.date: 03/30/2017
api_name:
- ICLRGCManager.SetGCStartupLimits
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::SetGCStartupLimits
helpviewer_keywords:
- SetGCStartupLimits method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::SetGCStartupLimits method [.NET Framework hosting]
ms.assetid: 1c8d9959-95b5-4131-be4a-556d97774014
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8b25f73e9af77faadbc691255cb3139498f5d25c
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2019
ms.locfileid: "67779711"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a>Метод ICLRGCManager::SetGCStartupLimits
Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.  
  
> [!IMPORTANT]
>  Начиная с .NET Framework 4.5, можно задать размер сегмента и максимально возможного поколения 0 размер значения больше, чем `DWORD` с помощью [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,   
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `SegmentSize`  
 [in] Указанный размер сегмент сборки мусора.  
  
 Минимальный размер сегмента составляет 4 МБ. Сегменты можно увеличить с шагом 1 МБ или больше.  
  
 `MaxGen0Size`  
 [in] Заданный максимальный размер поколения 0.  
  
 Минимальное поколения 0 размер составляет 64 КБ.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimits` успешно возвращен.|  
|ЗНАЧЕНИЕ HOST_E_CLRNOTAVAILABLE|Общеязыковая среда выполнения (CLR) не был загружен в процесс или находится в состоянии, в котором не может выполнять управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Истекло время ожидания вызова.|  
|HOST_E_NOT_OWNER|Вызывающий объект не является владельцем блокировки.|  
|HOST_E_ABANDONED|Событие было отменено с сохранением заблокированный поток или ожидал волокон.|  
|E_FAIL|Неизвестный Разрушительный сбой. После метод вернет значение E_FAIL, среда CLR больше не использовать в данном процессе. Последующие вызовы к размещению методы возвращают значение HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Примечания  
 Значения, `SetGCStartupLimits` наборы, которые можно указать только один раз. Последующие вызовы `SetGCStartupLimits` игнорируются.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** MSCorEE.h  
  
 **Библиотека:** Включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [Автоматическое управление памятью](../../../../docs/standard/automatic-memory-management.md)
- [Сборка мусора](../../../../docs/standard/garbage-collection/index.md)
- [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Интерфейс ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
