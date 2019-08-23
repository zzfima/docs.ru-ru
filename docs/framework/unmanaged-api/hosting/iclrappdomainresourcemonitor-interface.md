---
title: Интерфейс ICLRAppDomainResourceMonitor
ms.date: 03/30/2017
api_name:
- ICLRAppDomainResourceMonitor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRAppDomainResourceMonitor
helpviewer_keywords:
- ICLRAppDomainResourceMonitor interface [.NET Framework hosting]
ms.assetid: 72fa83a1-8997-41d7-b355-ab177a24a303
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 597381c8ab31e86a02f870a24f165676d200b66e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965017"
---
# <a name="iclrappdomainresourcemonitor-interface"></a>Интерфейс ICLRAppDomainResourceMonitor
Предоставляет методы для проверки использования памяти и ЦП домена приложения.  
  
## <a name="methods"></a>Методы  
  
|Метод|Описание|  
|------------|-----------------|  
|[Метод GetCurrentAllocated](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentallocated-method.md)|Возвращает общий размер (в байтах) всех выделений памяти, сделанных доменом приложения с момента его создания, без вычитания памяти, которая была собрана сборщиком мусора.|  
|[Метод GetCurrentSurvived](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentsurvived-method.md)|Возвращает число байтов, сохранившихся последней полной блокирующей сборки мусора, на которые ссылается текущий домен приложения.|  
|[Метод GetCurrentCpuTime](../../../../docs/framework/unmanaged-api/hosting/iclrappdomainresourcemonitor-getcurrentcputime-method.md)|Возвращает общее время процессора, которое использовалось всеми потоками во время выполнения в текущем домене приложения, так как был создан домен приложения.|  
  
## <a name="remarks"></a>Примечания  
 `ICLRAppDomainResourceMonitor` Интерфейс предоставляет функциональные возможности, аналогичные следующим управляемым свойствам:  
  
- <xref:System.AppDomain.MonitoringIsEnabled%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalProcessorTime%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringTotalAllocatedMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedProcessMemorySize%2A?displayProperty=nameWithType>  
  
- <xref:System.AppDomain.MonitoringSurvivedMemorySize%2A?displayProperty=nameWithType>  
  
## <a name="requirements"></a>Требования  
 **Платформ** См. раздел [Требования к системе](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Заголовок.** Метахост. h  
  
 **Библиотечная** Включается в качестве ресурса в библиотеку MSCorEE. dll  
  
 **Версии платформы .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>См. также

- [\<Элемент > Аппдомаинресаурцемониторинг](../../../../docs/framework/configure-apps/file-schema/runtime/appdomainresourcemonitoring-element.md)
- [Отслеживание ресурсов домена приложения](../../../standard/garbage-collection/app-domain-resource-monitoring.md)
- [Интерфейсы размещения](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Размещение](../../../../docs/framework/unmanaged-api/hosting/index.md)
