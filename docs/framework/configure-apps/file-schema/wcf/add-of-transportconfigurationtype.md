---
title: "&lt;add&gt; для &lt;transportConfigurationType&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 03d79db9-571d-4534-acef-d05e5467b257
caps.latest.revision: 12
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 12
---
# &lt;add&gt; для &lt;transportConfigurationType&gt;
Данный элемент представляет собой пару ключ\/значение, которая идентифицирует тип конкретного транспорта.  
  
## Синтаксис  
  
```  
  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="String"  
               transportConfigurationType="String"/>   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|имя|Обязательный строковый атрибут.<br /><br /> Содержит ключ, определяемый пользователем, который является уникальным идентификатором типа транспорта.|  
|transportConfigurationType|Строка, содержащая тип, реализующий конкретный транспорт.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<transportConfigurationTypes\>](../../../../../docs/framework/configure-apps/file-schema/wcf/transportconfigurationtypes.md)|Коллекция типов, реализующих конкретный транспорт.|  
  
## Пример  
  
```  
<serviceHostingEnvironment>   
   <transportConfigurationTypes>  
      <add name="net.udp"  
      transportConfigurationType="Microsoft.ServiceModel.Samples.Hosting.HostedUdpTransportConfiguration, UdpActivation, Version=1.0.0.0, Culture=neutral, PublicKeyToken=6fa904d2da1848d6" />   
   </transportConfigurationTypes>  
</serviceHostingEnvironment>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.TransportConfigurationTypeElement>   
 <xref:System.ServiceModel.Configuration.ServiceHostingEnvironmentSection>   
 <xref:System.ServiceModel.ServiceHostingEnvironment>   
 [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)