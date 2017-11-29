---
title: "&lt;endpoint&gt; для &lt;client&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: de6238ae-bbf8-48e9-a1b5-e24c0bea8afa
caps.latest.revision: "22"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 87c83826d45942deb682087ad717070bd1ea4471
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltendpointgt-of-ltclientgt"></a>&lt;endpoint&gt; для &lt;client&gt;
Задает свойства контракта, привязки и адреса конечной точки канала, которая используется клиентами для подключения к конечным точкам службы на сервере.  
  
 \<система. ServiceModel >  
\<Клиент >  
\<Конечная точка >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<endpoint address="String"  
   behaviorConfiguration="String"  
   binding="String"  
   bindingConfiguration="String"  
   contract="String"   endpointConfiguration="String"   kind="String"  
   name="String"  
</endpoint>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|address|Обязательный строковый атрибут.<br /><br /> Задает адрес конечной точки. Значение по умолчанию - пустая строка. Адрес должен быть абсолютным универсальным кодом ресурса (URI).|  
|behaviorConfiguration|Строка, содержащая имя поведения, используемое для создания экземпляра конечной точки. Имя поведения должно входить в область действия в точке определения службы. Значение по умолчанию - пустая строка.|  
|привязка|Обязательный строковый атрибут.<br /><br /> Строка, указывающая тип привязки для использования. Чтобы на тип можно было ссылаться, он должен иметь зарегистрированный раздел конфигурации. Тип регистрируется по имени раздела, а не по имени типа привязки.|  
|bindingConfiguration|Необязательно. Строка, содержащая имя конфигурации привязки для использования при создании экземпляра конечной точки. Конфигурация привязки должна входить в область действия в точке определения конечной точки. Значение по умолчанию - пустая строка.<br /><br /> Этот атрибут используется вместе с атрибутом `binding` для ссылки на конкретную конфигурацию привязки в файле конфигурации. Задайте этот атрибут, если выполняется попытка использовать пользовательскую привязку. В противном случае может быть создано исключение.|  
|контракт|Обязательный строковый атрибут.<br /><br /> Строка, указывающая, к какому контракту предоставляется доступ этой конечной точкой. В сборке должен быть реализован данный тип контракта.|  
|endpointConfiguration|Строка, указывающая имя стандартной конечной точки, задаваемой атрибутом `kind`, который ссылается на дополнительные сведения конфигурации этой конечной точки. Такое же имя должно быть задано в разделе `<standardEndpoints>`.|  
|kind|Строка, указывающая тип применяемой стандартной конечной точки. Этот тип должен быть зарегистрирован в разделе `<extensions>` или в файле machine.config. Если ничего не указано, будет создана обычная конечная точка канала.|  
|имя|Необязательный строковый атрибут. Этот атрибут уникальным образом идентифицирует конечную точку для данного контракта. Для данного типа контракта можно определить несколько клиентов. Определения должны отличаться друг от друга уникальным именем конфигурации. Если этот атрибут опущен, соответствующая конечная точка используется как конечная точка по умолчанию, связанная с заданным типом контракта. Значение по умолчанию - пустая строка.<br /><br /> Атрибут `name` привязки используется для экспорта определения посредством языка WSDL.|  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<заголовки >](../../../../../docs/framework/configure-apps/file-schema/wcf/headers.md)|Коллекция заголовков адреса.|  
|[\<удостоверение >](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|Удостоверение, обеспечивающее проверку подлинности конечной точки другими конечными точками, которые обмениваются с ней сообщениями.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<Клиент >](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|Раздел конфигурации, определяющий список конечных точек, к которым может подключаться клиент.|  
  
## <a name="example"></a>Пример  
 Далее приведен пример конфигурации конечной точки канала.  
  
```xml  
<endpoint address="/HelloWorld/"  
    bindingConfiguration="usingDefaults"  
    name="MyBinding"  
    binding="customBinding"  
    contract="HelloWorld">  
</endpoint>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 <xref:System.ServiceModel.Configuration.ClientSection>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElementCollection>  
 <xref:System.ServiceModel.Configuration.ClientSection.Endpoints%2A>  
 <xref:System.ServiceModel.Configuration.ChannelEndpointElement>  
 [Конфигурация клиента WCF](../../../../../docs/framework/wcf/feature-details/client-configuration.md)  
 [Клиенты](../../../../../docs/framework/wcf/feature-details/clients.md)
