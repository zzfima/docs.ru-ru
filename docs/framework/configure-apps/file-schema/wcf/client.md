---
title: <client>
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel/client
- http://schemas.microsoft.com/.NetConfiguration/v2.0#client
ms.assetid: bf0f7031-76c8-4e7e-a6c6-9ad9119134be
ms.openlocfilehash: 7dce5984882e48c3e62efc44ef00b6256d9eb64e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919530"
---
# <a name="client"></a>\<> клиента
Элемент `client` определяет список конечных точек, к которым может подключаться клиент.  
  
 \<системой. > ServiceModel  
\<> клиента  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>
  <client>
    <endpoint>
    </endpoint>
    <metadata>
    </metadata>
  </client>
</system.serviceModel>
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Отсутствуют  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<> конечной точки](endpoint-of-client.md)|Содержит коллекцию элементов конечных точек, указывающую конечные точки, к которым может подключиться данный клиент.|  
|[\<> метаданных](metadata.md)|Содержит параметры обработки метаданных.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<system.serviceModel>](system-servicemodel.md)|Корневой элемент всех элементов конфигурации Windows Communication Foundation (WCF).|  
  
## <a name="remarks"></a>Примечания  
 В разделе `client` определяется список конечных точек, к которым может подключаться клиент. Каждая конечная точка, указанная в разделе клиента, определяет свои собственные привязку, поведение и контракт. Она однозначно определяется сочетанием атрибутов `name` и `contract`. В коде клиента указывается атрибут `name` для подключения к конечной точке службы, выполняемой клиентом. Если атрибут `name` отсутствует, конечная точка действует как конечная точка по умолчанию для контракта, который она реализует.  
  
 Кроме того, в данном разделе также задаются параметры обработки метаданных.  
  
## <a name="example"></a>Пример  
  
```xml  
<client>
  <endpoint address="/HelloWorld/"
            bindingConfiguration="usingDefaults"
            name="MyBinding"
            binding="customBinding"
            contract="HelloWorld">
    <addressProperties actingAs="http://www.microsoft.com/TestActor"
                       identityData="BasicReadWrite"
                       identityType="Spn"
                       isAddressPrivate="false">
  </endpoint>
</client>
```  
  
## <a name="see-also"></a>См. также

- <xref:System.ServiceModel.Configuration.ClientSection>
- <xref:System.ServiceModel.Configuration.MetadataElement>
- [Конфигурация клиента WCF](../../../wcf/feature-details/client-configuration.md)
- [Клиенты](../../../wcf/feature-details/clients.md)
