---
title: Сериализация XML с использованием XML-веб-служб
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML Web services, XML serialization
- XML serialization, XML Web services
- SOAP, XML serialization
- asmx files
- serialization, SOAP
- XML serialization, attributes
- attributes [.NET Framework], XML serialization
- .asmx files
- encoded XML serialization
- literal XML serialization
- serialization, attributes
ms.assetid: a416192f-8102-458e-bc0a-0b8f3f784da9
ms.openlocfilehash: c8e4e848cb37ac1b2d147b570d98777a7beaf1bb
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460256"
---
# <a name="xml-serialization-with-xml-web-services"></a>Сериализация XML с использованием XML-веб-служб
Сериализация XML является базовым механизмом передачи, применяемом в архитектуре XML-веб-служб, и выполняется с использованием класса <xref:System.Xml.Serialization.XmlSerializer>. Для управления кодом XML, созданным XML-веб-службой, для классов, возвращаемых значений, параметров и полей файла, используемых для создания XML-веб-службы (файл ASMX), можно применять атрибуты, указанные в разделах [Атрибуты управления сериализацией XML](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md) и [Атрибуты управления сериализацией с кодировкой SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md). Дополнительные сведения о создании веб-службы XML см. в разделе [XML Web Services Using ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ba0z6a33(v=vs.100)).  
  
## <a name="literal-and-encoded-styles"></a>Литеральный и кодированный стили  
 XML-код, создаваемый XML, можно отформатировать одним из двух способов: с помощью литерала или кодирования, как описано в разделах [Настройка форматирования сообщений SOAP](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dkwy2d72(v=vs.100)). Поэтому для управления XML-сериализацией предусмотрено два набора атрибутов. Атрибуты, указанные в разделе [Атрибуты управления сериализацией XML](../../../docs/standard/serialization/attributes-that-control-xml-serialization.md), предназначены для управления литеральным стилем XML. Атрибуты, указанные в разделе [Атрибуты управления сериализацией с кодировкой SOAP](../../../docs/standard/serialization/attributes-that-control-encoded-soap-serialization.md), управляют кодированным стилем. Путем выборочного применения таких атрибутов можно настроить приложение на возврат одного или обоих стилей. Кроме того, эти атрибуты применимы (в соответствующих случаях) к возвращаемым значениям и параметрам.  
  
### <a name="example-of-using-both-styles"></a>Пример использования обоих стилей.  
 При создании XML-веб-службы для методов можно использовать оба набора атрибутов. В следующем примере кода класс с именем `MyService` содержит два метода XML-веб-служб: `MyLiteralMethod` и `MyEncodedMethod`. Оба метода выполняют одну и ту же функцию: возвращение экземпляра класса `Order`. В классе `Order` оба атрибута <xref:System.Xml.Serialization.XmlTypeAttribute> и <xref:System.Xml.Serialization.SoapTypeAttribute> применяются к полю `OrderID`, и свойство `ElementName` обоих атрибутов имеет разные значения.  
  
 Чтобы запустить пример, вставьте код в файл с расширением ASMX и поместите файл в виртуальный каталог, управляемый службами IIS. В HTML-браузере, например Internet Explorer, введите имя компьютера, виртуального каталога и файла.  
  
```vb  
<%@ WebService Language="VB" Class="MyService" %>  
Imports System  
Imports System.Web.Services  
Imports System.Web.Services.Protocols  
Imports System.Xml.Serialization  
Public Class Order  
    ' Both types of attributes can be applied. Depending on which type  
    ' the method used, either one will affect the call.  
    <SoapElement(ElementName:= "EncodedOrderID"), _  
    XmlElement(ElementName:= "LiteralOrderID")> _  
    public OrderID As String  
End Class  
  
Public Class MyService  
    <WebMethod, SoapDocumentMethod> _  
    public Function MyLiteralMethod() As Order   
        Dim myOrder As Order = New Order()  
        return myOrder  
    End Function  
    <WebMethod, SoapRpcMethod> _  
    public Function MyEncodedMethod() As Order   
        Dim myOrder As Order = New Order()  
        return myOrder  
    End Function  
End Class  
```  
  
