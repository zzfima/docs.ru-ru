---
title: "&lt;pnrpPeerResolver&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c1b34f3b-68e5-4911-a367-de49fb61dbc6
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# &lt;pnrpPeerResolver&gt;
Задает использование распознавателя протокола PNRP \(протокола однорангового разрешения имен\) в качестве распознавателя.  Этот элемент является необязательным, поскольку протокол PNRP является распознавателем по умолчанию.  
  
## Синтаксис  
  
```  
  
<pnrpResolver resolverType="String" />  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|resolverType|Строка, указывающая распознаватель для использования.  Этот атрибут является необязательным.  Если значение не задано или равно пустой строке, используется протокол PNRP.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<привязка\>](../../../../../docs/framework/misc/binding.md)|Определяет все возможности пользовательской привязки.|  
  
## Пример  
  
```  
<pnrpResolver resolverType="" />  
```  
  
## См. также  
 <xref:System.ServiceModel.Configuration.PnrpPeerResolverElement>   
 <xref:System.ServiceModel.Channels.PnrpPeerResolverBindingElement>   
 <xref:System.ServiceModel.Channels.CustomBinding>   
 [Привязки](../../../../../docs/framework/wcf/bindings.md)   
 [Расширение привязок](../../../../../docs/framework/wcf/extending/extending-bindings.md)   
 [Пользовательские привязки](../../../../../docs/framework/wcf/extending/custom-bindings.md)   
 [\<customBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)   
 [Одноранговые распознаватели](../../../../../docs/framework/wcf/feature-details/peer-resolvers.md)