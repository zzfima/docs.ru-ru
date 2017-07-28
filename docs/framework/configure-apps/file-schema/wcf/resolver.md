---
title: "&lt;resolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# &lt;resolver&gt;
Указывает распознаватель одноранговых узлов, используемый для распознавания идентификатора сетки с IP\-адресами в набор адресов одноранговых узлов, которые представляют несколько узлов, входящих в сетку.  
  
## Синтаксис  
  
```  
  
<resolver mode="Auto/Custom/Pnrp"  
   referralPolicy="DoNotShare/Service/Share">  
</resolver>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|`mode`|Строка, которая указывает, зависит ли экземпляр распознавателя одноранговых узлов, связанный с данной службой, от PNRP, является ли он пользовательским распознавателем или определяется автоматически.  Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.|  
|`referralPolicy`|Строка, указывающая, каким образом отсылки распределяются между одноранговыми узлами.  Это атрибут типа <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.|  
  
### Дочерние элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<верхние колонтитулы\>](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|Задает параметры службы пользовательского распознавателя одноранговых узлов.|  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности привязки [\<netPeerTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/netpeertcpbinding.md).|  
  
## Заметки  
 Распознаватель одноранговых узлов представляет собой службу обнаружения, используемую одноранговыми каналами для поиска одноранговых узлов, участвующих в сетке с IP\-адресами.  Он также используется для «регистрации» узла в сетке с IP\-адресами; с помощью такого механизма одноранговый узел становится известным и доступным из сетки с IP\-адресами.  Дополнительные сведения о распознавателях одноранговых узлов см. в разделе [Одноранговые распознаватели](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md).  
  
## См. также  
 <xref:System.ServiceModel.PeerResolver>   
 <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>   
 <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>   
 <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>   
 <xref:System.ServiceModel.Configuration.PeerResolverElement>   
 [Одноранговые распознаватели](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)   
 [Adding a Custom Resolver to a PeerChannel Application](http://msdn.microsoft.com/ru-ru/12aa3787-2962-439c-ad27-46523c8b0419)