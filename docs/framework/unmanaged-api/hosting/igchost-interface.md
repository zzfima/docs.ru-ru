---
title: "Интерфейс IGCHost"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IGCHost
api_location: mscoree.dll
api_type: COM
f1_keywords: IGCHost
helpviewer_keywords: IGCHost interface [.NET Framework hosting]
ms.assetid: 9ad70ffd-6963-4ab2-8c84-3d86c3fb8deb
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5c0f398c09569a855291a1565ce63b513161a803
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="igchost-interface"></a>Интерфейс IGCHost
Предоставляет методы для получения сведений о системе сборки мусора, а также для управления некоторыми аспектами сбора мусора.  
  
> [!NOTE]
>  Начиная с [!INCLUDE[net_v45](../../../../includes/net-v45-md.md)], можно использовать [IGCHost2::SetGCStartupLimitsEx](../../../../docs/framework/unmanaged-api/hosting/igchost2-setgcstartuplimitsex-method.md) метод, чтобы задать размер сегмент сборки мусора и максимальный размер в систему сбора мусора в поколении 0 к значениям больше `DWORD` ограничения, установленного по [SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md) метод.  
  
> [!NOTE]
>  Этот интерфейс не только для специалистов. При неправильном, он может повлиять на производительность приложения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Collect-метод](../../../../docs/framework/unmanaged-api/hosting/igchost-collect-method.md)|Принудительно вызывает сборку мусора для данного поколения, независимо от состояния текущей сборки мусора.|  
|[Метод GetStats](../../../../docs/framework/unmanaged-api/hosting/igchost-getstats-method.md)|Получает статистику для текущего состояния системы сборки мусора.|  
|[Getthreadstats-метод](../../../../docs/framework/unmanaged-api/hosting/igchost-getthreadstats-method.md)|Получает статистику отдельного потока для сборки мусора.|  
|[Метод SetGCStartupLimits](../../../../docs/framework/unmanaged-api/hosting/igchost-setgcstartuplimits-method.md)|Задает размер сегмента и максимальный размер для поколения 0.|  
|[Setvirtualmemlimit-метод](../../../../docs/framework/unmanaged-api/hosting/igchost-setvirtualmemlimit-method.md)|Задает максимальный размер виртуальной памяти среды выполнения.|  
  
## <a name="requirements"></a>Требования  
 **Платформы:** разделе [требования к системе для](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок:** GCHost.idl, GCHost.h  
  
 **Библиотека:** включена как ресурс в MSCorEE.dll  
  
 **Версии платформы .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>См. также  
 [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Компонентный класс CorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/corruntimehost-coclass.md)
