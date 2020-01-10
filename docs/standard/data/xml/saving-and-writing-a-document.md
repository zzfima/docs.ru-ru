---
title: Сохранение и запись документа
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 097b0cb1-5743-4c3a-86ef-caf5cbe6750d
ms.openlocfilehash: 0af160b720b9eddd9e72689c920316bffdc6d21e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75710223"
---
# <a name="saving-and-writing-a-document"></a>Сохранение и запись документа
При загрузке и сохранении <xref:System.Xml.XmlDocument> между сохраненным и исходным документами возможны следующие различия:  
  
- Если свойство <xref:System.Xml.XmlDocument.PreserveWhitespace%2A> имеет значение `true` перед вызовом метода <xref:System.Xml.XmlDocument.Save%2A>, то пробелы в документе при выводе сохраняются. Если свойство имеет значение `false`, то <xref:System.Xml.XmlDocument> автоматически вставляет отступы в выходные данные.  
  
- Все пробелы между атрибутами сокращаются до одного символа пробела.  
  
- Пробелы между элементами изменяются. Значащие пробелы сохраняются, а незначащие - нет. Но при сохранении документа он будет использовать режим **отступов** <xref:System.Xml.XmlTextWriter> по умолчанию, чтобы аккуратно распечатать выходные данные, чтобы сделать его более удобочитаемым.  
  
- Символ кавычки вокруг значений атрибута по умолчанию заменяется символом двойной кавычки. Выбрать в качестве символа кавычки двойную кавычку или одинарную кавычку можно с помощью свойства <xref:System.Xml.XmlTextReader.QuoteChar%2A> класса <xref:System.Xml.XmlTextWriter>.  
  
- По умолчанию символы числовых сущностей, например `{`, развертываются.  
  
- Значение отметки порядка байт во входном документе не сохраняется. UCS-2 сохраняется как UTF-8, если явно не создана XML-декларация, указывающая другую кодировку.  
  
- Если требуется записать <xref:System.Xml.XmlDocument> в файл или поток, то записываемые выходные данные не будут отличаться от содержимого документа. То есть, <xref:System.Xml.XmlDeclaration> записывается только если объявление содержится в документе, а кодировка, используемая при записи документа, совпадает с указанной в узле декларации.  
  
## <a name="writing-an-xmldeclaration"></a>Запись XmlDeclaration  
 XML-декларацию создают члены <xref:System.Xml.XmlDocument> и элементы <xref:System.Xml.XmlDeclaration> классов <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlNode.InnerXml%2A>, метод <xref:System.Xml.XmlNode.WriteTo%2A>, а также методы <xref:System.Xml.XmlDocument> и <xref:System.Xml.XmlDocument.Save%2A> класса <xref:System.Xml.XmlDocument.WriteContentTo%2A>.  
  
 Для свойств <xref:System.Xml.XmlDocument> методов <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDocument.InnerXml%2A>, а также методов <xref:System.Xml.XmlDocument.Save%2A>, <xref:System.Xml.XmlDocument.WriteTo%2A> и <xref:System.Xml.XmlDocument.WriteContentTo%2A> кодировка, записываемая в XML-декларацию, берется из узла <xref:System.Xml.XmlDeclaration>. Если узел <xref:System.Xml.XmlDeclaration> отсутствует, <xref:System.Xml.XmlDeclaration> не записывается. Если в узле <xref:System.Xml.XmlDeclaration> нет кодировки, кодировка не записывается в XML-декларацию.  
  
 Методы <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> и <xref:System.Xml.XmlDocument.Save%2A?displayProperty=nameWithType> всегда записывают <xref:System.Xml.XmlDeclaration>. Они получают кодировку из модуля, в который производится запись. То есть, кодовое значение модуля записи переопределяет кодировку в документе и в <xref:System.Xml.XmlDeclaration>. Например, приведенный ниже код не записывает кодировку в XML-декларацию, находящуюся в выходном файле `out.xml`.  
  
```vb  
Dim doc As New XmlDocument()  
Dim tw As XmlTextWriter = New XmlTextWriter("out.xml", Nothing)  
doc.Load("text.xml")  
doc.Save(tw)  
```  
  
```csharp  
XmlDocument doc = new XmlDocument();  
XmlTextWriter tw = new XmlTextWriter("out.xml", null);  
doc.Load("text.xml");  
doc.Save(tw);  
```  
  
 Для метода <xref:System.Xml.XmlDocument.Save%2A> XML-декларация записывается с помощью метода <xref:System.Xml.XmlWriter.WriteStartDocument%2A> класса <xref:System.Xml.XmlWriter>. Поэтому при перезаписи метода <xref:System.Xml.XmlWriter.WriteStartDocument%2A> изменяется способ записи начала документа.  
  
 Для <xref:System.Xml.XmlDeclaration> членов <xref:System.Xml.XmlNode.OuterXml%2A>, <xref:System.Xml.XmlDeclaration.WriteTo%2A>и <xref:System.Xml.XmlNode.InnerXml%2A>, если свойство <xref:System.Xml.XmlDeclaration.Encoding%2A> не задано, кодировка не записывается. В противном случае кодировка, записанная в XML-декларации, совпадает с кодировкой, найденной в свойстве <xref:System.Xml.XmlDeclaration.Encoding%2A>.  
  
## <a name="writing-document-content-using-the-outerxml-property"></a>Запись содержимого документа с помощью свойства OuterXml  
 Свойство <xref:System.Xml.XmlNode.OuterXml%2A> является расширением Майкрософт для стандартов объектной модели DOM XML-документа консорциума W3C. Свойство <xref:System.Xml.XmlNode.OuterXml%2A> позволяет получить разметку как полного XML-документа, так и единичного узла вместе с его дочерними узлами. Свойство <xref:System.Xml.XmlNode.OuterXml%2A> возвращает разметку, предоставляющую заданный узел и все его дочерние узлы.  
  
 В приведенном ниже образце кода показано сохранение документа целиком в виде строки.  
  
```vb  
Dim mydoc As New XmlDocument()  
' Perform application needs here, like mydoc.Load("myfile");  
' Now save the entire document to a string variable called "xml".  
Dim xml As String = mydoc.OuterXml  
```  
  
```csharp  
XmlDocument mydoc = new XmlDocument();  
// Perform application needs here, like mydoc.Load("myfile");  
// Now save the entire document to a string variable called "xml".  
string xml = mydoc.OuterXml;  
```  
  
 В следующем образце кода показано, как сохранить только отдельный элемент документа.  
  
```vb  
' For the content of the Document Element only.  
Dim xml As String = mydoc.DocumentElement.OuterXml  
```  
  
```csharp  
// For the content of the Document Element only.  
string xml = mydoc.DocumentElement.OuterXml;  
```  
  
 Однако если требуется содержимое дочерних узлов, можно использовать свойство <xref:System.Xml.XmlNode.InnerText%2A>.  
  
## <a name="see-also"></a>См. также:

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
