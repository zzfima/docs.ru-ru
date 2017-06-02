---
title: "&lt;net.tcp&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8bc2f2be-11c1-4bab-9018-1d21ae568d94
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# &lt;net.tcp&gt;
Задает параметры конфигурации для службы общего доступа к портам Net.Tcp, которая позволяет нескольким процессам совместно использовать один и тот же порт протокола TCP.  
  
## Синтаксис  
  
```  
  
<configuration>  
   <system.serviceModel.activation>  
       <net.tcp listenBacklog="Integer"  
          maxPendingAccepts="Integer"  
          maxPendingConnections="Integer"  
          receiveTimeout="TimeSpan"  
          teredoEnabled="Boolean">  
          <allowAccounts>  
             <!-- LocalSystem account -->   
             <add securityIdentifier="S-1-5-18"/>  
             <!-- LocalService account -->   
             <add securityIdentifier="S-1-5-19"/>  
             <!-- Administrators account -->   
             <add securityIdentifier="S-1-5-20"/>  
             <!-- Network Service account -->   
             <add securityIdentifier="S-1-5-32-544" />  
             <!-- IIS_IUSRS account (Vista only)-->   
             <add securityIdentifier="S-1-5-32-568"/>  
           </allowAccounts>  
       </net.tcp>  
   </system.serviceModel.activation>  
</configuration>  
```  
  
## Тип  
 `Type`  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`listenBacklog`|Целое число, которое определяет максимальное количество необработанных соединений, принятых от общего соединения, но еще не переданных службам [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  Значение по умолчанию — 10.|  
|`maxPendingAccepts`|Целое число, которое определяет максимальное количество одновременных необработанных принимающих потоков в конечной точке для общей службы.  Значение по умолчанию — 2.|  
|`MaxPendingConnections`|Максимальное число подключений, принятия которых приложением может ожидать прослушиватель.  После превышения значения этой квоты новые входящие подключения сбрасываются, а не ожидают принятия.  Функции подключения \(такие как безопасность сообщения\) могут вынудить клиента открыть несколько подключений.  При установке значения квоты администраторы службы должны учитывать возможность установления дополнительных подключений.  Значение по умолчанию — 10.|  
|`receiveTimeout`|Значение <xref:System.Timespan>, определяющее время ожидания для чтения данных кадрирования и проведения распределения подключений из базовых подключений.  Значение по умолчанию \- 00:00:10.|  
|`teredoEnabled`|Логическое значение, которое указывает, использует ли служба общего доступа к портам службу Microsoft Teredo для прослушивания TCP портов от имени службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)].  Значение по умолчанию — `false`.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<allowAccounts\>](../../../../../docs/framework/configure-apps/file-schema/wcf/allowaccounts.md)|Коллекция элементов конфигурации, которые содержат атрибут `securityIdentifier`, указывающий учетные записи пользователей для процессов служб [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)], которые имеют доступ к совместно используемой службе.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<system.serviceModel.activation\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel-activation.md)|Содержит параметры конфигурации для процесса прослушивателя SMSvcHost.exe.|  
  
## Заметки  
 Дополнительные сведения о поддержке общего доступа к портам см. в разделе [Net.TCP Port Sharing](http://msdn.microsoft.com/ru-ru/f13692ee-a179-4439-ae72-50db9534eded).  Дополнительные сведения о том, как настроить службу общего доступа к портам, см. в разделе [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/ru-ru/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0).  
  
## См. также  
 <xref:System.ServiceModel.Activation.Configuration.NetTcpSection>   
 [Net.TCP Port Sharing](http://msdn.microsoft.com/ru-ru/f13692ee-a179-4439-ae72-50db9534eded)   
 [Configuring the Net.TCP Port Sharing Service](http://msdn.microsoft.com/ru-ru/b6dd81fa-68b7-4e1b-868e-88e5901b7ea0)