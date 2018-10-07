---
title: 'Планирование перехода на платформу Windows Communication Foundation: упрощение будущей миграции'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 171a31b375eae4c032849c2a1c2090f5d9ff856f
ms.sourcegitcommit: 586dbdcaef9767642436b1e4efbe88fb15473d6f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/06/2018
ms.locfileid: "48837405"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Планирование перехода на платформу Windows Communication Foundation: упрощение будущей миграции
Чтобы упростить миграцию в будущем новых приложений ASP.NET на платформу WCF, выполните выше рекомендаций, а также следующие рекомендации.  
  
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
  
 Это рекомендуется, поскольку WCF требует сообщения, соответствующие различным протоколам, как SOAP 1.1 и SOAP 1.2, передавались с использованием различных конечных точках. Если веб-ASP.NET 2.0 служба настроена для поддержки SOAP 1.1 и SOAP 1.2, что является конфигурацией по умолчанию, в том случае, его нельзя перенести вперед на одну конечную точку WCF по исходному адресу, определенно было бы быть совместим со всеми веб-узла ASP.NET существующие клиенты службы. Кроме того, выбор версии SOAP 1.2 вместо версии 1.1 будет более строго ограничивать клиентуру службы.  
  
## <a name="service-development"></a>Разработка служб  
 WCF позволяет определять контракты служб, применяя <xref:System.ServiceModel.ServiceContractAttribute> интерфейсы или классы. Рекомендуется применять этот атрибут для интерфейса, а не для класса, поскольку при этом создается определение контракта, который может быть по-разному реализован любым количеством классов. ASP.NET 2.0 поддерживает возможность применения атрибута <xref:System.Web.Services.WebService> для интерфейсов и классов. Однако, как уже было сказано, в ASP.NET 2.0 существует недостаток, из-за которого параметр Namespace атрибута <xref:System.Web.Services.WebService> не имеет силы, если этот атрибут применяется для интерфейса, а не класса. Так как это обычно рекомендуется изменить пространство имен службы из значения по умолчанию, `http://tempuri.org`, используя параметр Namespace <xref:System.Web.Services.WebService> атрибута, следует продолжить определение веб-служб ASP.NET, применяя <xref:System.ServiceModel.ServiceContractAttribute> атрибут, либо для интерфейсов, либо для классов.  
  
-   Обеспечьте минимально возможный код в методах, с помощью которых определяются эти интерфейсы. Заставьте их делегировать свою работу в другие классы. Новые типы службы WCF может также делегировать свою реальную работу в этих классах.  
  
-   Обеспечьте явные имена для операций службы, используя параметр `MessageName` атрибута <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Это важно, так как имена по умолчанию для операций в ASP.NET отличаются от имен по умолчанию, предоставляемый WCF. Обеспечение явных имен исключает необходимость полагаться на имена по умолчанию.  
  
-   Не следует реализовывать операции ASP.NET веб-службы с помощью таких методов, поскольку WCF не поддерживает реализацию операций с помощью таких методов.  
  
-   Используйте атрибут <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>, чтобы обеспечить явные значения для заголовков SOAPAction HTTP, по которым запросы HTTP будут направляться в методы.  
  
    ```  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     При таком подходе исключит необходимость полагаться на значение по умолчанию значения SOAPAction, используемые ASP.NET и WCF, одинаков.  
  
-   Избегайте использования расширений SOAP. Если расширения SOAP требуются, затем определите, является ли цель, для которого они рассматриваются это функция, которая уже обеспечиваемые WCF. Если это действительно так, затем Пересмотрите возможность неприменения WCF прямо сейчас.  
  
## <a name="state-management"></a>Управление состоянием  
 Избегайте поддержания состояния в службах. Не только поддержание состояния ведет к нарушению масштабируемости приложения, но механизмы управления состоянием ASP.NET и WCF существенно различаются, несмотря на то, что WCF поддерживает механизмы ASP.NET в режиме совместимости ASP.NET.  
  
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
  
 Эти классы исключений можно будет легко многократно использовать с WCF<xref:System.ServiceModel.FaultException%601> класс, чтобы создать новое исключение `FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Безопасность  
 Ниже приведены некоторые рекомендации по безопасности.  
  
-   Избегайте использования профилей ASP.NET 2.0, так как их использование ограничит применение режима интеграции с ASP.NET, если служба была перенесена на платформу WCF.  
  
-   Избегайте использования списков ACL для управления доступом к службам, как ASP.NET Web services поддерживают списки ACL с помощью Internet Information Services (IIS), WCF не поддерживает, так как веб-службы ASP.NET зависят от служб IIS для размещения и WCF не обязательно быть размещена в IIS.  
  
-   Не принимайте во внимание использование поставщиков ролей ASP.NET 2.0 для авторизации доступа к ресурсам службы.  
  
## <a name="see-also"></a>См. также  
 [Планирование перехода на платформу Windows Communication Foundation: упрощение будущей интеграции](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
