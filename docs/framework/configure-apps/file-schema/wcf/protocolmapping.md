---
title: "&lt;protocolMapping&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 5076644b-1f33-4f26-9488-87de9fcda04c
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;protocolMapping&gt;
Представляет раздел конфигурации, в котором определяется набор сопоставления протоколов по умолчанию между схемами транспортных протоколов \(например, http, net.tcp, net.pipe и т. д.\) и привязками WCF.  При создании конечных точек по умолчанию во время выполнения [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] просматривает заданные сопоставления и решает, какую привязку необходимо использовать для определенного базового адреса.  
  
## Синтаксис  
  
```vb  
  
<protocolMapping>  
    <add binding="String”  
         bindingConfiguration="String”  
         scheme="http/net.msmq/net.pipe/net.tcp"/>  
</protocolMapping>  
  
```  
  
```csharp  
  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Отсутствует.  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<фильтры\>](../../../../../docs/framework/configure-apps/file-schema/wcf/filters-of-routing.md)|Содержит сопоставление протокола по умолчанию между схемой транспортного протокола \(например http, net.tcp, net.pipe и т. д.\) и привязкой WCF.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|system.ServiceModel|Корневой элемент всех элементов конфигурации WCF.|  
  
## Пример  
 В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config.  Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config.  Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.  
  
```  
  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
  
```  
  
## См. также  
 [System.ServiceModel.Configuration.ProtocolMappingSection](assetId:///System.ServiceModel.Configuration.ProtocolMappingSection?qualifyHint=False&amp;autoUpgrade=True)   
 [System.ServiceModel.Configuration.ProtocolMappingElement](assetId:///System.ServiceModel.Configuration.ProtocolMappingElement?qualifyHint=False&amp;autoUpgrade=True)