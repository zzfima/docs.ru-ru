---
title: "Планирование перехода на платформу Windows Communication Foundation: упрощение будущей интеграции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3028bba8-6355-4ee0-9ecd-c56e614cb474
caps.latest.revision: "7"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 8f60b2566895acfd7d2b749729fab9c3f5deb20c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-integration"></a><span data-ttu-id="4d659-102">Планирование перехода на платформу Windows Communication Foundation: упрощение будущей интеграции</span><span class="sxs-lookup"><span data-stu-id="4d659-102">Anticipating Adopting the Windows Communication Foundation: Easing Future Integration</span></span>
<span data-ttu-id="4d659-103">Для тех, кто в настоящее время использует ASP.NET и планирует в будущем использовать [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], этот раздел содержит рекомендации, как обеспечить как правильную работу веб-служб ASP.NET с приложениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d659-103">If you use ASP.NET today, and anticipate using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, this topic provides guidance to ensure that new ASP.NET Web services will work well together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="general-recommendations"></a><span data-ttu-id="4d659-104">Основные рекомендации</span><span class="sxs-lookup"><span data-stu-id="4d659-104">General Recommendations</span></span>  
 <span data-ttu-id="4d659-105">Используйте для создания новых служб ASP.NET 2.0.</span><span class="sxs-lookup"><span data-stu-id="4d659-105">Adopt ASP.NET 2.0 for any new services.</span></span> <span data-ttu-id="4d659-106">Это обеспечит доступ к усовершенствованиям, появившимся в новой версии.</span><span class="sxs-lookup"><span data-stu-id="4d659-106">Doing so will provide access to the improvements and enhancements of the new version.</span></span> <span data-ttu-id="4d659-107">В то же время это даст возможность использовать компоненты ASP.NET 2.0 вместе с компонентами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] в одном и том же приложении.</span><span class="sxs-lookup"><span data-stu-id="4d659-107">However, it will also allow for the possibility of using ASP.NET 2.0 components together with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] components in the same application.</span></span>  
  
## <a name="protocols"></a><span data-ttu-id="4d659-108">Протоколы</span><span class="sxs-lookup"><span data-stu-id="4d659-108">Protocols</span></span>  
 <span data-ttu-id="4d659-109">Используйте новую функцию ASP.NET 2.0 для проверки соответствия спецификации WS-I Basic Profile 1.1:</span><span class="sxs-lookup"><span data-stu-id="4d659-109">Use ASP.NET 2.0’s new facility for validating conformity to the WS-I Basic Profile 1.1:</span></span>  
  
```  
[WebService(Namespace = "http://tempuri.org/")]  
[WebServiceBinding(  
     ConformsTo = WsiProfiles.BasicProfile1_1,  
     EmitConformanceClaims=true)]  
public interface IEcho  
```  
  
 <span data-ttu-id="4d659-110">Веб-службы ASP.NET, соответствующие спецификации WS-I Basic Profile 1.1, будут способны взаимодействовать с клиентами [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] с помощью предопределенной привязки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] - <xref:System.ServiceModel.BasicHttpBinding>.</span><span class="sxs-lookup"><span data-stu-id="4d659-110">ASP.NET Web services that conform to WS-I Basic Profile 1.1 will be interoperable with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients by using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] predefined binding, <xref:System.ServiceModel.BasicHttpBinding>.</span></span>  
  
## <a name="service-development"></a><span data-ttu-id="4d659-111">Разработка служб</span><span class="sxs-lookup"><span data-stu-id="4d659-111">Service Development</span></span>  
 <span data-ttu-id="4d659-112">Избегайте использования атрибута <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> для маршрутизации сообщений методами по полному имени элемента текста сообщения протокола SOAP вместо заголовка HTTP SOAPAction.</span><span class="sxs-lookup"><span data-stu-id="4d659-112">Avoid using the <xref:System.Web.Services.Protocols.SoapDocumentServiceAttribute> attribute to have messages routed to methods based on the fully-qualified name of the body element of the SOAP message rather than the SOAPAction HTTP header.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="4d659-113"> использует HTTP-заголовок SOAPAction для маршрутизации сообщений.</span><span class="sxs-lookup"><span data-stu-id="4d659-113"> uses the SOAPAction HTTP header for routing messages.</span></span>  
  
