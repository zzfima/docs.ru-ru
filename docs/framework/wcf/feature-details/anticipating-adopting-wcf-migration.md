---
title: "Планирование перехода на платформу Windows Communication Foundation: упрощение будущей миграции"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 76770eff76a7a641ee853f314b5d2c14a56737c1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Планирование перехода на платформу Windows Communication Foundation: упрощение будущей миграции
Чтобы упростить миграцию в будущем новых приложений ASP.NET в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], действуйте согласно предшествующим, а также следующим рекомендациям.  
  
## <a name="protocols"></a>Протоколы  
 Отключите поддержку ASP.NET 2.0 для SOAP 1.2:  
  
```xml  
<configuration>  
     <system.web>  
      <webServices >  
          <protocols>  
           <remove name="HttpSoap12"/>  
          </protocols>    
      </webServices>  
     </system.web>   
</configuration>  
```  
  
 Такое отключение рекомендуется, поскольку [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] требует, чтобы сообщения, соответствующие различным протоколам (типа SOAP 1.1 и SOAP 1.2), передавались с использованием разных конечных точек. Если веб-служба ASP.NET 2.0 настроена на поддержку и SOAP 1.1, и SOAP 1.2, что является конфигурацией по умолчанию, ее нельзя мигрировать вперед в единственную конечную точку [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] по исходному адресу, совместимому со всеми существующими клиентами веб-службы ASP.NET. Кроме того, выбор версии SOAP 1.2 вместо версии 1.1 будет более строго ограничивать клиентуру службы.  
  
## <a name="service-development"></a>Разработка служб  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] позволяет определять контракты служб, применяя атрибут <xref:System.ServiceModel.ServiceContractAttribute> либо для интерфейсов, либо для классов. Рекомендуется применять этот атрибут для интерфейса, а не для класса, поскольку при этом создается определение контракта, который может быть по-разному реализован любым количеством классов. ASP.NET 2.0 поддерживает возможность применения атрибута <xref:System.Web.Services.WebService> для интерфейсов и классов. Однако, как уже было сказано, в ASP.NET 2.0 существует недостаток, из-за которого параметр Namespace атрибута <xref:System.Web.Services.WebService> не имеет силы, если этот атрибут применяется для интерфейса, а не класса. Поскольку обычно рекомендуется изменить значение по умолчанию (http://tempuri.org) пространства имен службы, используя параметр Namespace атрибута <xref:System.Web.Services.WebService>, следует продолжить определение веб-служб ASP.NET, применяя атрибут <xref:System.ServiceModel.ServiceContractAttribute> либо для интерфейсов, либо для классов.  
  
-   Обеспечьте минимально возможный код в методах, с помощью которых определяются эти интерфейсы. Заставьте их делегировать свою работу в другие классы. Новые типы служб [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] тогда смогут также делегировать свою реальную работу в эти классы.  
  
-   Обеспечьте явные имена для операций службы, используя параметр `MessageName` атрибута <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Это важно, поскольку имена по умолчанию для операций в ASP.NET отличаются от имен по умолчанию, предоставляемых системой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Обеспечение явных имен исключает необходимость полагаться на имена по умолчанию.  
  
-   Не реализуйте операции веб-служб ASP.NET полиморфными методами, так как [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не поддерживает реализацию операций с помощью таких методов.  
  
-   Используйте атрибут <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>, чтобы обеспечить явные значения для заголовков SOAPAction HTTP, по которым запросы HTTP будут направляться в методы.  
  
    ```  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     Использование такого подхода исключит необходимость полагаться на значения SOAPAction по умолчанию, используемые ASP.NET и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Избегайте использования расширений SOAP. Если расширения SOAP требуются, определите, соответствует ли цель, для которой их предполагается использовать, функции, уже обеспеченной системой [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]. Если это так, пересмотрите сделанный выбор в пользу неприменения [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] немедленно.  
  
## <a name="state-management"></a>Управление состоянием  
 Избегайте поддержания состояния в службах. Поддержание состояния ведет к нарушению масштабируемости приложения. Кроме того, механизмы управления состоянием ASP.NET и [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] очень различаются, хотя [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] поддерживает механизмы ASP.NET в режиме совместимости с ASP.NET.  
  
## <a name="exception-handling"></a>Обработка исключений  
 При разработке структур типов данных, которые должны передаваться и приниматься службой, разработайте также структуры для представления различных типов исключений, которые могут происходить в службе и подлежать передаче клиенту.  
  
```  
[Serializable]  
[XmlRoot(  
     Namespace="ExplicitNamespace", IsNullable=true)]  
    public partial class AnticipatedException {  
  
     private string anticipatedExceptionInformationField;  
  
     public string AnticipatedExceptionInformation {  
      get {  
          return this.anticipatedExceptionInformationField;  
          }  
      set {  
          this.anticipatedExceptionInformationField = value;  
          }  
     }  
}  
```  
  
 Предоставьте таким классам возможность сериализовать себя в XML:  
  
```  
public XmlNode ToXML()  
{  
     XmlSerializer serializer = new XmlSerializer(  
      typeof(AnticipatedException));  
     MemoryStream memoryStream = new MemoryStream();  
     XmlTextWriter writer = new XmlTextWriter(  
     memoryStream, UnicodeEncoding.UTF8);  
     serializer.Serialize(writer, this);  
     XmlDocument document = new XmlDocument();  
     document.LoadXml(new string(  
     UnicodeEncoding.UTF8.GetChars(  
     memoryStream.GetBuffer())).Trim());  
    return document.DocumentElement;  
}  
```  
  
 Затем классы могут использоваться для предоставления сведений в отношении явно вызванных экземпляров <xref:System.Web.Services.Protocols.SoapException>:  
  
```  
AnctipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 Эти классы исключений можно будет легко многократно использовать с классом [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<xref:System.ServiceModel.FaultException%601> для вызова нового исключения `FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Безопасность  
 Ниже приведены некоторые рекомендации по безопасности.  
  
-   Избегайте использования профилей ASP.NET 2.0, так как их использование ограничит применение режима интеграции с ASP.NET, если служба была мигрирована в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].  
  
-   Избегайте использования списков ACL для управления доступом к службам, так как веб-службы ASP.NET поддерживают списки ACL с помощью IIS, а [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] - нет, поскольку веб-службы ASP.NET зависят в вопросе размещения от IIS, а система WCF необязательно должна быть размещена в IIS.  
  
-   Не принимайте во внимание использование поставщиков ролей ASP.NET 2.0 для авторизации доступа к ресурсам службы.  
  
## <a name="see-also"></a>См. также  
 [Планирование перехода на платформу Windows Communication Foundation: упрощение будущей интеграции](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
