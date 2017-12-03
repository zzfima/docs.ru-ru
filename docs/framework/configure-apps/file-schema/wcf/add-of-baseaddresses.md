---
title: "&lt;add&gt; для &lt;baseAddresses&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bd7426f-5f4f-43fc-b8e9-de842219aa32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cf417653652c2a0f28fe5c6491a7da9949678140
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="ltaddgt-of-ltbaseaddressesgt"></a>&lt;add&gt; для &lt;baseAddresses&gt;
Представляет элемент конфигурации, который задает базовые адреса, используемые узлом службы.  
  
 \<система. ServiceModel >  
\<Клиент >  
\<Конечная точка >  
\<узел >  
\<baseAddresses >  
\<baseAddress >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<add baseAddress="string" />  
```  
  
## <a name="type"></a>Тип  
 `Type`  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|`baseAddress`|Строка, которая задает базовый адрес, используемый узлом службы.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<baseAddresses >](../../../../../docs/framework/configure-apps/file-schema/wcf/baseaddresses.md)|Коллекция элементов `baseAddress`.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.HostElement>  
 <xref:System.ServiceModel.ServiceHost>  
 <xref:System.ServiceModel.ServiceHostBase.BaseAddresses%2A>  
 [Размещение](../../../../../docs/framework/wcf/feature-details/hosting.md)
