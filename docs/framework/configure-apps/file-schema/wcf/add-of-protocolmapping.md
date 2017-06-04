---
title: "&lt;add&gt; для &lt;protocolMapping&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# &lt;add&gt; для &lt;protocolMapping&gt;
Представляет сопоставление протокола по умолчанию между схемой транспортного протокола \(например, http, net.tcp, net.pipe и т. д.\) и привязкой [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  При создании конечных точек по умолчанию во время выполнения [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] просматривает заданные сопоставления и решает, какую привязку необходимо использовать для определенного базового адреса.  
  
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
  
|Элемент|Описание|  
|-------------|--------------|  
|привязка|Строка, в которой указан тип привязки, используемый для конечной точки во время создания конечной точки по умолчанию.|  
|bindingConfiguration|Строка, содержащая имя раздела конфигурации привязки, на который будет установлена ссылка.|  
|scheme|Схема транспортного протокола, которая будет использоваться для конечной точки по умолчанию.|  
  
### Дочерние элементы  
 Отсутствует.  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<protocolMapping\>](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Представляет раздел конфигурации для определения сопоставлений протоколов по умолчанию между схемами транспортных протоколов \(например, http, net.tcp, net.pipe и т. д.\) и привязками [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].|  
  
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