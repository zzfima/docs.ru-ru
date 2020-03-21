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
ms.openlocfilehash: 645b64c8b536029663c350bdcde9a716a715aab3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178085"
---
# <a name="iclrgcmanagersetgcstartuplimits-method"></a>Метод ICLRGCManager::SetGCStartupLimits
Устанавливает размер сегмента сбора мусора и максимальный размер поколения 0 системы сбора мусора.  
  
> [!IMPORTANT]
> Начиная с .NET Framework 4.5, вы можете установить размер сегмента `DWORD` и максимальный размер поколения 0 на значения, превышающее значения с помощью метода [ICLRGCManager2::SetGCStartupLimitsEx.](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md)  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
HRESULT SetGCStartupLimits (  
    [in] DWORD SegmentSize,
    [in] DWORD MaxGen0Size  
);  
```  
  
## <a name="parameters"></a>Параметры  
 `SegmentSize`  
 (в) Указанный размер сегмента сбора мусора.  
  
 Минимальный размер сегмента составляет 4 МБ. Сегменты могут быть увеличены с шагом 1 МБ или больше.  
  
 `MaxGen0Size`  
 (в) Указанный максимальный размер для поколения 0.  
  
 Минимальный размер поколения 0 составляет 64 кБ.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
|HRESULT|Описание|  
|-------------|-----------------|  
|S_OK|`SetGCStartupLimits`вернулся успешно.|  
|HOST_E_CLRNOTAVAILABLE|Время выполнения общего языка (CLR) не было загружено в процесс, или CLR находится в состоянии, в котором он не может запустить управляемый код или успешно обработать вызов.|  
|HOST_E_TIMEOUT|Вызов приурочен.|  
|HOST_E_NOT_OWNER|Звонящее не владеет замком.|  
|HOST_E_ABANDONED|Событие было отменено в то время как заблокированный поток или волокно ждало на нем.|  
|E_FAIL|Произошел неизвестный катастрофический сбой. После того, как метод возвращается E_FAIL, CLR больше не может быть пригодным к удочку в процессе. Последующие вызовы к методам хостинга возвращают HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Remarks  
 Значения, которые `SetGCStartupLimits` наборы могут быть указаны только один раз. Более поздние звонки `SetGCStartupLimits` игнорируются.  
  
## <a name="requirements"></a>Требования  
 **Платформы:** см. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** Включено в качестве ресурса в MSCorEE.dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также раздел

- [Автоматическое управление памятью](../../../standard/automatic-memory-management.md)
- [Сборка мусора](../../../standard/garbage-collection/index.md)
- [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [Интерфейс ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
