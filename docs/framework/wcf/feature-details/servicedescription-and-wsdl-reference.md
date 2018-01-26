---
title: "ServiceDescription и справочная информация о WSDL"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: eedc025d-abd9-46b1-bf3b-61d2d5c95fd6
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7eadfaaae920071092f569fe2b8882875ed9497f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="servicedescription-and-wsdl-reference"></a>ServiceDescription и справочная информация о WSDL
В этом разделе описывается, как [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] сопоставляет документы на языке WSDL с экземплярами <xref:System.ServiceModel.Description.ServiceDescription> и наоборот.  
  
## <a name="how-servicedescription-maps-to-wsdl-11"></a>Сопоставление ServiceDescription с WSDL 1.1  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет экспортировать документы WSDL из экземпляра <xref:System.ServiceModel.Description.ServiceDescription> созданной службы. При публикации конечных точек метаданных документы WSDL формируются для службы автоматически.  
  
 Также можно импортировать экземпляры <xref:System.ServiceModel.Description.ServiceEndpoint>, экземпляры <xref:System.ServiceModel.Description.ContractDescription> и экземпляры <xref:System.ServiceModel.Channels.Binding> из документов WSDL, используя для этого тип `WsdlImporter`.  
  
 В экспортируемые [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] документы WSDL импортируются все используемые определения схемы XML из внешних документов схем XML. Для каждого целевого пространства имен, используемого в типах данных в службе, экспортируется отдельный документ схемы XML. Аналогично, для каждого целевого пространства имен, используемого в контрактах служб, экспортируется отдельный документ WSDL.  
  
### <a name="servicedescription"></a>ServiceDescription  
 Экземпляр <xref:System.ServiceModel.Description.ServiceDescription> сопоставляется с элементом `wsdl:service`. Экземпляр <xref:System.ServiceModel.Description.ServiceDescription> содержит коллекцию экземпляров <xref:System.ServiceModel.Description.ServiceEndpoint>, каждый из которых сопоставляется с отдельным элементом `wsdl:port`.  
  
|Свойства|Сопоставление с WSDL|  
|----------------|------------------|  
|`Name`|`wsdl:service` /@name Значение для службы.|  
|`Namespace`|Целевое пространство имен (targetNamespace) для определения `wsdl:service` для службы.|  
|`Endpoints`|Определения `wsdl:port` для службы.|  
  
### <a name="serviceendpoint"></a>ServiceEndpoint  
 Экземпляр <xref:System.ServiceModel.Description.ServiceEndpoint> сопоставляется с элементом `wsdl:port`. Экземпляр <xref:System.ServiceModel.Description.ServiceEndpoint> содержит адрес, привязку и контракт.  
  
 Поведения конечной точки, реализующие интерфейс <xref:System.ServiceModel.Description.IWsdlExportExtension>, могут изменять элемент `wsdl:port` для конечной точки, к которой они прикреплены.  
  
|Свойства|Сопоставление с WSDL|  
|----------------|------------------|  
|`Name`|`wsdl:port` /@name Значение для конечной точки и `wsdl:binding` /@name значение для привязки конечной точки.|  
|`Address`|Адрес для определения `wsdl:port` для конечной точки.<br /><br /> Формат адреса определяется транспортом для конечной точки. Например, для поддерживаемых [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] транспортов это может быть адрес SOAP или ссылка на конечную точку.|  
|`Binding`|Определение `wsdl:binding` для конечной точки.<br /><br /> В отличие от определений `wsdl:binding`, привязки в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не связаны с каким-либо одним контрактом.|  
|`Contract`|Определение `wsdl:portType` для конечной точки.|  
|`Behaviors`|Поведения конечной точки, реализующие интерфейс <xref:System.ServiceModel.Description.IWsdlExportExtension>, могут изменять элемент `wsdl:port` для конечной точки.|  
  
