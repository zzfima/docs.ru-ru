---
title: Взаимодействие с веб-службами ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: f2f1a8fd2bf34ff61784f2dcb88c0669585da573
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/12/2019
ms.locfileid: "67026022"
---
# <a name="interoperability-with-aspnet-web-services"></a>Взаимодействие с веб-службами ASP.NET
Можно достичь взаимодействия между веб-служб ASP.NET и Windows Communication Foundation (WCF) веб-служб, гарантируя, что служб, реализуемых используя обе технологии соответствующими требованиям WS-I Basic Profile 1.1 спецификации. Веб-службы ASP.NET, соответствующие спецификации WS-I Basic Profile 1.1, могут взаимодействовать с клиентами WCF с помощью привязки, предоставляемой системой WCF, <xref:System.ServiceModel.BasicHttpBinding>.  
  
 Использование ASP.NET 2.0 возможность добавления <xref:System.Web.Services.WebService> и <xref:System.Web.Services.WebMethodAttribute> атрибуты интерфейса, а не к классу и написания класса для реализации интерфейса, как показано в следующем примере кода.  
  
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
  
 Избегайте использования атрибута <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> для маршрутизации сообщений методами по полному имени элемента текста сообщения протокола SOAP, а не по заголовку HTTP `SOAPAction`. WCF использует `SOAPAction` заголовок HTTP для маршрутизации сообщений.  
  
 XML-код, в который тип сериализуется сериализатором <xref:System.Xml.Serialization.XmlSerializer>, по умолчанию семантически идентичен XML-коду, в который тип сериализуется сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML задано явным образом. При задании типа данных для использования со службами ASP.NETWeb заранее внедрения WCF, сделайте следующее:  
  
- Задавайте тип с использованием классов .NET Framework, а не схемы XML.  
  
- Добавляйте в класс только атрибуты <xref:System.SerializableAttribute> и <xref:System.Xml.Serialization.XmlRootAttribute>, используя последний для явного задания пространства имен для типа. Не добавляйте дополнительные атрибуты из пространства имен <xref:System.Xml.Serialization> для задания способа преобразования класса .NET Framework в XML.  
  
- Используя этот подход, вы впоследствии сможете превратить классы .NET в контракты данных, добавив атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, без значительного изменения XML-кода, в который классы сериализуются для передачи. Типы, используемые в сообщениях веб-службами ASP.NET могут обрабатываться как контракты данных приложений WCF, что, помимо прочих преимуществ, повышения производительности в приложениях WCF.  
  
 Избегайте использования параметров проверки подлинности, предусмотренных в службах IIS. Клиенты WCF не поддерживают их. Если служба должна быть защищена, используйте параметры, предоставляемые WCF, так как эти они надежны и основаны на стандартных протоколах.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Влияние загрузки модуля ServiceModel HttpModule на производительность  
 В платформе .NET Framework 3.0 модуль WCF `HttpModule` устанавливался в корневой файл Web.config таким образом, что любое приложение ASP.NET поддерживало WCF. Это может влиять на производительность, поэтому можно удалить `ServiceModel` из файла Web.config, как показано в следующем примере.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Настройка службы WCF для взаимодействия с клиентами ASP.NET веб-службы](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
