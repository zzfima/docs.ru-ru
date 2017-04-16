---
title: "Уменьшение: параметр конфигурации minFreeMemoryPercentageToActiveService | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a7875f26-0da8-4afe-9846-7a21778f757b
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Уменьшение: параметр конфигурации minFreeMemoryPercentageToActiveService
В [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] возникает исключение, если объем доступной памяти на веб\-сервере меньше процентного значения, заданного параметром конфигурации [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md).  В [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] этот параметр игнорируется.  
  
## Последствия  
 В большинстве случаев соблюдение параметра [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) желательно: благодаря этому повышается стабильность системы за счет предотвращения исключений <xref:System.OutOfMemoryException>, которые могут возникнуть при запуске службы Windows Communication Foundation \(WCF\) в системе с ограниченной памятью.  
  
 Однако в некоторых случаях служба, которая ранее успешно запускалась, может перестать запускаться.  В этом случае появляется подробное сообщение об ошибке.  
  
```Output  
  
Проверка доступной памяти завершилась ошибкой, объем свободной памяти (nnnn байт) меньше nn % общей памяти.  В результате служба будет недоступна для входящих запросов.  Чтобы устранить эту проблему, необходимо либо снизить нагрузку на компьютер, либо изменить значение параметра "minFreeMemoryPercentageToActivateService" в элементе конфигурации.    
```  
  
## Уменьшение  
 Чтобы вернуться к прежнему поведению, где параметр [minFreeMemoryPercentageToActivateService](../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md) игнорировался, измените файл "web.config" следующим образом.  
  
```  
  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"   
                           minFreeMemoryPercentageToActivateService="0">  
   <serviceActivations>  
   ...  
   </serviceActivations>  
</serviceHostingEnvironment>  
  
```  
  
## См. также  
 [Изменения среды выполнения](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)