## <a name="data-representation"></a><span data-ttu-id="4d659-114">Представление данных</span><span class="sxs-lookup"><span data-stu-id="4d659-114">Data Representation</span></span>  
 <span data-ttu-id="4d659-115">XML-код, в который тип сериализуется сериализатором <xref:System.Xml.Serialization.XmlSerializer>, по умолчанию семантически идентичен XML-коду, в который тип сериализуется сериализатором <xref:System.Runtime.Serialization.DataContractSerializer>, при условии, что пространство имен для XML задано явным образом.</span><span class="sxs-lookup"><span data-stu-id="4d659-115">The XML into which <xref:System.Xml.Serialization.XmlSerializer> serializes a type by default is semantically identical to the XML into which the <xref:System.Runtime.Serialization.DataContractSerializer> serializes a type, provided the namespace for the XML is explicitly defined.</span></span> <span data-ttu-id="4d659-116">При задании типа данных для использования в веб-службах ASP.NET, если в будущем планируется переход на [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], поступайте следующим образом.</span><span class="sxs-lookup"><span data-stu-id="4d659-116">When defining a data type for use with ASP.NET Web services in anticipation of adopting [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] in the future, do the following:</span></span>  
  
1.  <span data-ttu-id="4d659-117">Задавайте тип с использованием классов .NET Framework, а не схемы XML.</span><span class="sxs-lookup"><span data-stu-id="4d659-117">Define the type using .NET Framework classes rather than XML Schema.</span></span>  
  
2.  <span data-ttu-id="4d659-118">Добавляйте в класс только атрибуты <xref:System.SerializableAttribute> и <xref:System.Xml.Serialization.XmlRootAttribute>, используя последний для явного задания пространства имен для типа.</span><span class="sxs-lookup"><span data-stu-id="4d659-118">Add only the <xref:System.SerializableAttribute> and the <xref:System.Xml.Serialization.XmlRootAttribute> to the class, using the latter to explicitly define the namespace for the type.</span></span> <span data-ttu-id="4d659-119">Не добавляйте дополнительные атрибуты из пространства имен <xref:System.Xml.Serialization> для задания способа преобразования класса .NET Framework в XML.</span><span class="sxs-lookup"><span data-stu-id="4d659-119">Do no add additional attributes from the <xref:System.Xml.Serialization> namespace to control how the .NET Framework class is to be translated into XML.</span></span>  
  
 <span data-ttu-id="4d659-120">Используя этот подход, вы впоследствии сможете превратить классы .NET в контракты данных, добавив атрибуты <xref:System.Runtime.Serialization.DataContractAttribute> и <xref:System.Runtime.Serialization.DataMemberAttribute>, без значительного изменения XML-кода, в который классы сериализуются для передачи.</span><span class="sxs-lookup"><span data-stu-id="4d659-120">By adopting this approach, you should be able to later make the .NET classes into data contracts with the addition of the <xref:System.Runtime.Serialization.DataContractAttribute> and <xref:System.Runtime.Serialization.DataMemberAttribute> without significantly altering the XML into which the classes are serialized for transmission.</span></span> <span data-ttu-id="4d659-121">Типы, используемые в сообщениях веб-службами ASP.NET, смогут обрабатываться приложениями [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] как контракты данных, что, помимо прочих преимуществ, повышает производительность [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4d659-121">The types used in messages by ASP.NET Web services will be able to be processed as data contracts by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications, yielding, amongst other benefits, better performance in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="security"></a><span data-ttu-id="4d659-122">Безопасность</span><span class="sxs-lookup"><span data-stu-id="4d659-122">Security</span></span>  
 <span data-ttu-id="4d659-123">Избегайте использования параметров проверки подлинности, предусмотренных в службах IIS.</span><span class="sxs-lookup"><span data-stu-id="4d659-123">Avoid using the authentication options provided by Internet Information Services (IIS).</span></span> <span data-ttu-id="4d659-124">Клиенты [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживают их.</span><span class="sxs-lookup"><span data-stu-id="4d659-124">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients do not support them.</span></span> <span data-ttu-id="4d659-125">Если службу необходимо защитить, используйте параметры, предусмотренные в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]: они обеспечивают больше возможностей и основаны на стандартных протоколах.</span><span class="sxs-lookup"><span data-stu-id="4d659-125">If a service needs to be secured, use the options provided by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], because these options are richer and are based on standard protocols.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d659-126">См. также</span><span class="sxs-lookup"><span data-stu-id="4d659-126">See Also</span></span>  
 [<span data-ttu-id="4d659-127">Планирование перехода на платформу Windows Communication Foundation: упрощение будущей миграции</span><span class="sxs-lookup"><span data-stu-id="4d659-127">Anticipating Adopting the Windows Communication Foundation: Easing Future Migration</span></span>](../../../../docs/framework/wcf/feature-details/anticipating-adopting-wcf-migration.md)
