---
title: Атрибуты ServiceModel и справочная информация ServiceDescription
ms.date: 03/30/2017
ms.assetid: 4ab86b17-eab9-4846-a881-0099f9a7cc64
ms.openlocfilehash: 022731d7d6e60d36c5f4a595edc90aaff0586a79
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59195349"
---
# <a name="servicemodel-attributes-and-servicedescription-reference"></a>Атрибуты ServiceModel и справочная информация ServiceDescription
*Дерево описания* — это иерархия типов (начиная с <xref:System.ServiceModel.Description.ServiceDescription?displayProperty=nameWithType> класс), которые вместе описывают каждый аспект службы. Windows Communication Foundation (WCF) использует дерево описания для построения допустимой среды выполнения службы, чтобы опубликовать Web Services Description Language (WSDL), язык определения схемы XML (XSD) и утверждений политики (метаданные) о службе, которые клиенты могут использовать для подключиться и использовать службу и для создания различных кода и конфигурации файла представлений значений дерева описания.  
  
 В этом разделе описывается получение свойств, относящихся к контракту, из контракта службы, а также их реализация и добавление в дерево описания. В некоторых случаях значения атрибутов преобразуются в свойства поведения, затем поведение вставляется в дерево описания. Дополнительные сведения о том, как преобразования значений дерева описания в метаданные, см. в разделе [ServiceDescription и справочная WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## <a name="mapping-operations-to-the-description-tree"></a>Сопоставление операций дереву описания  
 В приложениях WCF контракты службы моделируются интерфейсами (или классы), использующими атрибуты для отметки интерфейса или класса и его методов, как группа operations. При открытии класса <xref:System.ServiceModel.ServiceHost> все контракты и реализации службы отражаются и объединяются с информацией о конфигурации в дереве описания.  
  
 Существует два типа моделей операции: *параметр* модели и *контракт сообщения* модели. В модели параметров используются управляемые методы, не имеющие типа параметра или возвращаемого значения, помеченного классом <xref:System.ServiceModel.MessageContractAttribute?displayProperty=nameWithType>. В этой модели разработчики управляют сериализацией параметров и возвращаемых значений, но WCF создает значения, которые используются для заполнения дерева описания службы и ее контракта.  
  
 Привязки, указанные в файлах конфигурации, загружаются непосредственно в свойство <xref:System.ServiceModel.Description.ServiceEndpoint.Binding%2A?displayProperty=nameWithType>.  
  
|Свойство ServiceBehaviorAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-------------------------------------|  
|name|<xref:System.ServiceModel.Description.ServiceDescription.Name%2A>|  
|Пространство имен|<xref:System.ServiceModel.Description.ServiceDescription.Namespace%2A>|  
|ConfigurationName|<xref:System.ServiceModel.Description.ServiceDescription.ConfigurationName%2A>|  
|IgnoreExtensionDataObject|Задает свойство <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.IgnoreExtensionDataObject%2A> для всех операций.|  
|MaxItemsInObjectGraph|Задает свойство <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior.MaxItemsInObjectGraph%2A> для всех операций.|  
  
|Свойство ServiceContractAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-------------------------------------|  
|CallbackContract|<xref:System.ServiceModel.Description.ContractDescription.CallbackContractType%2A>, <xref:System.ServiceModel.Description.MessageDescription> добавлен ко всем операциям <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>.|  
|ConfigurationName|<xref:System.ServiceModel.Description.ContractDescription.ConfigurationName%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.ContractDescription.ProtectionLevel%2A> и возможно дочерние уровни защиты. Дополнительные сведения об иерархии уровней защиты см. в разделе [уровень защиты понимание](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|SessionMode|<xref:System.ServiceModel.Description.ContractDescription.SessionMode%2A>|  
  
|Значение ServiceKnownTypesAttribute|Изменяемое значение дерева описания|  
|--------------------------------------|-------------------------------------|  
|MethodName|<xref:System.ServiceModel.Description.OperationDescription.KnownTypes%2A>|  
  
|Значение OperationContractAttribute|Изменяемое значение дерева описания|  
|--------------------------------------|-------------------------------------|  
|Действие|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> для исходящего или входящего сообщения, в зависимости от контракта/контракта обратного вызова.|  
|AsyncPattern|Если значение равно true, <xref:System.ServiceModel.Description.OperationDescription.BeginMethod%2A> и <xref:System.ServiceModel.Description.OperationDescription.EndMethod%2A>|  
|IsOneWay|Сопоставляется одному <xref:System.ServiceModel.Description.MessageDescription> в <xref:System.ServiceModel.Description.OperationDescription.Messages%2A>|  
|IsInitiating|<xref:System.ServiceModel.Description.OperationDescription.IsInitiating%2A>|  
|IsTerminating|<xref:System.ServiceModel.Description.OperationDescription.IsTerminating%2A>|  
|name|<xref:System.ServiceModel.Description.OperationDescription.Name%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.OperationDescription.ProtectionLevel%2A> и возможно дочерние уровни защиты. Дополнительные сведения об иерархии уровней защиты см. в разделе [уровень защиты понимание](../../../../docs/framework/wcf/understanding-protection-level.md).|  
|ReplyAction|<xref:System.ServiceModel.Description.MessageDescription.Action%2A> для исходящего или входящего сообщения, в зависимости от контракта/контракта обратного вызова.|  
  
|Значение FaultContractAttribute|Изменяемое значение дерева описания|  
|----------------------------------|-------------------------------------|  
|Действие|<xref:System.ServiceModel.Description.FaultDescription.Action%2A> в зависимости от контракта/контракта обратного вызова.|  
|DetailType|<xref:System.ServiceModel.Description.FaultDescription.DetailType%2A>|  
|name|<xref:System.ServiceModel.Description.FaultDescription.Name%2A>|  
|Пространство имен|<xref:System.ServiceModel.Description.FaultDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.FaultDescription.ProtectionLevel%2A>|  
  
|Значение DataContractFormatAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-------------------------------------|  
|Использовать|Задается значение <xref:System.ServiceModel.DataContractFormatAttribute.Style%2A> в <xref:System.ServiceModel.Description.DataContractSerializerOperationBehavior> для операции.|  
  
|Значение XmlSerializerFormatAttribute|Изменяемое значение дерева описания|  
|----------------------------------------|-------------------------------------|  
|Стиль|Это свойство <xref:System.ServiceModel.XmlSerializerFormatAttribute> задается в <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> для операции.|  
|Использовать|<xref:System.ServiceModel.XmlSerializerFormatAttribute> задается в <xref:System.ServiceModel.Description.XmlSerializerOperationBehavior> для операции.|  
  
|Значение TransactionFlowAttribute|Изменяемое значение дерева описания|  
|------------------------------------|-------------------------------------|  
|TransactionFlowOption|<xref:System.ServiceModel.TransactionFlowAttribute> добавляется в виде расширения функциональности в свойство <xref:System.ServiceModel.Description.OperationDescription.Behaviors%2A>.|  
  
|Значение MessageContractAttribute|Изменяемое значение дерева описания|  
|------------------------------------|-------------------------------------|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessageDescription.ProtectionLevel%2A>|  
|WrapperName|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperName%2A>|  
|WrapperNamespace|<xref:System.ServiceModel.Description.MessageBodyDescription.WrapperNamespace%2A>|  
  
|Значение MessageHeaderAttribute|Изменяемое значение дерева описания|  
|----------------------------------|-------------------------------------|  
|Actor|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Пространство имен|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A> для соответствующего заголовка в <xref:System.ServiceModel.Description.MessageDescription.Headers%2A>|  
  
|Значение MessageBodyMemberAttribute|Изменяемое значение дерева описания|  
|--------------------------------------|-------------------------------------|  
|name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Пространство имен|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|Номер|<xref:System.ServiceModel.Description.MessagePartDescription.Index%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
|Значение MessageHeaderArrayAttribute|Изменяемое значение дерева описания|  
|---------------------------------------|-------------------------------------|  
|Actor|<xref:System.ServiceModel.Description.MessageHeaderDescription.Actor%2A>|  
|MustUnderstand|<xref:System.ServiceModel.Description.MessageHeaderDescription.MustUnderstand%2A>|  
|name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
|Пространство имен|<xref:System.ServiceModel.Description.MessagePartDescription.Namespace%2A>|  
|ProtectionLevel|<xref:System.ServiceModel.Description.MessagePartDescription.ProtectionLevel%2A>|  
|Relay|<xref:System.ServiceModel.Description.MessageHeaderDescription.Relay%2A>|  
  
|Значение MessagePropertyAttribute|Изменяемое значение дерева описания|  
|------------------------------------|-------------------------------------|  
|name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A>|  
  
|Значение MessageParameterAttribute|Изменяемое значение дерева описания|  
|-------------------------------------|-------------------------------------|  
|name|<xref:System.ServiceModel.Description.MessagePartDescription.Name%2A> для соответствующей части в <xref:System.ServiceModel.Description.MessageBodyDescription.Parts%2A>|  
  
 Дополнительные сведения о том, как преобразования значений дерева описания в метаданные, см. в разделе [ServiceDescription и справочная WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md).  
  
## <a name="see-also"></a>См. также

- [ServiceDescription и справочная информация о WSDL](../../../../docs/framework/wcf/feature-details/servicedescription-and-wsdl-reference.md)
