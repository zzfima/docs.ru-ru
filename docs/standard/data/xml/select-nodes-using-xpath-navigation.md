---
title: Выбор узлов с помощью XPath-навигации
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: 8e4450dc-56b3-472b-b467-32f5694f83ad
ms.openlocfilehash: 58f1487486c2802a2c64b51afcecb01c76dd291a
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2020
ms.locfileid: "78155611"
---
# <a name="select-nodes-using-xpath-navigation"></a>Выбор узлов с помощью XPath-навигации
Модель DOM содержит методы, позволяющие использовать навигацию языка XPath для запроса данных в модели DOM. Язык XPath используется для поиска конкретного одиночного узла или всех узлов, соответствующих некоторым условиям.  
  
## <a name="xpath-select-methods"></a>Методы выбора XPath  
 Классы DOM предоставляют два способа выбора XPath: метод <xref:System.Xml.XmlNode.SelectSingleNode%2A> и метод <xref:System.Xml.XmlNode.SelectNodes%2A>. Метод <xref:System.Xml.XmlNode.SelectSingleNode%2A> возвращает первый узел, соответствующий критериям выбора. Метод <xref:System.Xml.XmlNode.SelectNodes%2A> возвращает список <xref:System.Xml.XmlNodeList>, содержащий соответствующие узлы.  
  
 В следующем примере метод <xref:System.Xml.XmlNode.SelectSingleNode%2A> используется для выбора первого узла `book`, в котором фамилия автора соответствует указанному критерию. Файл bookstore.xml (приведенный в конце этого раздела) используется в качестве входного файла.  
  
```vb  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select and display the first node in which the author's
' last name is Kingsolver.  
Dim node As XmlNode = root.SelectSingleNode( _  
     "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr)  
Console.WriteLine(node.InnerXml)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select and display the first node in which the author's
// last name is Kingsolver.  
XmlNode node = root.SelectSingleNode(  
    "descendant::bk:book[bk:author/bk:last-name='Kingsolver']", nsmgr);  
Console.WriteLine(node.InnerXml);  
```  
  
 В следующем примере метод <xref:System.Xml.XmlNode.SelectNodes%2A> используется для выбора всех узлов для книг, где цена превышает указанное значение. Затем цена каждой из книг в списке выборки программным способом уменьшается на 10 %. Наконец, файл с внесенными изменениями выводится на консоль. Файл bookstore.xml (приведенный в конце этого раздела) используется в качестве входного файла.  
  
```vb  
' Load the document and set the root element.  
Dim doc As New XmlDocument()  
doc.Load("bookstore.xml")  
Dim root As XmlNode = doc.DocumentElement  
  
' Add the namespace.  
Dim nsmgr As New XmlNamespaceManager(doc.NameTable)  
nsmgr.AddNamespace("bk", "urn:newbooks-schema")  
  
' Select all nodes where the book price is greater than 10.00.  
Dim nodeList As XmlNodeList = root.SelectNodes( _  
     "descendant::bk:book[bk:price>10.00]", nsmgr)  
For Each book As XmlNode In nodeList  
     Dim price As Double  
     price = Math.Round(Convert.ToSingle( _  
          book.LastChild.InnerText) * 0.9, 2)  
     book.LastChild.InnerText = price.ToString()  
Next  
  
' Display the updated document.  
doc.Save(Console.Out)  
```  
  
```csharp  
// Load the document and set the root element.  
XmlDocument doc = new XmlDocument();  
doc.Load("bookstore.xml");  
XmlNode root = doc.DocumentElement;  
  
// Add the namespace.  
XmlNamespaceManager nsmgr = new XmlNamespaceManager(doc.NameTable);  
nsmgr.AddNamespace("bk", "urn:newbooks-schema");  
  
// Select all nodes where the book price is greater than 10.00.  
XmlNodeList nodeList = root.SelectNodes(  
     "descendant::bk:book[bk:price>10.00]", nsmgr);  
foreach (XmlNode book in nodeList)  
{  
     // Discount prices by 10%.  
     double price;  
     price = Math.Round(Convert.ToSingle(  
          book.LastChild.InnerText) * 0.9, 2);  
     book.LastChild.InnerText = price.ToString();  
}  
  
// Display the updated document.  
doc.Save(Console.Out);  
```  
  
 В вышеприведенных примерах запрос XPath начинается с элемента документа. Указание начальной точки для запроса XPath устанавливает контекстный узел, с которого начинается запрос XPath. Если нужно начать не с элемента документа, а с первого дочернего элемента, можно использовать инструкцию выбора следующим образом.  
  
```vb  
doc.DocumentElement.FirstChild.SelectNodes(. . . )  
```  
  
```csharp  
this doc.DocumentElement.FirstChild.SelectNodes(. . .);  
```  
  
 Все объекты <xref:System.Xml.XmlNodeList> синхронизируются с базовым документом. Поэтому если при проходе по списку узлов изменить значение узла, этот узел также обновляется в исходном документе. В вышеприведенном примере обратите внимание, что при изменении узла в выбранном списке узлов <xref:System.Xml.XmlNodeList> базовый документ также изменится.  
  
> [!NOTE]
> При изменении базового документа рекомендуется повторно запустить выбор. Если изменение узла может привести к его добавлению в список узлов, где он ранее отсутствовал, или удалению из списка узлов, точность списка узлов не гарантируется.  
  
## <a name="namespaces-in-xpath-expressions"></a>Пространства имен в выражениях XPath  
 Выражения XPath могут включать пространства имен. Разрешение пространства имен поддерживается с помощью объекта <xref:System.Xml.XmlNamespaceManager>. Если выражение XPath содержит префикс, этот префикс вместе с URI-кодом пространства имен необходимо добавить к объекту <xref:System.Xml.XmlNamespaceManager>, и объект <xref:System.Xml.XmlNamespaceManager> передается методу <xref:System.Xml.XmlNode.SelectNodes%28System.String%2CSystem.Xml.XmlNamespaceManager%29> или <xref:System.Xml.XmlNode.SelectSingleNode%28System.String%2CSystem.Xml.XmlNamespaceManager%29>. Обратите внимание, что вышеприведенные примеры кода пользуются диспетчером <xref:System.Xml.XmlNamespaceManager> для разрешения пространства имен документа bookstore.xml.  
  
> [!NOTE]
> Если выражение XPath не содержит префикс, предполагается, что URI-код пространства имен указывает на пустое пространство имен. Если XML включает пространство имен по умолчанию, необходимо добавить префикс вместе с URI-кодом пространства имен к объекту <xref:System.Xml.XmlNamespaceManager>, в противном случае невозможно будет выбрать узлы.  
  
#### <a name="input-file"></a>Входной файл  
 Файл bookstore.xml используется в качестве входного файла в примерах этого раздела.  
  
```xml  
<?xml version='1.0'?>  
<bookstore xmlns="urn:newbooks-schema">  
  <book genre="novel" style="hardcover">  
    <title>The Handmaid's Tale</title>  
    <author>  
      <first-name>Margaret</first-name>  
      <last-name>Atwood</last-name>  
    </author>  
    <price>19.95</price>  
  </book>  
  <book genre="novel" style="other">  
    <title>The Poisonwood Bible</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>11.99</price>  
  </book>  
  <book genre="novel" style="paperback">  
    <title>The Bean Trees</title>  
    <author>  
      <first-name>Barbara</first-name>  
      <last-name>Kingsolver</last-name>  
    </author>  
    <price>5.99</price>  
  </book>  
</bookstore>  
```  
  
## <a name="see-also"></a>См. также раздел

- [Модель объектов документов XML (DOM)](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