```csharp  
<%@ WebService Language="C#" Class="MyService" %>  
using System;  
using System.Web.Services;  
using System.Web.Services.Protocols;  
using System.Xml.Serialization;  
public class Order {  
    // Both types of attributes can be applied. Depending on which type  
    // the method used, either one will affect the call.  
    [SoapElement(ElementName = "EncodedOrderID")]  
    [XmlElement(ElementName = "LiteralOrderID")]  
    public String OrderID;  
}  
public class MyService {  
    [WebMethod][SoapDocumentMethod]  
    public Order MyLiteralMethod(){  
        Order myOrder = new Order();  
        return myOrder;  
    }  
    [WebMethod][SoapRpcMethod]  
    public Order MyEncodedMethod(){  
        Order myOrder = new Order();  
        return myOrder;  
    }  
}  
```  
  
 В приведенном ниже примере кода вызывается `MyLiteralMethod`. Имя элемента изменяется на "LiteralOrderID".  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethodResponse xmlns="http://tempuri.org/">  
            <MyLiteralMethodResult>  
                <LiteralOrderID>string</LiteralOrderID>  
            </MyLiteralMethodResult>  
        </MyLiteralMethodResponse>  
    </soap:Body>  
</soap:Envelope>  
```  
  
 В приведенном ниже примере кода вызывается `MyEncodedMethod`. Имя элемента - "EncodedOrderID".  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/" xmlns:tns="http://tempuri.org/" xmlns:types="http://tempuri.org/encodedTypes" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body soap:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
        <tns:MyEncodedMethodResponse>  
            <MyEncodedMethodResult href="#id1" />  
        </tns:MyEncodedMethodResponse>  
        <types:Order id="id1" xsi:type="types:Order">  
            <EncodedOrderID xsi:type="xsd:string">string</EncodedOrderID>  
        </types:Order>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="applying-attributes-to-return-values"></a>Применение атрибутов к возвращаемым значениям  
 Также можно применять атрибуты к возвращаемым значениям для управления пространством имен, именем элемента и т. д. В следующем примере кода атрибут `XmlElementAttribute` применяется к возвращаемому значению метода `MyLiteralMethod`. Это обеспечивает управление пространством имен и именем элемента.  
  
```vb  
<WebMethod, SoapDocumentMethod> _  
public Function MyLiteralMethod() As _  
<XmlElement(Namespace:="http://www.cohowinery.com", _  
ElementName:= "BookOrder")> _  
Order   
    Dim myOrder As Order = New Order()  
    return myOrder  
End Function  
```  
  
```csharp  
[return: XmlElement(Namespace = "http://www.cohowinery.com",  
ElementName = "BookOrder")]  
[WebMethod][SoapDocumentMethod]  
public Order MyLiteralMethod(){  
    Order myOrder = new Order();  
    return myOrder;  
}  
```  
  
 При вызове код возвращает XML, который может иметь следующий вид.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethodResponse xmlns="http://tempuri.org/">  
            <BookOrder xmlns="http://www.cohowinery.com">  
                <LiteralOrderID>string</LiteralOrderID>  
            </BookOrder>  
        </MyLiteralMethodResponse>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="attributes-applied-to-parameters"></a>Атрибуты, применяемые к параметрам  
 Также можно применять атрибуты к параметрам для указания пространства имен, имени элемента и т. д. В следующем примере кода к методу `MyLiteralMethodResponse` добавляется параметр, и к параметру применяется атрибут `XmlAttributeAttribute`. Для параметра задается как имя элемента, так и пространство имен.  
  
```vb  
<WebMethod, SoapDocumentMethod> _  
public Function MyLiteralMethod(<XmlElement _  
("MyOrderID", Namespace:="http://www.microsoft.com")>ID As String) As _  
<XmlElement(Namespace:="http://www.cohowinery.com", _  
ElementName:= "BookOrder")> _  
Order   
    Dim myOrder As Order = New Order()  
    myOrder.OrderID = ID  
    return myOrder  
