---
title: "ServiceDescription и справочная информация о WSDL | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: eedc025d-abd9-46b1-bf3b-61d2d5c95fd6
caps.latest.revision: 15
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 15
---
# ServiceDescription и справочная информация о WSDL
В этом разделе описывается, как [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] сопоставляет документы на языке WSDL с экземплярами <xref:System.ServiceModel.Description.ServiceDescription> и наоборот.  
  
## Сопоставление ServiceDescription с WSDL 1.1  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет экспортировать документы WSDL из экземпляра <xref:System.ServiceModel.Description.ServiceDescription> созданной службы.  При публикации конечных точек метаданных документы WSDL формируются для службы автоматически.  
  
 Также можно импортировать экземпляры <xref:System.ServiceModel.Description.ServiceEndpoint>, экземпляры <xref:System.ServiceModel.Description.ContractDescription> и экземпляры <xref:System.ServiceModel.Channels.Binding> из документов WSDL, используя для этого тип `WsdlImporter`.  
  
 В экспортируемые [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] документы WSDL импортируются все используемые определения схемы XML из внешних документов схем XML.  Для каждого целевого пространства имен, используемого в типах данных в службе, экспортируется отдельный документ схемы XML.  Аналогично, для каждого целевого пространства имен, используемого в контрактах служб, экспортируется отдельный документ WSDL.  
  
### ServiceDescription  
 Экземпляр <xref:System.ServiceModel.Description.ServiceDescription> сопоставляется с элементом `wsdl:service`.  Экземпляр <xref:System.ServiceModel.Description.ServiceDescription> содержит коллекцию экземпляров <xref:System.ServiceModel.Description.ServiceEndpoint>, каждый из которых сопоставляется с отдельным элементом `wsdl:port`.  
  
|Свойства|Сопоставление с WSDL|  
|--------------|--------------------------|  
|`Name`|Значение `wsdl:service`\/@name для службы.|  
|`Namespace`|Целевое пространство имен \(targetNamespace\) для определения `wsdl:service` для службы.|  
|`Endpoints`|Определения `wsdl:port` для службы.|  
  
### ServiceEndpoint  
 Экземпляр <xref:System.ServiceModel.Description.ServiceEndpoint> сопоставляется с элементом `wsdl:port`.  Экземпляр <xref:System.ServiceModel.Description.ServiceEndpoint> содержит адрес, привязку и контракт.  
  
 Поведения конечной точки, реализующие интерфейс <xref:System.ServiceModel.Description.IWsdlExportExtension>, могут изменять элемент `wsdl:port` для конечной точки, к которой они прикреплены.  
  
|Свойства|Сопоставление с WSDL|  
|--------------|--------------------------|  
|`Name`|Значение `wsdl:port`\/@name для конечной точки и значение `wsdl:binding`\/@name для привязки конечной точки.|  
|`Address`|Адрес для определения `wsdl:port` для конечной точки.<br /><br /> Формат адреса определяется транспортом для конечной точки.  Например, для поддерживаемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] транспортов это может быть адрес SOAP или ссылка на конечную точку.|  
|`Binding`|Определение `wsdl:binding` для конечной точки.<br /><br /> В отличие от определений `wsdl:binding`, привязки в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не связаны с каким\-либо одним контрактом.|  
|`Contract`|Определение `wsdl:portType` для конечной точки.|  
|`Behaviors`|Поведения конечной точки, реализующие интерфейс <xref:System.ServiceModel.Description.IWsdlExportExtension>, могут изменять элемент `wsdl:port` для конечной точки.|  
  
### Привязки  
 Экземпляр привязки `ServiceEndpoint` сопоставляется с определением `wsdl:binding`.  В отличие от определений `wsdl:binding`, которые должны быть связаны с конкретным определением `wsdl:portType`, привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не зависимы от какого\-либо контракта.  
  
 Привязка состоит из коллекции элементов привязки.  Каждый элемент описывает некоторый аспект взаимодействия конечной точки с клиентами.  Кроме того, каждая привязка имеет свойство <xref:System.ServiceModel.Channels.MessageVersion>, которое указывает версию конверта \(<xref:System.ServiceModel.EnvelopeVersion>\) и версию адресации \(<xref:System.ServiceModel.Channels.AddressingVersion>\) для конечной точки.  
  
|Свойства|Сопоставление с WSDL|  
|--------------|--------------------------|  
|`Name`|Используется в имени по умолчанию конечной точки, которое состоит из имени привязки и имени контракта, разделенных символом подчеркивания.|  
|`Namespace`|`targetNamespace` для определения `wsdl:binding`.<br /><br /> При импорте, если политика прикреплена к порту WSDL, импортируемое пространство имен привязки сопоставляется с `targetNamespace` для определения `wsdl:port`.|  
|`BindingElementCollection`, возвращаемое методом `CreateBindingElements`\(\)|Различные зависящие от домена расширения определения `wsdl:binding`, обычно утверждения политики.|  
|`MessageVersion`|`EnvelopeVersion` и `AddressingVersion` для конечной точки.<br /><br /> Если задано свойство `MessageVersion.None`, привязка WSDL не содержит привязки SOAP, а порт WSDL не содержит данных о WS\-Addressing.  Этот вариант обычно используется для конечных точек POX \(передающих сообщения в формате "plain old XML"\).|  
  
