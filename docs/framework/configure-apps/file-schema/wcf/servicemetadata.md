---
title: "&lt;serviceMetadata&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 2b4c3b4c-31d4-4908-a9b7-5bb411c221f2
caps.latest.revision: 28
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 28
---
# &lt;serviceMetadata&gt;
Задает публикацию метаданных службы и связанных сведений.  
  
## Синтаксис  
  
```  
  
<serviceMetadata   
    externalMetadataLocation="String"  
    httpGetBinding=”String”  
    httpGetBindingConfiguration=”String”  
    httpGetEnabled="Boolean"   
    httpGetUrl="String"  
    httpsGetBinding=”String”  
    httpsGetBindingConfiguration=”String”  
    httpsGetEnabled="Boolean"   
    httpsGetUrl="String"  
    policyVersion="Policy12/Policy15"/>  
```  
  
## Атрибуты и элементы  
 В следующих разделах описаны атрибуты, дочерние и родительские элементы.  
  
### Атрибуты  
  
|Атрибут|Описание|  
|-------------|--------------|  
|externalMetadataLocation|Универсальный код ресурса \(URI\), содержащий местоположение WSDL\-файла, возвращаемый пользователю в ответ на запросы WSDL и MEX, вместо автоматически создаваемых WSDL.  Если атрибут не задан, по умолчанию возвращается WSDL.  Значение по умолчанию \- пустая строка.|  
|httpGetBinding|Строковое значение, в котором указывается тип привязки, используемой для загрузки метаданных посредством HTTP GET.  Этот параметр является необязательным.  Если он не указан, то будут использоваться привязки по умолчанию.<br /><br /> Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>.  Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion%2A> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.|  
|httpGetBindingConfiguration|Строка, задающая имя привязки, указанной атрибутом `httpGetBinding`, который ссылается на дополнительные сведения конфигурации этой привязки.  Такое же имя должно быть задано в разделе `<bindings>`.|  
|httpGetEnabled|Логическое значение, указывающее, следует ли опубликовывать метаданные службы для извлечения с помощью запроса HTTP\-GET.  Значение по умолчанию — `false`.<br /><br /> Если атрибут httpGetUrl не указан, адрес, по которому публикуются метаданные, \- это адрес службы плюс «?wsdl».  Например, если адрес службы \- "http:\/\/localhost:8080\/CalculatorService", то адрес метаданных HTTP\/Get будет иметь вид "http:\/\/localhost:8080\/CalculatorService?wsdl".<br /><br /> Если это свойство имеет значение `false` или адрес службы не основан на HTTP или HTTPS, суффикс "?wsdl" игнорируется.|  
|httpGetUrl|URI, указывающий адрес, по которому метаданные публикуются для извлечения с использованием запроса HTTP\-GET.  Если указан относительный URI, то он будет обрабатываться относительно базового адреса службы.|  
|httpsGetBinding|Строковое значение, в котором указывается тип привязки, используемой для загрузки метаданных посредством HTTPS GET.  Этот параметр является необязательным.  Если он не указан, то будут использоваться привязки по умолчанию.<br /><br /> Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>.  Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion%2A> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.|  
|httpsGetBindingConfiguration|Строка, задающая имя привязки, указанной атрибутом `httpsGetBinding`, который ссылается на дополнительные сведения конфигурации этой привязки.  Такое же имя должно быть задано в разделе `<bindings>`.|  
|httpsGetEnabled|Логическое значение, указывающее, следует ли опубликовывать метаданные службы для извлечения с помощью запроса HTTPS\-GET.  Значение по умолчанию — `false`.<br /><br /> Если атрибут httpsGetUrl не указан, адрес, по которому публикуются метаданные, \- это адрес службы плюс «?wsdl».  Например, если адрес службы \- "https:\/\/localhost:8080\/CalculatorService", то адрес метаданных HTTPS\/Get будет иметь вид "https:\/\/localhost:8080\/CalculatorService?wsdl".<br /><br /> Если это свойство имеет значение `false` или адрес службы не основан на HTTP или HTTPS, суффикс "?wsdl" игнорируется.|  
|httpsGetUrl|URI, указывающий адрес, по которому метаданные публикуются для извлечения с использованием запроса HTTPS\-GET.|  
|policyVersion|Строка, указывающая версию используемой спецификации Web Services Policy.  Это атрибут типа <xref:System.ServiceModel.Description.PolicyVersion>.|  
  
