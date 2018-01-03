---
title: '&lt;system.serviceModel&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#system.ServiceModel
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.ServiceModel
helpviewer_keywords:
- <system.serviceModel> element
- system.serviceModel element
ms.assetid: 78519531-ad7a-40d3-b3e7-42f1103d8854
caps.latest.revision: "26"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 02bf740794b1551d3b130922939dbb27e572578e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="ltsystemservicemodelgt"></a>&lt;system.serviceModel&gt;
Данный раздел конфигурации содержит все элементы конфигурации ServiceModel для [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)].  
  
## <a name="syntax"></a>Синтаксис  
  
```xml  
<system.serviceModel>  
  <behaviors>  
  </behaviors>  
  <bindings>  
  </bindings>  
  <client>  
  </client>  
  <comContracts>  
  </comContracts>  
  <commonBehaviors>  
  </commonBehaviors>  
  <diagnostics>  
  </diagnostics>  
  <extensions>  
  </extensions>
  <protocolMapping>
  </protocolMapping>
  <routing>
  </routing>  
  <serviceHostingEnvironment>  
  </serviceHostingEnvironment>  
  <services>  
  </services>
  <standardEndpoints>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
 Нет  
  
### <a name="child-elements"></a>Дочерние элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|[\<поведения >](../../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md)|Данный раздел определяет две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.  Каждая коллекция определяет элементы поведений, используемые конечными точками и службами соответственно. Каждый элемент поведения идентифицируется по уникальному атрибуту `name`.|  
|[\<привязки >](../../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md)|В этом разделе содержится коллекция стандартных и пользовательских привязок. Каждая запись идентифицируется по уникальному свойству `name`. Службы используют привязки, связывая их с помощью параметра `name`.|  
|[\<Клиент >](../../../../../docs/framework/configure-apps/file-schema/wcf/client.md)|Данный раздел содержит список конечных точек, которые клиент использует для подключения к службе.|  
|[\<comContracts >](../../../../../docs/framework/configure-apps/file-schema/wcf/comcontracts.md)|В данном разделе определяются контракты COM, которые разрешены для обеспечения взаимодействия WCF и COM.|  
|[\<commonBehaviors >](../../../../../docs/framework/configure-apps/file-schema/wcf/commonbehaviors.md)|Этот раздел может быть определен только в файле machine.config. В нем определяются две дочерние коллекции с именами `endpointBehaviors` и `serviceBehaviors`.  Каждая коллекция определяет элементы поведения, используемые соответственно всеми конечными точками [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] и службами на компьютере.  Если поведение определено как `<commonBehaviors>` и `<behaviors>` разделах, в \<поведения > отдается поведениям из раздела.|  
|[\<расширения >](../../../../../docs/framework/configure-apps/file-schema/wcf/extensions-section.md)|Данный раздел содержит коллекцию расширений, которые позволяют пользователю создавать определяемые пользователем привязки, поведения и другие виды расширений.|  
|[\<Диагностика >](../../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md)|В этом разделе содержатся параметры возможностей диагностики WCF. Пользователь может включить или отключить трассировку, счетчики производительности и провайдер инструментария WMI, а также может добавлять специальные фильтры сообщений.|  
|[\<protocolMapping >](../../../../../docs/framework/configure-apps/file-schema/wcf/protocolmapping.md)|Этот раздел определяет набор сопоставления протоколов по умолчанию между схемами транспортных протоколов (например, http, net.tcp, net.pipe, т. д.) и привязками WCF.|  
|[\<Маршрутизация >](../../../../../docs/framework/configure-apps/file-schema/wcf/routing.md)|Этот раздел определяет набор фильтров маршрутизации, которые определяют тип [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]<xref:System.ServiceModel.Dispatcher.MessageFilter>, используемый при оценке входящих сообщений, а также таблиц маршрутизации, которые определяют целевые конечные точки для отправки сообщений (в случае если фильтр срабатывает).|  
|[\<serviceHostingEnvironment >](../../../../../docs/framework/configure-apps/file-schema/wcf/servicehostingenvironment.md)|Этот раздел определяет тип, который среда размещения служб создает для определенного транспорта. Если данный раздел пуст, то используется тип, заданный по умолчанию.|  
|[\<службы >](../../../../../docs/framework/configure-apps/file-schema/wcf/services.md)|Раздел содержит коллекцию служб. Для каждой службы, определенной в сборке, данный элемент содержит элемент `service`, который задает параметры для данной службы.|  
|[\<standardEndpoints >](../../../../../docs/framework/configure-apps/file-schema/wcf/standardendpoints.md)|В этом разделе определяется коллекция конечных точек, которые являются пригодными для многократного использования стандартными конечными точками. Значение одного или нескольких атрибутов стандартной конечной точки, обозначающих адрес, привязку или контракт, является фиксированным. Например, в конечной точке обнаружения фиксированным является контракт. По аналогии с определением пользовательских привязок можно также использовать стандартные конечные точки для расширения конечной точки службы за счет новых свойств.|  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание:|  
|-------------|-----------------|  
|\<configuration>|Корневой элемент для всех элементов конфигурации в файле конфигурации .NET.|  
  
## <a name="remarks"></a>Примечания  
 [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] не добавляет элементы к разделам конфигурации других продуктов.  
  
 Службы [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] определяются в разделе `services` файла конфигурации. Сборка может содержать любое число служб. Для каждой службы используется собственный раздел конфигурации `service`. Этот раздел и его содержимое определяют контракт, поведение и конечные точки конкретной службы.  
  
 Обязательным является только атрибут `name`.  По умолчанию имя службы описывает базовый тип CLR, который используется для реализации службы, однако можно изменить свойство ConfigurationName в классе <xref:System.ServiceModel.ServiceContractAttribute>, чтобы изменить требования к типу CLR.  
  
 Атрибут `behaviorConfiguration` является необязательным. Он указывает поведение, используемое службой. Поведение, которое определяется данным атрибутом, должно быть связано с поведением службы, которое определяется в области того же файла конфигурации (то есть в том же файле или в родительском файле).  
  
 Каждая служба предоставляет одну или несколько конечных точек, которые определяются в элементе `endpoint`. Каждая конечная точка имеет свой адрес и привязку. Все привязки в файле конфигурации должны быть определены в области файла.  
  
 Привязки связаны с конечными точками через сочетание атрибутов `name` и `bindingConfiguration`. Атрибут `binding` указывает, в каком разделе определяется привязка. Атрибут `bindingConfiguration` указывает, какая из настроенных привязок используется в разделе привязки. В разделе привязки может определяться несколько настроенных привязок.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример файла конфигурации WCF.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
    <system.serviceModel>  
        <behaviors>  
           <!-- List of Behaviors -->  
        </behaviors>  
        <client>  
           <!-- List of Endpoints -->  
        </client>  
        <diagnostics wmiProviderEnabled="false" performanceCountersEnabled="false" tracingEnabled="false">  
        </diagnostics>  
        <serviceHostingEnvironment>  
           <!-- List of entries -->  
        </serviceHostingEnvironment>  
        <comContracts>  
           <!-- List of COM+ Contracts -->  
        </comContracts>          
        <services>  
           <!-- List of Services -->  
        </services>  
        <bindings>  
           <!-- List of Bindings -->  
        </bindings>  
    </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ServiceModelSectionGroup>
