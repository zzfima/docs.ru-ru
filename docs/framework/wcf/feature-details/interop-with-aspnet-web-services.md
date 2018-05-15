---
title: Взаимодействие с веб-службами ASP.NET
ms.date: 03/30/2017
ms.assetid: 622422f8-6651-442f-b8be-e654a4aabcac
ms.openlocfilehash: 8a0737a36989dd8bc6f5d5670555c7b2218798bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="interoperability-with-aspnet-web-services"></a><span data-ttu-id="2b6d7-102">Взаимодействие с веб-службами ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2b6d7-102">Interoperability with ASP.NET Web Services</span></span>
<span data-ttu-id="2b6d7-103">Взаимодействие между [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] веб-службы и службы Windows Communication Foundation (WCF) веб-службы, может осуществляться за счет того, что службы, реализованные с помощью обеих технологий соответствующими требованиям WS-I Basic Profile 1.1 спецификации.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-103">Interoperability between [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services and Windows Communication Foundation (WCF) Web services can be achieved by ensuring that services implemented using both technologies conform to the WS-I Basic Profile 1.1 specification.</span></span> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="2b6d7-104"> Веб-службы, соответствующие спецификации WS-I Basic Profile 1.1, могут взаимодействовать с клиентами WCF с помощью привязки, предоставляемой системой WCF, <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-104"> Web services that conform to WS-I Basic Profile 1.1 are interoperable with WCF clients by using WCF system-provided binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
 <span data-ttu-id="2b6d7-105">Используйте имеющуюся в [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] возможность добавления атрибутов <xref:System.Web.Services.WebService> и <xref:System.Web.Services.WebMethodAttribute> в интерфейс, а не в класс, и создания класса для реализации интерфейса, как показано в следующем примере кода.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-105">Use [!INCLUDE[vstecasplong](../../../../includes/vstecasplong-md.md)] option of adding the <xref:System.Web.Services.WebService> and <xref:System.Web.Services.WebMethodAttribute> attributes to an interface rather than to a class, and writing a class to implement the interface, as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="2b6d7-106">Использование этого варианта предпочтительно, так как интерфейс с атрибутом <xref:System.Web.Services.WebService> составляет контракт для операций, выполняемых службой, доступный для повторного использования в различных классах, которые могут реализовывать этот же контракт другими способами.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-106">Using this option is preferred, because the interface with the <xref:System.Web.Services.WebService> attribute constitutes a contract for the operations performed by the service that can be reused with various classes that might implement that same contract in different ways.</span></span>  
  
 <span data-ttu-id="2b6d7-107">Избегайте использования атрибута <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> для маршрутизации сообщений методами по полному имени элемента текста сообщения протокола SOAP, а не по заголовку HTTP `SOAPAction`.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-107">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the `SOAPAction` HTTP header.</span></span> <span data-ttu-id="2b6d7-108">WCF использует `SOAPAction` заголовок HTTP для маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-108">WCF uses the `SOAPAction` HTTP header for routing messages.</span></span>  
  
 <span data-ttu-id="2b6d7-109">XML-код, в который тип сериализуется сериализатором <xref:System.Xml.Serialization.XmlSerializer>, по умолчанию семантически идентичен XML-коду, в который тип сериализуется сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML задано явным образом.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-109">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="2b6d7-110">При задании типа данных для использования с [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]веб-службы в будущем планируется переход WCF, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="2b6d7-110">When defining a data type for use with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web services in anticipation of adopting WCF, do the following:</span></span>  
  
-   <span data-ttu-id="2b6d7-111">Задавайте тип с использованием классов .NET Framework, а не схемы XML.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-111">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
-   <span data-ttu-id="2b6d7-112">Добавляйте в класс только атрибуты <xref:System.SerializableAttribute> и <xref:System.Xml.Serialization.XmlRootAttribute>, используя последний для явного задания пространства имен для типа.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-112">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="2b6d7-113">Не добавляйте дополнительные атрибуты из пространства имен <xref:System.Xml.Serialization> для задания способа преобразования класса .NET Framework в XML.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-113">Do not add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
-   <span data-ttu-id="2b6d7-114">Используя этот подход, вы впоследствии сможете превратить классы .NET в контракты данных, добавив атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, без значительного изменения XML-кода, в который классы сериализуются для передачи.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-114">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="2b6d7-115">Типы, используемые в сообщениях [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] веб-служб могут обрабатываться как контракты данных приложений WCF, что, помимо прочих преимуществ, повышения производительности в приложениях WCF.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-115">The types used in messages by [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web services can be processed as data contracts by WCF applications, yielding, among other benefits, better performance in WCF applications.</span></span>  
  
 <span data-ttu-id="2b6d7-116">Избегайте использования параметров проверки подлинности, предусмотренных в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-116">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="2b6d7-117">Клиенты WCF не поддерживает их.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-117">WCF clients do not support them.</span></span> <span data-ttu-id="2b6d7-118">Если служба должна быть защищена, используйте параметры, предоставляемые WCF, так как эти они надежны и основаны на стандартных протоколах.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-118">If a service must be secured, use the options provided by WCF, because these options are robust and are based on standard protocols.</span></span>  
  
## <a name="performance-impact-caused-by-loading-the-servicemodel-httpmodule"></a><span data-ttu-id="2b6d7-119">Влияние загрузки модуля ServiceModel HttpModule на производительность</span><span class="sxs-lookup"><span data-stu-id="2b6d7-119">Performance impact caused by loading the ServiceModel HttpModule</span></span>  
 <span data-ttu-id="2b6d7-120">В платформе .NET Framework 3.0 модуль WCF `HttpModule` устанавливался в корневой файл Web.config таким образом, что любое приложение ASP.NET поддерживало WCF.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-120">In the .NET Framework 3.0, the WCF `HttpModule` was installed in the root Web.config file such that every ASP.NET application was WCF enabled.</span></span> <span data-ttu-id="2b6d7-121">Это может влиять на производительность, поэтому можно удалить `ServiceModel` из файла Web.config, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="2b6d7-121">This might affect performance, so you can remove `ServiceModel` for the Web.config file as shown in the following example.</span></span>  
  
```xml  
<httpModules>  
    <remove name="ServiceModel" />  
<httpModules/>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b6d7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="2b6d7-122">See Also</span></span>  
 [<span data-ttu-id="2b6d7-123">Практическое руководство. Настройка службы WCF для взаимодействия с клиентами веб-службы ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2b6d7-123">How to: Configure WCF Service to Interoperate with ASP.NET Web Service Clients</span></span>](../../../../docs/framework/wcf/feature-details/config-wcf-service-with-aspnet-web-service.md)
