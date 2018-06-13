---
title: Интерфейс ICLRGCManager
ms.date: 03/30/2017
api_name:
- ICLRGCManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager
helpviewer_keywords:
- ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 045b924033630ea98d5a532a62f1037a5972df90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33433928"
---
# <a name="iclrgcmanager-interface"></a>Интерфейс ICLRGCManager
Предоставляет методы, позволяющие ведущему приложению взаимодействовать с системой сборки мусора среды CLR.  
  
> [!NOTE]
>  Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно использовать [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) метод, чтобы задать размер сегмент сборки мусора и максимальный размер в систему сбора мусора в поколении 0 к значениям больше чем `DWORD` ограничения, установленного по [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) метод.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод Collect](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|Принудительная сборка мусора для заданного поколения.|  
|[Метод GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|Получает набор текущих статистических данных о системе сборки мусора.|  
|[Метод SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.|  
  
## <a name="remarks"></a>Примечания  
 Общеязыковая среда выполнения (CLR) реализует его механизм сборки мусора управляемые <xref:System.GC> типа. Дополнительные сведения о системе сборки мусора см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Автоматическое управление памятью](../../../../docs/standard/automatic-memory-management.md)  
 [Структура COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [Интерфейс ICLRControl](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Интерфейсы размещения CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
