---
title: 'Планирование перехода на платформу Windows Communication Foundation: упрощение будущей миграции'
ms.date: 03/30/2017
ms.assetid: f49664d9-e9e0-425c-a259-93f0a569d01b
ms.openlocfilehash: 995bdaaaba96bf8697ea75c1f1a17fa8e51ec2d5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79185472"
---
# <a name="anticipating-adopting-the-windows-communication-foundation-easing-future-migration"></a>Планирование перехода на платформу Windows Communication Foundation: упрощение будущей миграции
Для обеспечения более легкой дальнейшей миграции новых ASP.NET приложений в WCF, следуйте предыдущим рекомендациям, а также следующим рекомендациям.  
  
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
  
 Это целесообразно, потому что WCF требует сообщений, соответствующих различным протоколам, таким как SOAP 1.1 и SOAP 1.2, чтобы пойти с помощью различных конечных точек. Если webслужба ASP.NET 2.0 настроена для поддержки как SOAP 1.1, так и SOAP 1.2, которая является конфигурацией по умолчанию, то она не может быть перенесена вперед в одну конечную точку WCF по первоначальному адресу, который, безусловно, будет совместим со всеми ASP.NET Web существующих клиентов сервиса. Кроме того, выбор версии SOAP 1.2 вместо версии 1.1 будет более строго ограничивать клиентуру службы.  
  
## <a name="service-development"></a>Разработка служб  
 WCF позволяет определить сервисные контракты, применяя <xref:System.ServiceModel.ServiceContractAttribute> либо к интерфейсам, либо к классам. Рекомендуется применять этот атрибут для интерфейса, а не для класса, поскольку при этом создается определение контракта, который может быть по-разному реализован любым количеством классов. ASP.NET 2.0 поддерживает возможность применения атрибута <xref:System.Web.Services.WebService> для интерфейсов и классов. Однако, как уже было сказано, в ASP.NET 2.0 существует недостаток, из-за которого параметр Namespace атрибута <xref:System.Web.Services.WebService> не имеет силы, если этот атрибут применяется для интерфейса, а не класса. Поскольку обычно желательно изменять пространство имен службы из `http://tempuri.org`значения по умолчанию, <xref:System.Web.Services.WebService> используя параметр Namespace атрибута, следует <xref:System.ServiceModel.ServiceContractAttribute> продолжать определение ASP.NET Web-сервисов, применяя атрибут либо к интерфейсам, либо к классам.  
  
- Обеспечьте минимально возможный код в методах, с помощью которых определяются эти интерфейсы. Заставьте их делегировать свою работу в другие классы. Новые типы служб WCF могли бы также делегировать свои основные работы этим классам.  
  
- Обеспечьте явные имена для операций службы, используя параметр `MessageName` атрибута <xref:System.Web.Services.WebMethodAttribute>.  
  
    ```csharp  
    [WebMethod(MessageName="ExplicitName")]  
    string Echo(string input);  
    ```  
  
     Это важно, поскольку имена по умолчанию для операций в ASP.NET отличаются от имен по умолчанию, поставляемых WCF. Обеспечение явных имен исключает необходимость полагаться на имена по умолчанию.  
  
- Не реализуйте ASP.NET операции Web-сервиса полиморфными методами, так как WCF не поддерживает реализацию операций полиморфными методами.  
  
- Используйте атрибут <xref:System.Web.Services.Protocols.SoapDocumentMethodAttribute>, чтобы обеспечить явные значения для заголовков SOAPAction HTTP, по которым запросы HTTP будут направляться в методы.  
  
    ```csharp  
    [WebMethod]  
    [SoapDocumentMethod(RequestElementName="ExplicitAction")]  
    string Echo(string input);  
    ```  
  
     При таком подходе будет обойти необходимость полагаться на значения SOAPAction по умолчанию, используемые ASP.NET и WCF, которые одинаковы.  
  
- Избегайте использования расширений SOAP. Если требуется расширение SOAP, то определите, является ли цель, для которой они рассматриваются, функцией, которая уже предоставлена WCF. Если это действительно так, а затем пересмотреть выбор, чтобы не принимать WCF сразу.  
  
## <a name="state-management"></a>Управление состоянием  
 Избегайте поддержания состояния в службах. Сохранение состояния не только может поставить под угрозу масштабируемость приложения, но и механизмы государственного управления ASP.NET и WCF очень разные, хотя WCF поддерживает механизмы ASP.NET в ASP.NET режиме совместимости.  
  
## <a name="exception-handling"></a>Обработка исключений.  
 При разработке структур типов данных, которые должны передаваться и приниматься службой, разработайте также структуры для представления различных типов исключений, которые могут происходить в службе и подлежать передаче клиенту.  
  
```csharp  
[Serializable]  
[XmlRoot(Namespace="ExplicitNamespace", IsNullable=true)]  
public partial class AnticipatedException
{
    private string anticipatedExceptionInformationField;  

    public string AnticipatedExceptionInformation
    {  
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
  
```csharp  
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
  
```csharp  
AnticipatedException exception = new AnticipatedException();  
exception.AnticipatedExceptionInformation = "…";  
throw new SoapException(  
     "Fault occurred",  
     SoapException.ClientFaultCode,  
     Context.Request.Url.AbsoluteUri,  
     exception.ToXML());  
```  
  
 Эти классы исключений будут легко многоразового с классом WCF, <xref:System.ServiceModel.FaultException%601> чтобы бросить новый`FaultException<AnticipatedException>(anticipatedException);`  
  
## <a name="security"></a>Безопасность  
 Ниже приведены некоторые рекомендации по безопасности.  
  
- Избегайте использования ASP.NET профилей 2.0, так как их использование ограничило бы использование режима ASP.NET интеграции, если служба была перенесена в WCF.  
  
- Избегайте использования ACL для контроля доступа к службам, так как ASP.NET Web-сервисы поддерживают ACL с помощью информационных служб Интернета (IIS), WCF не использует, потому что ASP.NET веб-службы зависят от IIS для хостинга, и WCF не обязательно должны быть размещены в IIS.  
  
- Не принимайте во внимание использование поставщиков ролей ASP.NET 2.0 для авторизации доступа к ресурсам службы.  
  
## <a name="see-also"></a>См. также раздел

- [Планирование перехода на платформу Windows Communication Foundation: упрощение будущей интеграции](../../../../docs/framework/wcf/feature-details/anticipating-adopting-the-wcf-easing-future-integration.md)
