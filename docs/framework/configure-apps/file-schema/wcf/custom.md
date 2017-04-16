---
title: "&lt;пользовательский&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
caps.latest.revision: 14
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 14
---
# &lt;пользовательский&gt;
Задает параметры службы пользовательского распознавателя одноранговых узлов.  
  
## Синтаксис  
  
```  
  
<custom address="Uri"  
   resolverType="String">  
      <headers/>  
   <identity/>  
</peerResolver>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`address`|URI, указывающий адрес конечной точки однорангового узла, на котором размещается пользовательская служба распознавателя одноранговых узлов.|  
|`resolverType`|Строка, задающая тип пользовательской службы распознавателя одноранговых узлов.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<удостоверение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Задает идентификатор пользовательских распознавателей одноранговых узлов, настроенных для данного элемента.  Это элемент типа <xref:System.ServiceModel.Configuration.IdentityElement>.|  
|[\<верхние колонтитулы\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers-element.md)|Коллекция заголовков адреса, используемых для сообщений SOAP, обрабатываемых пользовательским распознавателем одноранговых узлов.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<resolver\>](../../../../../docs/framework/configure-apps/file-schema/wcf/resolver.md)|Распознаватель одноранговых узлов, используемый для разрешения идентификатора сетки с IP\-адресами в набор адресов одноранговых узлов, представляющих несколько узлов, входящих в сетку.|  
  
## Заметки  
 Этот элемент определяет основные параметры пользовательской службы распознавателя одноранговых узлов, включая адрес конечной точки однорангового узла, на котором размещена служба, и любые специальные параметры привязки.  Дополнительные сведения о создании пользовательского распознавателя см. в разделе [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/ru-ru/12aa3787-2962-439c-ad27-46523c8b0419).  
  
## См. также  
 <xref:System.Servicemodel.PeerResolvers.CustomPeerResolverService>   
 <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>   
 <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>   
 <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>   
 [Одноранговые распознаватели](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)   
 [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/ru-ru/12aa3787-2962-439c-ad27-46523c8b0419)