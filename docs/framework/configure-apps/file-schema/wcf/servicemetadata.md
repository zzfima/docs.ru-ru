---
title: '&lt;serviceMetadata&gt;'
ms.date: 03/30/2017
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
ms.openlocfilehash: 3c59a47f8a45fbccb05eb1f385215fe2aa739836
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32751794"
---
# <a name="ltservicemetadatagt"></a>&lt;serviceMetadata&gt;
Задает публикацию метаданных службы и связанных сведений.  
  
\<system.serviceModel >  
\<поведения >  
\<serviceBehaviors >  
\<поведение >  
\<serviceMetadata >  
  
## <a name="syntax"></a>Синтаксис  
  
```xml
<serviceMetadata externalMetadataLocation="String"  
                 httpGetBinding="String" 
                 httpGetBindingConfiguration="String"  
                 httpGetEnabled="Boolean" 
                 httpGetUrl="String" 
                 httpsGetBinding="String" 
                 httpsGetBindingConfiguration="String"  
                 httpsGetEnabled="Boolean"   
                 httpsGetUrl="String"  
                 policyVersion="Policy12/Policy15" />  
```  
  
## <a name="attributes-and-elements"></a>Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### <a name="attributes"></a>Атрибуты  
  
|Атрибут|Описание|  
|---------------|-----------------|  
|externalMetadataLocation|Универсальный код ресурса (URI), содержащий местоположение WSDL-файла, возвращаемый пользователю в ответ на запросы WSDL и MEX, вместо автоматически создаваемых WSDL. Если атрибут не задан, по умолчанию возвращается WSDL. Значение по умолчанию - пустая строка.|  
|httpGetBinding|Строковое значение, в котором указывается тип привязки, используемой для загрузки метаданных посредством HTTP GET. Этот параметр является необязательным. Если он не указан, то будут использоваться привязки по умолчанию.<br /><br /> Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>. Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.|  
|httpGetBindingConfiguration|Строка, задающая имя привязки, указанной атрибутом `httpGetBinding`, который ссылается на дополнительные сведения конфигурации этой привязки. Такое же имя должно быть задано в разделе `<bindings>`.|  
|httpGetEnabled|Логическое значение, указывающее, следует ли опубликовывать метаданные службы для извлечения с помощью запроса HTTP-GET. Значение по умолчанию — `false`.<br /><br /> Если атрибут httpGetUrl не указан, адрес, по которому публикуются метаданные, - это адрес службы плюс «?wsdl». Например, если адресом службы является «http://localhost:8080/CalculatorService«, то адрес метаданных HTTP/Get будет»http://localhost:8080/CalculatorService?wsdl».<br /><br /> Если это свойство имеет `false`, или адрес службы не основан на HTTP или HTTPS, «? wsdl» игнорируется.|  
|httpGetUrl|URI, указывающий адрес, по которому метаданные публикуются для извлечения с использованием запроса HTTP-GET. Если указан относительный URI, то он будет обрабатываться относительно базового адреса службы.|  
|httpsGetBinding|Строковое значение, в котором указывается тип привязки, используемой для загрузки метаданных посредством HTTPS GET. Этот параметр является необязательным. Если он не указан, то будут использоваться привязки по умолчанию.<br /><br /> Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>. Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.|  
|httpsGetBindingConfiguration|Строка, задающая имя привязки, указанной атрибутом `httpsGetBinding`, который ссылается на дополнительные сведения конфигурации этой привязки. Такое же имя должно быть задано в разделе `<bindings>`.|  
|httpsGetEnabled|Логическое значение, указывающее, следует ли опубликовывать метаданные службы для извлечения с помощью запроса HTTPS-GET. Значение по умолчанию — `false`.<br /><br /> Если атрибут httpsGetUrl не указан, адрес, по которому публикуются метаданные, - это адрес службы плюс «?wsdl». Например, если адресом службы является «https://localhost:8080/CalculatorService«, то адрес метаданных HTTP/Get будет»https://localhost:8080/CalculatorService?wsdl».<br /><br /> Если это свойство имеет `false`, или адрес службы не основан на HTTP или HTTPS, «? wsdl» игнорируется.|  
|httpsGetUrl|URI, указывающий адрес, по которому метаданные публикуются для извлечения с использованием запроса HTTPS-GET.|  
|policyVersion|Строка, указывающая версию используемой спецификации Web Services Policy. Это атрибут типа <xref:System.ServiceModel.Description.PolicyVersion>.|  
  
