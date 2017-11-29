---
title: "Интерфейс ICLRGCManager"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRGCManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRGCManager
helpviewer_keywords: ICLRGCManager interface [.NET Framework hosting]
ms.assetid: fb511c9b-3fe4-41b0-822a-6ba4a079d1f5
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7215ce1423e8541b23daae7b9e051ade6e25f1b7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="iclrgcmanager-interface"></a>Интерфейс ICLRGCManager
Предоставляет методы, позволяющие ведущему приложению взаимодействовать с системой сборки мусора среды CLR.  
  
> [!NOTE]
>  Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно использовать [ICLRGCManager2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager2-setgcstartuplimitsex-method.md) метод, чтобы задать размер сегмент сборки мусора и максимальный размер в систему сбора мусора в поколении 0 к значениям больше чем `DWORD` ограничения, установленного по [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md) метод.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Collect-метод](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-collect-method.md)|Принудительная сборка мусора для заданного поколения.|  
|[Метод GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md)|Получает набор текущих статистических данных о системе сборки мусора.|  
|[Метод SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-setgcstartuplimits-method.md)|Задает размер сегмент сборки мусора и максимальный размер в систему сбора мусора поколения 0.|  
  
## <a name="remarks"></a>Примечания  
 Общеязыковая среда выполнения (CLR) реализует его механизм сборки мусора управляемые <xref:System.GC> типа. Дополнительные сведения о системе сборки мусора см. в разделе [мусора](../../../../docs/standard/garbage-collection/index.md).  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** MSCorEE.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Автоматическое управление памятью](../../../../docs/standard/automatic-memory-management.md)  
 [COR_GC_STATS-структура](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)  
 [ICLRControl-интерфейс](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)  
 [Интерфейсы размещения CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
