---
title: "Устранение рисков: параметр конфигурации minFreeMemoryPercentageToActiveService | Документация Майкрософт"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 783dd4fb28f1590722833ce9a456b9c2c76ecd80
ms.contentlocale: ru-ru
ms.lasthandoff: 04/18/2017

---
# <a name="mitigation-minfreememorypercentagetoactiveservice-configuration-setting"></a>Устранение рисков: параметр конфигурации minFreeMemoryPercentageToActiveService
В [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] возникает исключение, если объем доступной памяти на веб-сервере меньше процентного значения, заданного параметром конфигурации [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md). В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] этот параметр игнорируется.  
  
## <a name="impact"></a>Последствия  
 В большинстве случаев соблюдение параметра [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) желательно: благодаря этому повышается стабильность системы за счет предотвращения исключений <xref:System.OutOfMemoryException>, которые могут возникнуть при запуске службы Windows Communication Foundation (WCF) в системе с ограниченной памятью.  
  
 Однако в некоторых случаях служба, которая ранее успешно запускалась, может перестать запускаться. В этом случае появляется подробное сообщение об ошибке.  
  
```console
Memory gates checking failed because the free memory (nnnn bytes) is less than nn% of total memory. As a result, the service will not be available for incoming requests. To resolve this, either reduce the load on the machine or adjust the value of minFreeMemoryPercentageToActivateService on the serviceHostingEnvironment config element.
```
  
## <a name="mitigation"></a>Уменьшение  
 Чтобы вернуться к прежнему поведению, где параметр [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) игнорировался, измените файл web.config следующим образом.  
  
```xml
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
```  
  
## <a name="see-also"></a>См. также  
 [Изменения среды выполнения](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)