#### BindingElements  
 Элементы привязки для привязки конечной точки сопоставляются с различными расширениями WSDL в элементе `wsdl:binding`, такими как утверждения политики.  
  
 Элемент <xref:System.ServiceModel.Channels.TransportBindingElement> привязки определяет универсальный код ресурса \(URI\) для привязки SOAP.  
  
#### AddressingVersion  
 Свойство `AddressingVersion` привязки сопоставляется с версией адресации, используемой в элементе `wsd:port`.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает адреса протоколов SOAP 1.1 и SOAP 1.2 и конечные точки WS\-Addressing 08\/2004 и WS\-Addressing 1.0.  
  
#### EnvelopeVersion  
 Свойство `EnvelopeVersion` привязки сопоставляется с версией адресации протокола SOAP, используемой в элементе `wsdl:binding`.  [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает привязки протоколов SOAP 1.1 и SOAP 1.2.  
  
### Контракты  
 Экземпляр <xref:System.ServiceModel.Description.ContractDescription> для экземпляра `ServiceEndpoint` сопоставляется с элементом `wsdl:portType`.  В экземпляре `ContractDescription` описываются все операции для данного контракта.  
  
|Свойства|Сопоставление с WSDL|  
|--------------|--------------------------|  
|`Name`|Значение `wsdl:portType`\/@name для контракта.|  
|`Namespace`|Целевое пространство имен \(targetNamespace\) для определения `wsdl:portType`.|  
|`SessionMode`|Значение `wsdl:portType`\/@msc:usingSession для контракта.  Этот атрибут является расширением [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для WSDL 1.1.|  
|`Operations`|Определения `wsdl:operation` для контракта.|  
  
### Операции  
 Экземпляр <xref:System.ServiceModel.Description.OperationDescription> сопоставляется с `wsdl:portType`\/`wsdl:operation`.  Экземпляр `OperationDescription` содержит коллекцию экземпляров `MessageDescription`, которые описывают сообщения для операции.  
  
 Два поведения операции играют большую роль в том, как `OperationDescription` сопоставляется с документом WSDL: `DataContractSerializerOperationBehavior` и `XmlSerializerOperationBehavior`.  
  
|Свойства|Сопоставление с WSDL|  
|--------------|--------------------------|  
|`Name`|Значение `wsdl:portType`\/`wsdl:operation`\/@name для операции.|  
|`ProtectionLevel`|Утверждения защиты в политике безопасности, прикрепленной к сообщениям `wsdl:binding/wsdl:operation` для этой операции.|  
|`IsInitiating`|Значение `wsdl:portType`\/`wsdl:operation`\/@msc:isInitiating для операции.  Этот атрибут является расширением [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для WSDL 1.1.|  
|`IsTerminating`|Значение `wsdl:portType`\/`wsdl:operation`\/@msc:isTerminating для операции.  Этот атрибут является расширением [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для WSDL 1.1.|  
|`Messages`|Сообщения `wsdl:portType`\/`wsdl:operation`\/`wsdl:input` и `wsdl:portType`\/`wsdl:operation`\/`wsdl:output` для операции.|  
|`Faults`|Определения `wsdl:portType``wsdl:operation``wsdl:fault` для операции.|  
|`Behaviors`|Поведения `DataContractSerializerOperationBehavior` и `XmlSerializerOperationBehavior` отвечают за привязку операции и сообщения операции.|  
  
#### DataContractSerializerOperationBehavior  
 Поведение `DataContractSerializerOperationBehavior` для операции представляет собой реализацию интерфейса `IWsdlExportExtension`, которая экспортирует сообщения и привязку WSDL для данной операции.  Типы схемы XML экспортируются с помощью `XsdDataContractExporter`.  Поведение `DataContractSerializerOperationBehavior` также определяет назначение, стиль, а также экспортер и импортер схемы, используемые для данной операции.  
  
|Свойства|Сопоставление с WSDL|  
|--------------|--------------------------|  
|`DataContractFormatAttribute`|Свойство `Style` для этого атрибута сопоставляется со значением `wsdl:binding`\/`wsdl:operation`\/`soap:operation`\/@style для операции.<br /><br /> `DataContractSerializerOperationBehavior` поддерживает только литеральное использование типов схемы в WSDL.|  
  
#### XmlSerializerOperationBehavior  
 Поведение `XmlSerializerOperationBehavior` для операции представляет собой реализацию интерфейса `IWsdlExportExtension`, которая экспортирует сообщения и привязку WSDL для данной операции.  Типы схемы XML экспортируются с помощью `XmlSchemaExporter`.  Поведение `XmlSerializerOperationBehavior` также определяет назначение, стиль, а также экспортер и импортер схемы, используемые для данной операции.  
  
|Свойства|Сопоставление с WSDL|  
|--------------|--------------------------|  
|`XmlSerializerFormatAttribute`|Свойство `Style` для этого атрибута сопоставляется со значением `wsdl:binding`\/`wsdl:operation`\/`soap:operation`\/@style для операции.<br /><br /> Свойство `Use` для этого атрибута сопоставляется со значениями `wsdl:binding`\/`wsdl:operation`\/`soap:operation`\/\*\/@use для всех сообщений в операции.|  
  
### Сообщения  
 Экземпляр `MessageDescription` сопоставляется с элементом `wsdl:message`, на который ссылается сообщение `wsdl:portType`\/`wsdl:operation`\/`wsdl:input` или сообщение `wsdl:portType`\/`wsdl:operation`\/`wsdl:output` в операции.  Экземпляр `MessageDescription` имеет тело и заголовки.  
  
|Свойства|Сопоставление с WSDL|  
|--------------|--------------------------|  
|`Action`|Действие SOAP или WS\-Addressing для сообщения.<br /><br /> Обратите внимание, что операции, в которых используется строка действия "\*", не отражаются в документе WSDL.|  
|`Direction`|`MessageDirection.Input` сопоставляется с `wsdl:input`.<br /><br /> `MessageDirection.Output` сопоставляется с `wsdl:output`.|  
|`ProtectionLevel`|Утверждения защиты в политике безопасности, прикрепленной к определению `wsdl:message` для этого сообщения.|  
|`Body`|Текст сообщения для сообщения.|  
|`Headers`|Заголовки для сообщения.|  
|`ContractDescription.Name`, `OperationContract.Name`|При экспорте используются для вывода значения `wsdl:message`\/@name.|  
  
#### Текст сообщения  
 Экземпляр `MessageBodyDescription` сопоставляется с определениями `wsdl:message`\/`wsdl:part` для текста сообщения.  Тело сообщения может быть заключено в оболочку или передаваться в режиме "bare".  
  
|Свойства|Сопоставление с WSDL|  
|--------------|--------------------------|  
|`WrapperName`|Если стиль \- не RPC, `WrapperName` сопоставляется с именем элемента, на которое ссылается `wsdl:message`\/`wsdl:part`, где @name равно "parameters".|  
|`WrapperNamespace`|Если стиль \- не RPC, `WrapperNamespace` сопоставляется с пространством имен элемента для `wsdl:message`\/`wsdl:part`, где @name равно "parameters".|  
|`Parts`|Части сообщения для данного тела сообщения.|  
|`ReturnValue`|Дочерний элемент элемента\-оболочки, если имеется элемент\-оболочка \(стиль упакованного документа \(document\/wrapped\), или стиль RPC\); в противном случае, первый элемент `wsdl:message`\/`wsdl:part` в сообщении.|  
  
#### Части сообщения  
 Экземпляр `MessagePartDescription` сопоставляется с элементом `wsdl:message`\/`wsdl:part` и типом схемы XML или элементом, на который указывает часть сообщения.  
  
|Свойства|Сопоставление с WSDL|  
|--------------|--------------------------|  
|`Name`|Значение `wsd:message`\/`wsdl:part`\/@name для части сообщения и имя элемента, на который указывает часть сообщения.|  
|`Namespace`|Пространство имен элемента, на который указывает часть сообщения.|  
|`Index`|Индекс элемента `wsdl:message`\/`wsdl:part` для сообщения.|  
|`ProtectionLevel`|Утверждения защиты в политике безопасности, прикрепленной к определению `wsdl:message` для этой части сообщения.  Политика параметризована для указания на конкретную часть сообщения.|  
|`MessageType`|Тип схемы XML элемента, на который указывает часть сообщения.|  
  
#### Заголовки сообщений  
 Экземпляр `MessageHeaderDescription` представляет собой часть сообщения, которая также сопоставляется с привязкой `soap:header` для части сообщения.  
  
### Ошибки  
 Экземпляр `FaultDescription` сопоставляется с определением `wsdl:portType`\/`wsdl:operation`\/`wsdl:fault` и связанным с ним определением `wsdl:message`.  Элемент `wsdl:message` добавляется в то же целевое пространство имен, что и связанный с ним тип порта WSDL.  Элемент `wsdl:message` имеет одну часть сообщения с именем "detail", которая указывает на элемент схемы XML, соответствующий значению свойства `DefaultType` для экземпляра `FaultDescription`.  
  
|Свойства|Сопоставление с WSDL|  
|--------------|--------------------------|  
|`Name`|Значение `wsdl:portType`\/`wsdl:operation`\/`wsdl:fault`\/@name для ошибки.|  
|`Namespace`|Пространство имен элемента схемы XML, на которое указывает часть "detail" сообщения ошибки.|  
|`Action`|Действие SOAP или WS\-Addressing для ошибки.|  
|`ProtectionLevel`|Утверждения защиты в политике безопасности, прикрепленной к определению `wsdl:message` для этой ошибки.|  
|`DetailType`|Тип схемы XML элемента, на который указывает часть "detail" сообщения.|  
|`Name, ContractDescription.Name, OperationDescription.Name,`|Используются для вывода значения `wsdl:message`\/@name для сообщения ошибки.|  
  
## См. также  
 <xref:System.ServiceModel.Description>