### Дочерние элементы  
 Нет  
  
### Родительские элементы  
  
|Элемент|Описание|  
|-------------|--------------|  
|[\<поведение\>](../../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md)|Указывает элемент поведения.|  
  
## Заметки  
 Элемент конфигурации позволяет управлять функциями публикации метаданных службы.  Чтобы предотвратить непреднамеренное разглашение потенциально важных метаданных службы, в конфигурации служб [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] публикация метаданных по умолчанию отключена.  Такое расширение функциональности по умолчанию защищено, но это также означает, что при этом невозможно использовать средство импорта метаданных \(например, Svcutil.exe\) для создания клиентского кода, необходимого для вызова службы, если поведение публикации не включено явно в конфигурации.  Включить такое поведение публикации для службы можно с помощью элемента конфигурации.  
  
 Подробный пример кода, иллюстрирующий настройку такого поведения, представлен в разделе [Поведение публикации метаданных](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md).  
  
 Дополнительные атрибуты `httpGetBinding` и `httpsGetBinding` позволяют настроить привязки, используемые для извлечения метаданных посредством HTTP\-GET \(или HTTPS\-GET\).  Если они не заданы, для извлечения метаданных применяются привязки по умолчанию \(`HttpTransportBindingElement` для HTTP и `HttpsTransportBindingElement` для HTTPS\).  Обратите внимание, что эти атрибуты нельзя использовать вместе со встроенными привязками WCF.  Поддерживаются только привязки с внутренними элементами привязки, поддерживающими <xref:System.ServiceModel.Channels.IReplyChannel>.  Кроме этого, свойство <xref:System.ServiceModel.Channels.MessageVersion%2A> привязки должно иметь значение <xref:System.ServiceModel.Channels.MessageVersion.None%2A>.  
  
 Для снижения подверженности службы действиям недобросовестных пользователей перенос можно защитить с помощью механизма SSL по протоколу HTTP \(HTTPS\).  Для этого необходимо вначале выполнить привязку подходящего сертификата X.509 к конкретному порту компьютера, на котором размещена служба.  \([!INCLUDE[crdefault](../../../../../includes/crdefault-md.md)] [Работа с сертификатами](../../../../../docs/framework/wcf/feature-details/working-with-certificates.md).\) Затем необходимо добавить этот элемент в конфигурацию службы и задать атрибуту `httpsGetEnabled` значение `true`.  После этого следует присвоить атрибуту `httpsGetUrl` URL\-адрес конечной точки метаданных службы, как показано в следующем примере.  
  
```  
<behaviors>  
 <serviceBehaviors>  
  <behavior name="NewBehavior">  
    <serviceMetadata httpsGetEnabled="true"   
     httpsGetUrl="https://myComputerName/myEndpoint" />  
  </behavior>  
 </serviceBehaviors>  
</behaviors>  
```  
  
## Пример  
 В следующем примере выполняется настройка службы так, чтобы обеспечить доступ к метаданным с использованием элемента \<serviceMetadata\>.  Здесь также настраивается конечная точка предоставления доступа к контракту `IMetadataExchange` как реализации протокола WS\-MetadataExchange \(MEX\).  В примере используется привязка `mexHttpBinding`, являющаяся удобной стандартной привязкой, эквивалентной привязке `wsHttpBinding` с режимом безопасности `None`.  Относительный адрес «mex» используется в конечной точке, которая при разрешении относительно базового адреса службы приводит к созданию адреса конечной точки http:\/\/localhost\/servicemodelsamples\/service.svc\/mex.  
  
```  
<configuration>  
<system.serviceModel>  
  <services>  
    <service   
        name="Microsoft.ServiceModel.Samples.CalculatorService"  
        behaviorConfiguration="CalculatorServiceBehavior">  
      <!-- This endpoint is exposed at the base address provided by the host: http://localhost/servicemodelsamples/service.svc  -->  
      <endpoint address=""  
                binding="wsHttpBinding"  
                contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      <!-- the mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex   
           To expose the IMetadataExchange contract, you   
           must enable the serviceMetadata behavior as demonstrated below -->  
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
  
## См. также  
 <xref:System.ServiceModel.Configuration.ServiceMetadataPublishingElement>   
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>   
 [Поведения безопасности](../../../../../docs/framework/wcf/feature-details/security-behaviors-in-wcf.md)   
 [Поведение публикации метаданных](../../../../../docs/framework/wcf/samples/metadata-publishing-behavior.md)