---
title: Практическое руководство. Указание имени альтернативного элемента для потока XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- XML serialization, overriding
- serialization, overriding
- XML stream, specifying alternate element name for
- overriding XML serialization
- classes, overriding
- overriding classes
ms.assetid: 5cc1c0b0-f94b-4525-9a41-88a582cd6668
ms.openlocfilehash: 6aaff20e2955fc9f121b3e60b14c0bbcf7515660
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78159862"
---
# <a name="how-to-specify-an-alternate-element-name-for-an-xml-stream"></a>Практическое руководство. Указание имени альтернативного элемента для потока XML
  
Используя <xref:System.Xml.Serialization.XmlSerializer>, можно создать несколько потоков XML с одним и тем же набором классов. Это может понадобиться, поскольку для двух разных XML-веб-служб требуется одинаковая основная информация с незначительными различиями. Допустим, две веб-службы XML обрабатывают заказы на книги, и поэтому для каждой из них требуются номера ISBN. Одна служба использует тег \<ISBN>, а другая — тег \<BookID>. Имеется класс с именем `Book`, содержащий поле с именем `ISBN`. При сериализации экземпляра класса `Book` имя члена (ISBN) будет по умолчанию использоваться в качестве имени элемента для тега. Первая XML-веб-служба работает, как и предполагалось. Но чтобы отправить поток XML во вторую XML-веб-службу, необходимо переопределить сериализацию, чтобы именем элемента для тега стало `BookID`.  
  
## <a name="to-create-an-xml-stream-with-an-alternate-element-name"></a>Создание потока XML с именем альтернативного элемента  
  
1. Создайте экземпляр класса <xref:System.Xml.Serialization.XmlElementAttribute>.  
  
2. Задайте <xref:System.Xml.Serialization.XmlElementAttribute.ElementName%2A> атрибута <xref:System.Xml.Serialization.XmlElementAttribute> как "BookID".  
  
3. Создайте экземпляр класса <xref:System.Xml.Serialization.XmlAttributes>.  
  
4. Добавьте объект `XmlElementAttribute` в коллекцию, доступ к которой осуществляется через свойство <xref:System.Xml.Serialization.XmlAttributes.XmlElements%2A> атрибута <xref:System.Xml.Serialization.XmlAttributes>.  
  
5. Создайте экземпляр класса <xref:System.Xml.Serialization.XmlAttributeOverrides>.  
  
6. Добавьте `XmlAttributes` к <xref:System.Xml.Serialization.XmlAttributeOverrides>, передавая тип переопределяемого объекта и имя переопределяемого члена.  
  
7. Создайте экземпляр класса `XmlSerializer` с `XmlAttributeOverrides`.  
  
8. Создайте экземпляр класса `Book`, сериализуйте или десериализуйте его.  
  
## <a name="example"></a>Пример  
  
```vb  
Public Class SerializeOverride()  
    ' Creates an XmlElementAttribute with the alternate name.  
    Dim myElementAttribute As XmlElementAttribute = _  
    New XmlElementAttribute()  
    myElementAttribute.ElementName = "BookID"  
    Dim myAttributes As XmlAttributes = New XmlAttributes()  
    myAttributes.XmlElements.Add(myElementAttribute)  
    Dim myOverrides As XmlAttributeOverrides = New XmlAttributeOverrides()  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes)  
    Dim mySerializer As XmlSerializer = _  
    New XmlSerializer(GetType(Book), myOverrides)  
    Dim b As Book = New Book()  
    b.ISBN = "123456789"  
    ' Creates a StreamWriter to write the XML stream to.  
    Dim writer As StreamWriter = New StreamWriter("Book.xml")  
    mySerializer.Serialize(writer, b);  
End Class  
```  
  
```csharp  
public class SerializeOverride()  
{  
    // Creates an XmlElementAttribute with the alternate name.  
    XmlElementAttribute myElementAttribute = new XmlElementAttribute();  
    myElementAttribute.ElementName = "BookID";  
    XmlAttributes myAttributes = new XmlAttributes();  
    myAttributes.XmlElements.Add(myElementAttribute);  
    XmlAttributeOverrides myOverrides = new XmlAttributeOverrides();  
    myOverrides.Add(typeof(Book), "ISBN", myAttributes);  
    XmlSerializer mySerializer =
    new XmlSerializer(typeof(Book), myOverrides)  
    Book b = new Book();  
    b.ISBN = "123456789"  
    // Creates a StreamWriter to write the XML stream to.  
    StreamWriter writer = new StreamWriter("Book.xml");  
    mySerializer.Serialize(writer, b);  
}  
```  
  
 Поток XML может иметь следующий вид.  
  
```xml  
<Book>  
    <BookID>123456789</BookID>  
</Book>  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Xml.Serialization.XmlElementAttribute>
- <xref:System.Xml.Serialization.XmlAttributes>
- <xref:System.Xml.Serialization.XmlAttributeOverrides>
- [Сериализация XML и SOAP](../../../docs/standard/serialization/xml-and-soap-serialization.md)
- <xref:System.Xml.Serialization.XmlSerializer>
- [Практическое руководство. Сериализация объекта](../../../docs/standard/serialization/how-to-serialize-an-object.md)
- [Практическое руководство. Десериализация объекта](../../../docs/standard/serialization/how-to-deserialize-an-object.md)