### <a name="bindings"></a>Привязки  
 Экземпляр привязки `ServiceEndpoint` сопоставляется с определением `wsdl:binding`. В отличие от определений `wsdl:binding`, которые должны быть связаны с конкретным определением `wsdl:portType`, привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не зависимы от какого-либо контракта.  
  
 Привязка состоит из коллекции элементов привязки. Каждый элемент описывает некоторый аспект взаимодействия конечной точки с клиентами. Кроме того, каждая привязка имеет свойство <xref:System.ServiceModel.Channels.MessageVersion>, которое указывает версию конверта (<xref:System.ServiceModel.EnvelopeVersion>) и версию адресации (<xref:System.ServiceModel.Channels.AddressingVersion>) для конечной точки.  
  
|Свойства|Сопоставление с WSDL|  
|----------------|------------------|  
|`Name`|Используется в имени по умолчанию конечной точки, которое состоит из имени привязки и имени контракта, разделенных символом подчеркивания.|  
|`Namespace`|`targetNamespace` для определения `wsdl:binding`.<br /><br /> При импорте, если политика прикреплена к порту WSDL, импортируемое пространство имен привязки сопоставляется с `targetNamespace` для определения `wsdl:port`.|  
|`BindingElementCollection`, возвращаемое методом `CreateBindingElements`()|Различные зависящие от домена расширения определения `wsdl:binding`, обычно утверждения политики.|  
|`MessageVersion`|`EnvelopeVersion` и `AddressingVersion` для конечной точки.<br /><br /> Если задано свойство `MessageVersion.None`, привязка WSDL не содержит привязки SOAP, а порт WSDL не содержит данных о WS-Addressing. Этот вариант обычно используется для конечных точек POX (передающих сообщения в формате "plain old XML").|  
  
#### <a name="bindingelements"></a>BindingElements  
 Элементы привязки для привязки конечной точки сопоставляются с различными расширениями WSDL в элементе `wsdl:binding`, такими как утверждения политики.  
  
 Элемент <xref:System.ServiceModel.Channels.TransportBindingElement> привязки определяет универсальный код ресурса (URI) для привязки SOAP.  
  
#### <a name="addressingversion"></a>AddressingVersion  
 Свойство `AddressingVersion` привязки сопоставляется с версией адресации, используемой в элементе `wsd:port`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает адреса протоколов SOAP 1.1 и SOAP 1.2 и конечные точки WS-Addressing 08/2004 и WS-Addressing 1.0.  
  
#### <a name="envelopeversion"></a>EnvelopeVersion  
 Свойство `EnvelopeVersion` привязки сопоставляется с версией адресации протокола SOAP, используемой в элементе `wsdl:binding`. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает привязки протоколов SOAP 1.1 и SOAP 1.2.  
  
### <a name="contracts"></a>Контракты  
 Экземпляр <xref:System.ServiceModel.Description.ContractDescription> для экземпляра `ServiceEndpoint` сопоставляется с элементом `wsdl:portType`. В экземпляре `ContractDescription` описываются все операции для данного контракта.  
  
