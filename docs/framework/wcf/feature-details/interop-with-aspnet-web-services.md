---
title: "Взаимодействие с веб-службами ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Взаимодействие с веб-службами ASP.NET
Взаимодействие между веб\-службами [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] и веб\-службами [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] возможно, если обеспечить, чтобы службы, реализованные с помощью обеих технологий, соответствовали спецификации WS\-I Basic Profile 1.1.Веб\-службы [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], соответствующие спецификации WS\-I Basic Profile 1.1, могут взаимодействовать с клиентами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью предоставляемой системой привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] — <xref:System.ServiceModel.BasicHttpBinding>.  
  
 Используйте имеющуюся в [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] возможность добавления атрибутов <xref:System.Web.Services.WebService> и <xref:System.Web.Services.WebMethodAttribute> в интерфейс, а не в класс, и создания класса для реализации интерфейса, как показано в следующем примере кода.  
  
```  
[WebService]  
public interface IEcho  
{  
    [WebMethod]  
    string Echo(string input);  
}  
  
public class Service : IEcho  
{  
  
   public string Echo(string input)  
   {  
        return input;  
    }  
}  
```  
  
 Использование этого варианта предпочтительно, так как интерфейс с атрибутом <xref:System.Web.Services.WebService> составляет контракт для операций, выполняемых службой, доступный для повторного использования в различных классах, которые могут реализовывать этот же контракт другими способами.  
  
 Избегайте использования атрибута <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> для маршрутизации сообщений методами по полному имени элемента текста сообщения протокола SOAP, а не по заголовку HTTP `SOAPAction`.[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует заголовок HTTP `SOAPAction` для маршрутизации сообщений.  
  
 XML\-код, в который тип сериализуется сериализатором <xref:System.Xml.Serialization.XmlSerializer>, по умолчанию семантически идентичен XML\-коду, в который тип сериализуется сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML задано явным образом.При задании типа данных для использования в веб\-службах [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], если в будущем планируется переход на [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], поступайте следующим образом.  
  
-   Задавайте тип с использованием классов .NET Framework, а не схемы XML.  
  
-   Добавляйте в класс только атрибуты <xref:System.SerializableAttribute> и <xref:System.Xml.Serialization.XmlRootAttribute>, используя последний для явного задания пространства имен для типа.Не добавляйте дополнительные атрибуты из пространства имен <xref:System.Xml.Serialization> для задания способа преобразования класса .NET Framework в XML.  
  
-   Используя этот подход, вы впоследствии сможете превратить классы .NET в контракты данных, добавив атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, без значительного изменения XML\-кода, в который классы сериализуются для передачи.Типы, используемые в сообщениях веб\-службами [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)], могут обрабатываться приложениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] как контракты данных, что, помимо прочих преимуществ, повышает производительность приложений [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
 Избегайте использования параметров аутентификации, предусмотренных в службах IIS.Клиенты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживают их.Если службу необходимо защитить, используйте параметры, предусмотренные в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]: они надежны и основаны на стандартных протоколах.  
  
## Влияние загрузки модуля ServiceModel HttpModule на производительность  
 В платформе .NET Framework 3.0 модуль WCF `HttpModule` устанавливался в корневой файл Web.config таким образом, что любое приложение ASP.NET поддерживало WCF.Это может влиять на производительность, поэтому можно удалить `ServiceModel` из файла Web.config, как показано в следующем примере.  
  
```  
<httpModules>  
    <remove name=”ServiceModel” />  
<httpModules/>  
  
```  
  
## См. также  
 [Как настраивать службы WCF для взаимодействия с клиентами веб\-службы ASP.NET](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)