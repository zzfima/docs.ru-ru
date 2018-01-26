---
title: "&lt;add&gt; для &lt;protocolMapping&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 08e62249-1641-41d1-91b1-66d7b46244e4
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6a254b8a4de8f66cb0d051d246be2d07e905615a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltaddgt-of-ltprotocolmappinggt"></a>&lt;add&gt; для &lt;protocolMapping&gt;
Представляет сопоставление протокола по умолчанию между схемой транспортного протокола (например, http, net.tcp, net.pipe, т. д.) и [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] привязки. При создании конечных точек по умолчанию во время выполнения [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] просматривает заданные сопоставления и решает, какую привязку необходимо использовать для определенного базового адреса.  
  
 \<system.serviceModel >  
\<protocolMapping >  
\<add>  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
   <protocolMapping>    <add binding="String"         bindingConfiguration="String"         scheme="http/net.msmq/net.pipe/net.tcp"/></protocolMapping>
```

## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Элемент|Описание|  
|-------------|-----------------|  
|привязка|Строка, в которой указан тип привязки, используемый для конечной точки во время создания конечной точки по умолчанию.|  
|bindingConfiguration|Строка, содержащая имя раздела конфигурации привязки, на который будет установлена ссылка.|  
|scheme|Схема транспортного протокола, которая будет использоваться для конечной точки по умолчанию.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Отсутствует.  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<protocolMapping >](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Представляет раздел конфигурации для определения сопоставлений протоколов по умолчанию между схемами транспортных протоколов (например, http, net.tcp, net.pipe, т. д.) и [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] привязки.|  
  
## <a name="example"></a>Пример  
 В следующем примере конфигурации показано сопоставление протокола по умолчанию в файле machine.config. Это сопоставление по умолчанию можно переопределить на уровне компьютера путем изменения файла machine.config. Или же, если необходимо переопределить это сопоставление только в области приложения, можно отменить этот раздел в файле конфигурации приложения и изменить сопоставление для отдельных схем протокола.  
  
```xml  
<protocolMapping>  
        <add scheme="http" binding="basicHttpBinding"/>  
        <add scheme="net.tcp" binding="netTcpBinding"/>  
        <add scheme="net.pipe" binding="netNamedPipeBinding"/>  
        <add scheme="net.msmq" binding="netMsmqBinding"/>  
</protocolMapping>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ProtocolMappingSection?displayProperty=nameWithType>      
 <xref:System.ServiceModel.Configuration.ProtocolMappingElement?displayProperty=nameWithType>    
