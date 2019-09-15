---
title: Взаимодействие с веб-службами ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 59ee6412cde152588e8007fe530cc8e5708410e5
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991536"
---
# <a name="interoperability-with-aspnet-web-services"></a>Взаимодействие с веб-службами ASP.NET
Взаимодействие между веб-службами ASP.NET и веб-службами Windows Communication Foundation (WCF) можно обеспечить, убедившись, что службы, реализованные с помощью обеих технологий, соответствуют спецификации WS-I Basic Profile 1,1. Веб-службы ASP.NET, которые соответствуют стандартному профилю WS-I 1,1, взаимодействуют с клиентами WCF с помощью предоставляемой системой <xref:System.ServiceModel.BasicHttpBinding>привязки WCF.  
  
 Используйте параметр ASP.NET 2,0, чтобы добавить <xref:System.Web.Services.WebService> атрибуты <xref:System.Web.Services.WebMethodAttribute> и в интерфейс, а не в класс, а также написать класс для реализации интерфейса, как показано в следующем образце кода.  
  
```csharp
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
  
 XML-код, в который тип сериализуется сериализатором <xref:System.Xml.Serialization.XmlSerializer>, по умолчанию семантически идентичен XML-коду, в который тип сериализуется сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML задано явным образом. При определении типа данных для использования со службами ASP. Нетвеб в качестве ожидаемого внедрения WCF выполните следующие действия.  
  
- Задавайте тип с использованием классов .NET Framework, а не схемы XML.  
  
- Добавляйте в класс только атрибуты <xref:System.SerializableAttribute> и <xref:System.Xml.Serialization.XmlRootAttribute>, используя последний для явного задания пространства имен для типа. Не добавляйте дополнительные атрибуты из пространства имен <xref:System.Xml.Serialization> для задания способа преобразования класса .NET Framework в XML.  
  
- Используя этот подход, вы впоследствии сможете превратить классы .NET в контракты данных, добавив атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, без значительного изменения XML-кода, в который классы сериализуются для передачи. Типы, используемые в сообщениях ASP.NET веб-служб, могут обрабатываться как контракты данных приложениями WCF, что обеспечивает, помимо прочих преимуществ, лучшую производительность приложений WCF.  
  
 Избегайте использования параметров проверки подлинности, предусмотренных в службах IIS. Клиенты WCF не поддерживают их. Если служба должна быть защищена, используйте параметры, предоставляемые WCF, поскольку эти параметры являются надежными и основаны на стандартных протоколах.  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a>Влияние загрузки модуля ServiceModel HttpModule на производительность  
 В платформе .NET Framework 3.0 модуль WCF `HttpModule` устанавливался в корневой файл Web.config таким образом, что любое приложение ASP.NET поддерживало WCF. Это может влиять на производительность, поэтому можно удалить `ServiceModel` из файла Web.config, как показано в следующем примере.  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a>См. также

- [Практическое руководство. Настройка службы WCF для взаимодействия с клиентами веб-службы ASP.NET](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
