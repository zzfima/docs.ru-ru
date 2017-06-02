---
title: "&lt;клиент&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client"
  - "http://schemas.microsoft.com/.NetConfiguration/v2.0#client"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 18
---
# &lt;клиент&gt;
Элемент `client` определяет список конечных точек, к которым может подключаться клиент.  
  
## Синтаксис  
  
```  
  
<system.serviceModel>  
    <client>  
        <endpoint>  
        </endpoint>  
                <metadata>  
        </metadata>  
    </client>  
</system.serviceModel>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
 Нет  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<конечная точка\>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|Содержит коллекцию элементов конечных точек, указывающую конечные точки, к которым может подключиться данный клиент.|  
|[\<метаданные\>](../../../../../docs/framework/configure-apps/file-schema/wcf/metadata.md)|Содержит параметры обработки метаданных.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<system.serviceModel\>](../../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)|Корневой элемент всех элементов конфигурации Windows Communication Foundation \(WCF\).|  
  
## Заметки  
 В разделе `client` определяется список конечных точек, к которым может подключаться клиент.  Каждая конечная точка, указанная в разделе клиента, определяет свои собственные привязку, поведение и контракт.  Она однозначно определяется сочетанием атрибутов `name` и `contract`.  В коде клиента указывается атрибут `name` для подключения к конечной точке службы, выполняемой клиентом.  Если атрибут `name` отсутствует, конечная точка действует как конечная точка по умолчанию для контракта, который она реализует.  
  
 Кроме того, в данном разделе также задаются параметры обработки метаданных.  
  
## Пример  
  
```  
<client>  
    <endpoint address="/HelloWorld/"  
              bindingConfiguration="usingDefaults"  
              name="MyBinding"  
              binding="customBinding"  
              contract="HelloWorld">  
    <addressProperties actingAs="http://www.microsoft.com/TestActor"  
             identityData="BasicReadWrite" identityType="Spn" isAddressPrivate="false">  
    </endpoint>  
</client>  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.ClientSection>   
 <xref:System.ServiceModel.Configuration.MetadataElement>   
 [Конфигурация клиента WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)   
 [Клиенты](../../../../../docs/framework/wcf/feature-details/clients.md)