---
title: "Атрибуты ServiceModel и справочная информация ServiceDescription | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 4ab86b17-eab9-4846-a881-0099f9a7cc64
caps.latest.revision: 13
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 13
---
# Атрибуты ServiceModel и справочная информация ServiceDescription
*Дерево описания* — это иерархия типов \(начиная с класса <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=fullName>\), которые вместе описывают каждый аспект службы.[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] использует дерево описания для построения допустимой среды выполнения службы, для публикации схем на языке WSDL, схем XSD и утверждений политики \(метаданные\) о службе, которые клиенты могут использовать для подключения и использования службы, а также для создания различных файлов конфигурации представления и кода на основе значений из дерева описания.  
  
 В этом разделе описывается получение свойств, относящихся к контракту, из контракта службы, а также их реализация и добавление в дерево описания.В некоторых случаях значения атрибутов преобразуются в свойства поведения, и поведение затем вставляется в дерево описания.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] порядке преобразования значений дерева описания в метаданные см. в разделе [ServiceDescription и справочная информация о WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## Сопоставление операций дереву описания  
 В приложениях [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] контракты службы моделируются интерфейсами \(или классами\), использующими атрибуты для отметки интерфейса или класса и его методы в качестве групп операций.При открытии класса <xref:System.ServiceModel.ServiceHost> все контракты и реализации службы отражаются и объединяются с информацией о конфигурации в дереве описания.  
  
 Существуют два типа моделей операции: модель *параметров* и модель *контракта сообщений*.В модели параметров используются управляемые методы, не имеющие типа параметра или возвращаемого значения, помеченного классом <xref:System.ServiceModel.MessageContractAttribute?displayProperty=fullName>.В этой модели разработчики управляют сериализацией параметров и возвращаемых значений, а [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] генерирует значения, используемые для заполнения дерева описания службы и ее контракта.  
  
 Привязки, указанные в файлах конфигурации, загружаются непосредственно в свойство <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A?displayProperty=fullName>.  
  
|Свойство ServiceBehaviorAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-----------------------------------------|  
|Name|<xref:System.ServiceModel.Description.ServiceDescription.Name%2A>|  
|Namespace|<xref:System.ServiceModel.Description.ServiceDescription.Namespace%2A>|  
|ConfigurationName|<xref:System.ServiceModel.Description.ServiceDescription.ConfigurationName%2A>|  
|IgnoreExtensionDataObject|Задает свойство <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.IgnoreExtensionDataObject%2A> для всех операций.|  
|MaxItemsInObjectGraph|Задает свойство <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> для всех операций.|  
  
|Свойство ServiceContractAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-----------------------------------------|  
|CallbackContract|<xref:System.ServiceModel.Description.ContractDescription.CallbackContractType%2A>, <xref:System.ServiceModel.Description.MessageDescription>, добавленные к <xref:System.ServiceModel.Description.OperationDescription.Messages%2A> всех операций.|  
|ConfigurationName|<xref:System.ServiceModel.Description.ContractDescription.ConfigurationName%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A> и, возможно, дочерние уровни защиты.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] об иерархии уровней защиты см. в разделе [Основные сведения об уровне защиты](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|SessionMode|<xref:System.ServiceModel.Description.ContractDescription.SessionMode%2A>|  
  
|Значение ServiceKnownTypesAttribute|Изменяемое значение дерева описания|  
|-----------------------------------------|-----------------------------------------|  
|MethodName|<xref:System.ServiceModel.Description.OperationDescription.KnownTypes%2A>|  
  
|Значение OperationContractAttribute|Изменяемое значение дерева описания|  
|-----------------------------------------|-----------------------------------------|  
|Action|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> для исходящего или входящего сообщения, в зависимости от контракта\/контракта обратного вызова.|  
|AsyncPattern|Если имеет значение "True", <xref:System.ServiceModel.Description.OperationDescription.BeginMethod%2A> и <xref:System.ServiceModel.Description.OperationDescription.EndMethod%2A>|  
|IsOneWay|Сопоставляется одному описанию <xref:System.ServiceModel.Description.MessageDescription> в <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>|  
|IsInitiating|<xref:System.ServiceModel.Description.OperationDescription.IsInitiating%2A>|  
|IsTerminating|<xref:System.ServiceModel.Description.OperationDescription.IsTerminating%2A>|  
|Имя|<xref:System.ServiceModel.Description.OperationDescription.Name%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A> и, возможно, дочерние уровни защиты.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] об иерархии уровней защиты см. в разделе [Основные сведения об уровне защиты](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|ReplyAction|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> для исходящего или входящего сообщения, в зависимости от контракта\/контракта обратного вызова.|  
  
|Значение FaultContractAttribute|Изменяемое значение дерева описания|  
|-------------------------------------|-----------------------------------------|  
|Action|<xref:System.ServiceModel.Description.FaultDescription.Action%2A>, в зависимости от контракта\/контракта обратного вызова.|  
|DetailType|<xref:System.ServiceModel.Description.FaultDescription.DetailType%2A>|  
|Name|<xref:System.ServiceModel.Description.FaultDescription.Name%2A>|  
|Namespace|<xref:System.ServiceModel.Description.FaultDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.FaultDescription.ProtectionLevel%2A>|  
  
|Значение DataContractFormatAttribute|Изменяемое значение дерева описания|  
|------------------------------------------|-----------------------------------------|  
|Use|Задается значение <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> в <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> для операции.|  
  
|Значение XmlSerializerFormatAttribute|Изменяемое значение дерева описания|  
|-------------------------------------------|-----------------------------------------|  
|Style|Это свойство <xref:System.ServiceModel.XmlSerializerFormatAttribute> задается в <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> для операции.|  
|Use|<xref:System.ServiceModel.XmlSerializerFormatAttribute> задается в <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> для операции.|  
  
|Значение TransactionFlowAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-----------------------------------------|  
|TransactionFlowOption|<xref:System.ServiceModel.TransactionFlowAttribute> добавляется в виде расширения функциональности в свойство <xref:System.ServiceModel.Description.OperationDescription.Behaviors%2A>.|  
  
|Значение MessageContractAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-----------------------------------------|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessageDescription.ProtectionLevel%2A>|  
|WrapperName|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperName%2A>|  
|WrapperNamespace|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperNamespace%2A>|  
  
|Значение MessageHeaderAttribute|Изменяемое значение дерева описания|  
|-------------------------------------|-----------------------------------------|  
|Actor|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Namespace|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
  
|Значение MessageBodyMemberAttribute|Изменяемое значение дерева описания|  
|-----------------------------------------|-----------------------------------------|  
|Name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Namespace|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Order|<xref:System.ServiceModel.Description.MessagePartDescription.Index%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
|Значение MessageHeaderArrayAttribute|Изменяемое значение дерева описания|  
|------------------------------------------|-----------------------------------------|  
|Actor|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>|  
|Name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
|Пространство имен|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>|  
  
|Значение MessagePropertyAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-----------------------------------------|  
|Name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
  
|Значение MessageParameterAttribute|Изменяемое значение дерева описания|  
|----------------------------------------|-----------------------------------------|  
|Name|<xref:System.ServiceModel.Description.MessagePartDescription.name%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
 [!INCLUDE[crabout](../../../../includes/crabout-md.md)] порядке преобразования значений дерева описания в метаданные см. в разделе [ServiceDescription и справочная информация о WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## См. также  
 [ServiceDescription и справочная информация о WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md)