### <a name="child-elements"></a>Дочерние элементы  
 Нет  
  
### <a name="parent-elements"></a>Родительские элементы  
  
|Элемент|Описание|  
|-------------|-----------------|  
|[\<поведение >](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## <a name="remarks"></a>Примечания  
 Элемент конфигурации позволяет управлять возможностями публикации метаданных службы. Чтобы предотвратить непреднамеренное разглашение потенциально важных метаданных службы, конфигурации по умолчанию для службы Windows Communication Foundation (WCF) отключает публикацию метаданных. Такое расширение функциональности по умолчанию защищено, но это также означает, что при этом невозможно использовать средство импорта метаданных (например, Svcutil.exe) для создания клиентского кода, необходимого для вызова службы, если поведение публикации не включено явно в конфигурации. Включить такое поведение публикации для службы можно с помощью элемента конфигурации.  
  
 Подробный пример настройки этого поведения см. в разделе [поведения публикации метаданных](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).  
  
 Дополнительные атрибуты `httpGetBinding` и `httpsGetBinding` позволяют настроить привязки, используемые для извлечения метаданных посредством HTTP-GET (или HTTPS-GET). Если они не заданы, для извлечения метаданных применяются привязки по умолчанию (`HttpTransportBindingElement` для HTTP и `HttpsTransportBindingElement` для HTTPS). Обратите внимание, что эти атрибуты нельзя использовать вместе со встроенными привязками WCF. Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>. Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  
  
 Для снижения подверженности службы действиям недобросовестных пользователей перенос можно защитить с помощью механизма SSL по протоколу HTTP (HTTPS). Для этого необходимо вначале выполнить привязку подходящего сертификата X.509 к конкретному порту компьютера, на котором размещена служба. (Дополнительные сведения см. в разделе [работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).) Затем необходимо добавить этот элемент в конфигурацию службы и задать атрибуту `httpsGetEnabled` значение `true`. После этого следует присвоить атрибуту `httpsGetUrl` URL-адрес конечной точки метаданных службы, как показано в следующем примере.  
  
```xml
<behaviors>  
  <serviceBehaviors>  
    <behavior name="NewBehavior">  
      <serviceMetadata httpsGetEnabled="true"   
                       httpsGetUrl="https://myComputerName/myEndpoint" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
## <a name="example"></a>Пример  
 Следующий пример настроить службу для предоставления метаданных с помощью \<serviceMetadata > элемент. Здесь также настраивается конечная точка предоставления доступа к контракту `IMetadataExchange` как реализации протокола WS-MetadataExchange (MEX). В примере используется привязка `mexHttpBinding`, являющаяся удобной стандартной привязкой, эквивалентной привязке `wsHttpBinding` с режимом безопасности `None`. Относительный адрес «MEX» используется в конечной точке, которая при разрешении со службами базовый адрес приводит к созданию адреса конечной точки http://localhost/servicemodelsamples/service.svc/mex.  
  
```xml
<configuration>  
  <system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService" 
               behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc -->  
        <endpoint address=""  
                  binding="wsHttpBinding"  
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex   
             To expose the IMetadataExchange contract, you must enable the serviceMetadata behavior as demonstrated below. -->  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <!-- The serviceMetadata behavior publishes metadata through   
               the IMetadataExchange contract. When this behavior is   
               present, you can expose this contract through an endpoint   
               as shown above. Setting httpGetEnabled to true publishes   
               the service's WSDL at the <baseaddress>?wsdl  
               eg. http://localhost/servicemodelsamples/service.svc?wsdl -->  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)  
 [Поведение публикации метаданных](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)
