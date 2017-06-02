---
title: "Планирование перехода на платформу Windows Communication Foundation: упрощение будущей интеграции | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Планирование перехода на платформу Windows Communication Foundation: упрощение будущей интеграции
Для тех, кто в настоящее время использует ASP.NET и планирует в будущем использовать [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], этот раздел содержит рекомендации, как обеспечить как правильную работу веб\-служб ASP.NET с приложениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Основные рекомендации  
 Используйте для создания новых служб ASP.NET 2.0.Это обеспечит доступ к усовершенствованиям, появившимся в новой версии.В то же время это даст возможность использовать компоненты ASP.NET 2.0 вместе с компонентами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в одном и том же приложении.  
  
## Протоколы  
 Используйте новую функцию ASP.NET 2.0 для проверки соответствия спецификации WS\-I Basic Profile 1.1:  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
  
```  
  
 Веб\-службы ASP.NET, соответствующие спецификации WS\-I Basic Profile 1.1, будут способны взаимодействовать с клиентами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью предопределенной привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] — <xref:System.ServiceModel.BasicHttpBinding>.  
  
## Разработка служб  
 Избегайте использования <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute>атрибута для маршрутизации сообщений методами, основанными на полном имени элемента текста сообщения протокола SOAP, а не по HTTP\-заголовку SOAPAction.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует HTTP\-заголовок SOAPAction для маршрутизации сообщений.  
  
## Представление данных  
 XML\-код, в который тип сериализуется сериализатором <xref:System.Xml.Serialization.XmlSerializer>, по умолчанию семантически идентичен XML\-коду, в который тип сериализуется сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML задано явным образом.При задании типа данных для использования в веб\-службах ASP.NET, если в будущем планируется переход на [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], поступайте следующим образом.  
  
1.  Задавайте тип с использованием классов .NET Framework, а не схемы XML.  
  
2.  Добавляйте в класс только атрибуты <xref:System.SerializableAttribute> и <xref:System.Xml.Serialization.XmlRootAttribute>, используя последний для явного задания пространства имен для типа.Не добавляйте дополнительные атрибуты из пространства имен <xref:System.Xml.Serialization> для задания способа преобразования класса .NET Framework в XML.  
  
 Используя этот подход, вы впоследствии сможете превратить классы .NET в контракты данных, добавив атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, без значительного изменения XML\-кода, в который классы сериализуются для передачи.Типы, используемые в сообщениях веб\-службами ASP.NET, смогут обрабатываться приложениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] как контракты данных, что, помимо прочих преимуществ, повышает производительность [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
## Безопасность  
 Избегайте использования параметров аутентификации, предусмотренных в службах IIS.Клиенты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживают их.Если службу необходимо защитить, используйте параметры, предусмотренные в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]: они обеспечивают больше возможностей и основаны на стандартных протоколах.  
  
## См. также  
 [Планирование перехода на платформу Windows Communication Foundation: упрощение будущей миграции](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)