|Свойства|Сопоставление с WSDL|  
|----------------|------------------|  
|`Name`|`wsdl:portType` /@name Значение для контракта.|  
|`Namespace`|Целевое пространство имен (targetNamespace) для определения `wsdl:portType`.|  
|`SessionMode`|`wsdl:portType` /@msc:usingSession Значение для контракта. Этот атрибут является расширением [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для WSDL 1.1.|  
|`Operations`|Определения `wsdl:operation` для контракта.|  
  
### <a name="operations"></a>Операции  
 <xref:System.ServiceModel.Description.OperationDescription> Экземпляр сопоставляется с `wsdl:portType` / `wsdl:operation`. Экземпляр `OperationDescription` содержит коллекцию экземпляров `MessageDescription`, которые описывают сообщения для операции.  
  
 Два поведения операции играют большую роль в том, как `OperationDescription` сопоставляется с документом WSDL: `DataContractSerializerOperationBehavior` и `XmlSerializerOperationBehavior`.  
  
|Свойства|Сопоставление с WSDL|  
|----------------|------------------|  
|`Name`|`wsdl:portType` / `wsdl:operation` /@name Значение для операции.|  
|`ProtectionLevel`|Утверждения защиты в политике безопасности, прикрепленной к сообщениям `wsdl:binding/wsdl:operation` для этой операции.|  
|`IsInitiating`|`wsdl:portType` / `wsdl:operation` /@msc:isInitiating Значение для операции. Этот атрибут является расширением [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для WSDL 1.1.|  
|`IsTerminating`|`wsdl:portType` / `wsdl:operation` /@msc:isTerminating Значение для операции. Этот атрибут является расширением [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] для WSDL 1.1.|  
|`Messages`|`wsdl:portType` / `wsdl:operation` / `wsdl:input` И `wsdl:portType` / `wsdl:operation` / `wsdl:output` сообщения для операции.|  
|`Faults`|`wsdl:portType` / `wsdl:operation` / `wsdl:fault` Определения для операции.|  
|`Behaviors`|Поведения `DataContractSerializerOperationBehavior` и `XmlSerializerOperationBehavior` отвечают за привязку операции и сообщения операции.|  
  
#### <a name="the-datacontractserializeroperationbehavior"></a>DataContractSerializerOperationBehavior  
 Поведение `DataContractSerializerOperationBehavior` для операции представляет собой реализацию интерфейса `IWsdlExportExtension`, которая экспортирует сообщения и привязку WSDL для данной операции. Типы схемы XML экспортируются с помощью `XsdDataContractExporter`. Поведение `DataContractSerializerOperationBehavior` также определяет назначение, стиль, а также экспортер и импортер схемы, используемые для данной операции.  
  
|Свойства|Сопоставление с WSDL|  
|----------------|------------------|  
|`DataContractFormatAttribute`|`Style` Свойство для этого атрибута сопоставляется `wsdl:binding` / `wsdl:operation` / `soap:operation` /@style значение для операции.<br /><br /> `DataContractSerializerOperationBehavior` поддерживает только литеральное использование типов схемы в WSDL.|  
  
#### <a name="the-xmlserializeroperationbehavior"></a>XmlSerializerOperationBehavior  
 Поведение `XmlSerializerOperationBehavior` для операции представляет собой реализацию интерфейса `IWsdlExportExtension`, которая экспортирует сообщения и привязку WSDL для данной операции. Типы схемы XML экспортируются с помощью `XmlSchemaExporter`. Поведение `XmlSerializerOperationBehavior` также определяет назначение, стиль, а также экспортер и импортер схемы, используемые для данной операции.  
  
|Свойства|Сопоставление с WSDL|  
|----------------|------------------|  
|`XmlSerializerFormatAttribute`|`Style` Свойство для этого атрибута сопоставляется `wsdl:binding` / `wsdl:operation` / `soap:operation` /@style значение для операции.<br /><br /> `Use` Свойство для этого атрибута сопоставляется `wsdl:binding` / `wsdl:operation` / `soap:operation`/ */@use значения для всех сообщений в операции.|  
  
### <a name="messages"></a>Сообщения  
 Объект `MessageDescription` экземпляр сопоставляется с `wsdl:message` , на который ссылается `wsdl:portType` / `wsdl:operation` / `wsdl:input` или `wsdl:portType` / `wsdl:operation` / `wsdl:output`сообщения в операции. Экземпляр `MessageDescription` имеет тело и заголовки.  
  
|Свойства|Сопоставление с WSDL|  
|----------------|------------------|  
|`Action`|Действие SOAP или WS-Addressing для сообщения.<br /><br /> Обратите внимание, что операции, в которых используется строка действия "*", не отражаются в документе WSDL.|  
|`Direction`|`MessageDirection.Input` сопоставляется с `wsdl:input`.<br /><br /> `MessageDirection.Output` сопоставляется с `wsdl:output`.|  
|`ProtectionLevel`|Утверждения защиты в политике безопасности, прикрепленной к определению `wsdl:message` для этого сообщения.|  
|`Body`|Текст сообщения для сообщения.|  
|`Headers`|Заголовки для сообщения.|  
|`ContractDescription.Name`, `OperationContract.Name`|При экспорте используются для формирования `wsdl:message` /@name значение.|  
  
#### <a name="message-body"></a>Текст сообщения  
 Объект `MessageBodyDescription` экземпляр сопоставляется с `wsdl:message` / `wsdl:part` определения для текста сообщения. Тело сообщения может быть заключено в оболочку или передаваться в режиме "bare".  
  
|Свойства|Сопоставление с WSDL|  
|----------------|------------------|  
|`WrapperName`|Если стиль-не RPC, а затем `WrapperName` сопоставляется с именем элемента ссылается `wsdl:message` / `wsdl:part` с @name значение «параметры».|  
|`WrapperNamespace`|Если стиль-не RPC, а затем `WrapperNamespace` сопоставляется с пространством имен элемента для `wsdl:message` / `wsdl:part` с @name значение «параметры».|  
|`Parts`|Части сообщения для данного тела сообщения.|  
|`ReturnValue`|Дочерний элемент элемента программы-оболочки, если имеется элемент-оболочка (стиль упакованным документом или стиль RPC), в противном случае — первый `wsdl:message` / `wsdl:part` в сообщении.|  
  
#### <a name="message-parts"></a>Части сообщения  
 Объект `MessagePartDescription` экземпляр сопоставляется с `wsdl:message` / `wsdl:part` и тип схемы XML, или элемент, который указывает часть сообщения.  
  
|Свойства|Сопоставление с WSDL|  
|----------------|------------------|  
|`Name`|`wsd:message` / `wsdl:part` /@name Значение для части сообщения и имя элемента, который указывает часть сообщения.|  
|`Namespace`|Пространство имен элемента, на который указывает часть сообщения.|  
|`Index`|Индекс `wsdl:message` / `wsdl:part` для сообщения.|  
|`ProtectionLevel`|Утверждения защиты в политике безопасности, прикрепленной к определению `wsdl:message` для этой части сообщения. Политика параметризована для указания на конкретную часть сообщения.|  
|`MessageType`|Тип схемы XML элемента, на который указывает часть сообщения.|  
  
#### <a name="message-headers"></a>Заголовки сообщений  
 Экземпляр `MessageHeaderDescription` представляет собой часть сообщения, которая также сопоставляется с привязкой `soap:header` для части сообщения.  
  
### <a name="faults"></a>Ошибки  
 Объект `FaultDescription` экземпляр сопоставляется с `wsdl:portType` / `wsdl:operation` / `wsdl:fault` определения и связанный с ним `wsdl:message` определения. Элемент `wsdl:message` добавляется в то же целевое пространство имен, что и связанный с ним тип порта WSDL. Элемент `wsdl:message` имеет одну часть сообщения с именем "detail", которая указывает на элемент схемы XML, соответствующий значению свойства `DefaultType` для экземпляра `FaultDescription`.  
  
|Свойства|Сопоставление с WSDL|  
|----------------|------------------|  
|`Name`|`wsdl:portType` / `wsdl:operation` / `wsdl:fault` /@name Значение для ошибки.|  
|`Namespace`|Пространство имен элемента схемы XML, на которое указывает часть "detail" сообщения ошибки.|  
|`Action`|Действие SOAP или WS-Addressing для ошибки.|  
|`ProtectionLevel`|Утверждения защиты в политике безопасности, прикрепленной к определению `wsdl:message` для этой ошибки.|  
|`DetailType`|Тип схемы XML элемента, на который указывает часть "detail" сообщения.|  
|`Name, ContractDescription.Name, OperationDescription.Name,`|Используются для получения `wsdl:message` /@name значение для сообщения об ошибке.|  
  
## <a name="see-also"></a>См. также  
 <xref:System.ServiceModel.Description>