End Function  
```  
  
```csharp  
[return: XmlElement(Namespace = "http://www.cohowinery.com",  
ElementName = "BookOrder")]  
[WebMethod][SoapDocumentMethod]  
public Order MyLiteralMethod([XmlElement("MyOrderID",   
Namespace="http://www.microsoft.com")] string ID){  
    Order myOrder = new Order();  
    myOrder.OrderID = ID;  
    return myOrder;  
}   
```  
  
 Запрос SOAP должен может иметь следующий вид.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<soap:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">  
    <soap:Body>  
        <MyLiteralMethod xmlns="http://tempuri.org/">  
            <MyOrderID xmlns="http://www.microsoft.com">string</MyOrderID>  
        </MyLiteralMethod>  
    </soap:Body>  
</soap:Envelope>  
```  
  
### <a name="applying-attributes-to-classes"></a>Применение атрибутов к классам  
 Если требуется управление пространством имен элементов, сопоставленных классам, можно применить `XmlTypeAttribute`, `XmlRootAttribute` и `SoapTypeAttribute` по мере необходимости. В следующем примере кода к классу `Order` применяются все три атрибута.  
  
```vb  
<XmlType("BigBookService"), _  
SoapType("SoapBookService"), _  
XmlRoot("BookOrderForm")> _  
Public Class Order  
    ' Both types of attributes can be applied. Depending on which  
    ' the method used, either one will affect the call.  
    <SoapElement(ElementName:= "EncodedOrderID"), _  
    XmlElement(ElementName:= "LiteralOrderID")> _  
    public OrderID As String  
End Class  
```  
  
```csharp  
[XmlType("BigBooksService", Namespace = "http://www.cpandl.com")]  
[SoapType("SoapBookService")]  
[XmlRoot("BookOrderForm")]  
public class Order {  
    // Both types of attributes can be applied. Depending on which  
    // the method used, either one will affect the call.  
    [SoapElement(ElementName = "EncodedOrderID")]  
    [XmlElement(ElementName = "LiteralOrderID")]  
    public String OrderID;  
}  
```  
  
 Результат применения `XmlTypeAttribute` и `SoapTypeAttribute` можно определить при анализе описания службы, см. пример кода ниже.  
  
```xml
<s:element name="BookOrderForm" type="s0:BigBookService" />
<s:complexType name="BigBookService">
  <s:sequence>
    <s:element minOccurs="0" maxOccurs="1" name="LiteralOrderID" type="s:string" />
  </s:sequence>

  <s:schema targetNamespace="http://tempuri.org/encodedTypes">
    <s:complexType name="SoapBookService">
      <s:sequence>
        <s:element minOccurs="1" maxOccurs="1" name="EncodedOrderID" type="s:string" />
      </s:sequence>
    </s:complexType>
  </s:schema>
</s:complexType>
```
  
 Результат `XmlRootAttribute` можно увидеть в результатах HTTP GET и HTTP POST, см. ниже.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<BookOrderForm xmlns="http://tempuri.org/">  
    <LiteralOrderID>string</LiteralOrderID>  
</BookOrderForm>  
```  
  
## <a name="see-also"></a>См. также

- [Сериализация XML и SOAP](xml-and-soap-serialization.md)
- [Атрибуты управления сериализацией с кодировкой SOAP](attributes-that-control-encoded-soap-serialization.md)
- [Практическое руководство. Сериализация объекта как потока XML с кодировкой SOAP](how-to-serialize-an-object-as-a-soap-encoded-xml-stream.md)
- [Практическое руководство. Переопределение сериализации XML с кодировкой SOAP](how-to-override-encoded-soap-xml-serialization.md)
- [Введение в сериализацию XML](introducing-xml-serialization.md)
- [Практическое руководство. Сериализация объекта](how-to-serialize-an-object.md)
- [Практическое руководство. Десериализация объекта](how-to-deserialize-an-object.md)
