---
title: Практическое руководство. Выполнение потокового преобразования крупных XML-документов (C#)
ms.date: 07/20/2015
ms.assetid: 5f16d1f8-5370-4b55-b0c8-e497df163037
ms.openlocfilehash: 1a12e8c0ae98be37599b05e5d63469336247d915
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33325608"
---
# <a name="how-to-perform-streaming-transform-of-large-xml-documents-c"></a><span data-ttu-id="2edcf-102">Практическое руководство. Выполнение потокового преобразования крупных XML-документов (C#)</span><span class="sxs-lookup"><span data-stu-id="2edcf-102">How to: Perform Streaming Transform of Large XML Documents (C#)</span></span>
<span data-ttu-id="2edcf-103">Иногда необходимо преобразовывать большие XML-файлы, при этом приложение должно быть написано так, чтобы используемый им объем памяти был прогнозируемым.</span><span class="sxs-lookup"><span data-stu-id="2edcf-103">Sometimes you have to transform large XML files, and write your application so that the memory footprint of the application is predictable.</span></span> <span data-ttu-id="2edcf-104">Если вставить в XML-дерево очень большой XML-файл, то объем используемой памяти будет пропорциональным размеру файла (то есть чрезмерным).</span><span class="sxs-lookup"><span data-stu-id="2edcf-104">If you try to populate an XML tree with a very large XML file, your memory usage will be proportional to the size of the file (that is, excessive).</span></span> <span data-ttu-id="2edcf-105">Поэтому следует вместо этого использовать потоки.</span><span class="sxs-lookup"><span data-stu-id="2edcf-105">Therefore, you should use a streaming technique instead.</span></span>  
  
 <span data-ttu-id="2edcf-106">Использование потоков лучше всего уместно в ситуациях, когда требуется обработать исходный документ только один раз, и элементы можно обрабатывать в порядке их следования в документе.</span><span class="sxs-lookup"><span data-stu-id="2edcf-106">Streaming techniques are best applied in situations where you need to process the source document only once, and you can process the elements in document order.</span></span> <span data-ttu-id="2edcf-107">Некоторые стандартные операторы запросов, например <xref:System.Linq.Enumerable.OrderBy%2A>, проходят через источник, собирают все данные, сортируют их и выдают первый элемент последовательности.</span><span class="sxs-lookup"><span data-stu-id="2edcf-107">Certain standard query operators, such as <xref:System.Linq.Enumerable.OrderBy%2A>, iterate their source, collect all of the data, sort it, and then finally yield the first item in the sequence.</span></span> <span data-ttu-id="2edcf-108">Отметим, что при использовании оператора запроса, который материализует свой источник перед тем, как выдать первый элемент, приложение снова будет использовать большой объем памяти.</span><span class="sxs-lookup"><span data-stu-id="2edcf-108">Note that if you use a query operator that materializes its source before yielding the first item, you will not retain a small memory footprint for your application.</span></span>  
  
 <span data-ttu-id="2edcf-109">Даже при использовании метода, описанного в разделе [Практическое руководство. Потоковая передача фрагментов XML с доступом к сведениям заголовка](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md), при попытке сборки дерева XML, содержащего преобразованный документ, объем используемой памяти будет слишком большим.</span><span class="sxs-lookup"><span data-stu-id="2edcf-109">Even if you use the technique described in [How to: Stream XML Fragments with Access to Header Information (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md), if you try to assemble an XML tree that contains the transformed document, memory usage will be too great.</span></span>  
  
 <span data-ttu-id="2edcf-110">Существует два основных подхода.</span><span class="sxs-lookup"><span data-stu-id="2edcf-110">There are two main approaches.</span></span> <span data-ttu-id="2edcf-111">Один подход заключается в использовании возможностей отложенной обработки объекта <xref:System.Xml.Linq.XStreamingElement>.</span><span class="sxs-lookup"><span data-stu-id="2edcf-111">One approach is to use the deferred processing characteristics of <xref:System.Xml.Linq.XStreamingElement>.</span></span> <span data-ttu-id="2edcf-112">Другой подход состоит в создании <xref:System.Xml.XmlWriter> и использовании возможностей [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] для записи элементов в модуле <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="2edcf-112">Another approach is to create an <xref:System.Xml.XmlWriter>, and use the capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="2edcf-113">В этом разделе рассказывается об обоих подходах.</span><span class="sxs-lookup"><span data-stu-id="2edcf-113">This topic demonstrates both approaches.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2edcf-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2edcf-114">Example</span></span>  
 <span data-ttu-id="2edcf-115">Следующий пример основан на примере в разделе [Практическое руководство. Потоковая передача фрагментов XML с доступом к сведениям заголовка (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span><span class="sxs-lookup"><span data-stu-id="2edcf-115">The following example builds on the example in [How to: Stream XML Fragments with Access to Header Information (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>  
  
 <span data-ttu-id="2edcf-116">В этом примере возможности отложенной обработки объекта <xref:System.Xml.Linq.XStreamingElement> используются для создания выходного потока.</span><span class="sxs-lookup"><span data-stu-id="2edcf-116">This example uses the deferred execution capabilities of <xref:System.Xml.Linq.XStreamingElement> to stream the output.</span></span> <span data-ttu-id="2edcf-117">Данный пример может преобразовать очень большой документ при незначительном использовании памяти.</span><span class="sxs-lookup"><span data-stu-id="2edcf-117">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="2edcf-118">Заметьте, что пользовательская ось (`StreamCustomerItem`) специально написана таким образом, что ожидает документа с элементами `Customer`, `Name` и `Item`, упорядоченными, как в следующем документе Source.xml.</span><span class="sxs-lookup"><span data-stu-id="2edcf-118">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="2edcf-119">Однако более надежная реализации должна предусматривать такую ситуацию, что при проведении синтаксического анализа встретится документ, не прошедший проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="2edcf-119">A more robust implementation, however, would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="2edcf-120">Далее показан исходный документ, Source.xml:</span><span class="sxs-lookup"><span data-stu-id="2edcf-120">The following is the source document, Source.xml:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>   
<Root>  
  <Customer>  
    <Name>A. Datum Corporation</Name>  
    <Item>  
      <Key>0001</Key>  
    </Item>  
    <Item>  
      <Key>0002</Key>  
    </Item>  
    <Item>  
      <Key>0003</Key>  
    </Item>  
    <Item>  
      <Key>0004</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Fabrikam, Inc.</Name>  
    <Item>  
      <Key>0005</Key>  
    </Item>  
    <Item>  
      <Key>0006</Key>  
    </Item>  
    <Item>  
      <Key>0007</Key>  
    </Item>  
    <Item>  
      <Key>0008</Key>  
    </Item>  
  </Customer>  
  <Customer>  
    <Name>Southridge Video</Name>  
    <Item>  
      <Key>0009</Key>  
    </Item>  
    <Item>  
      <Key>0010</Key>  
    </Item>  
  </Customer>  
</Root>  
```  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null)  
                        {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    XStreamingElement root = new XStreamingElement("Root",  
        from el in StreamCustomerItem("Source.xml")  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        )  
    );  
    root.Save("Test.xml");  
    Console.WriteLine(File.ReadAllText("Test.xml"));  
}  
```  
  
 <span data-ttu-id="2edcf-121">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2edcf-121">This code produces the following output:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="2edcf-122">Пример</span><span class="sxs-lookup"><span data-stu-id="2edcf-122">Example</span></span>  
 <span data-ttu-id="2edcf-123">Следующий пример также основан на примере в разделе [Практическое руководство. Потоковая передача фрагментов XML с доступом к сведениям заголовка (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span><span class="sxs-lookup"><span data-stu-id="2edcf-123">The following example also builds on the example in [How to: Stream XML Fragments with Access to Header Information (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md).</span></span>  
  
 <span data-ttu-id="2edcf-124">В этом примере используются возможности [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] по записи элементов в <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="2edcf-124">This example uses the capability of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to write elements to an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="2edcf-125">Данный пример может преобразовать очень большой документ при незначительном использовании памяти.</span><span class="sxs-lookup"><span data-stu-id="2edcf-125">This example can transform a very large document while maintaining a small memory footprint.</span></span>  
  
 <span data-ttu-id="2edcf-126">Заметьте, что пользовательская ось (`StreamCustomerItem`) специально написана таким образом, что ожидает документа с элементами `Customer`, `Name` и `Item`, упорядоченными, как в следующем документе Source.xml.</span><span class="sxs-lookup"><span data-stu-id="2edcf-126">Note that the custom axis (`StreamCustomerItem`) is specifically written so that it expects a document that has `Customer`, `Name`, and `Item` elements, and that those elements will be arranged as in the following Source.xml document.</span></span> <span data-ttu-id="2edcf-127">Однако при более надежной реализации должна быть либо выполнена проверка правильности исходного документа с помощью XSD, либо проведена подготовка на тот случай, что при проведении синтаксического анализа встретится документ, не прошедший проверку правильности.</span><span class="sxs-lookup"><span data-stu-id="2edcf-127">A more robust implementation, however, would either validate the source document with an XSD, or would be prepared to parse an invalid document.</span></span>  
  
 <span data-ttu-id="2edcf-128">В этом примере используется тот же исходный документ, Source.xml, как и в предыдущем примере этого раздела.</span><span class="sxs-lookup"><span data-stu-id="2edcf-128">This example uses the same source document, Source.xml, as the previous example in this topic.</span></span> <span data-ttu-id="2edcf-129">Он также выдает точно такие же выходные данные.</span><span class="sxs-lookup"><span data-stu-id="2edcf-129">It also produces exactly the same output.</span></span>  
  
 <span data-ttu-id="2edcf-130">Использование <xref:System.Xml.Linq.XStreamingElement> для создания выходного потока итогового XML-документа предпочтительнее, чем запись в <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="2edcf-130">Using <xref:System.Xml.Linq.XStreamingElement> for streaming the output XML is preferred over writing to an <xref:System.Xml.XmlWriter>.</span></span>  
  
```csharp  
static IEnumerable<XElement> StreamCustomerItem(string uri)  
{  
    using (XmlReader reader = XmlReader.Create(uri))  
    {  
        XElement name = null;  
        XElement item = null;  
  
        reader.MoveToContent();  
  
        // Parse the file, save header information when encountered, and yield the  
        // Item XElement objects as they are created.  
  
        // loop through Customer elements  
        while (reader.Read())  
        {  
            if (reader.NodeType == XmlNodeType.Element  
                && reader.Name == "Customer")  
            {  
                // move to Name element  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.Element &&  
                        reader.Name == "Name")  
                    {  
                        name = XElement.ReadFrom(reader) as XElement;  
                        break;  
                    }  
                }  
  
                // loop through Item elements  
                while (reader.Read())  
                {  
                    if (reader.NodeType == XmlNodeType.EndElement)  
                        break;  
                    if (reader.NodeType == XmlNodeType.Element  
                        && reader.Name == "Item")  
                    {  
                        item = XElement.ReadFrom(reader) as XElement;  
                        if (item != null) {  
                            XElement tempRoot = new XElement("Root",  
                                new XElement(name)  
                            );  
                            tempRoot.Add(item);  
                            yield return item;  
                        }  
                    }  
                }  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    IEnumerable<XElement> srcTree =  
        from el in StreamCustomerItem("Source.xml")  
        select new XElement("Item",  
            new XElement("Customer", (string)el.Parent.Element("Name")),  
            new XElement(el.Element("Key"))  
        );  
    XmlWriterSettings xws = new XmlWriterSettings();  
    xws.OmitXmlDeclaration = true;  
    xws.Indent = true;  
    using (XmlWriter xw = XmlWriter.Create("Output.xml", xws)) {  
        xw.WriteStartElement("Root");  
        foreach (XElement el in srcTree)  
            el.WriteTo(xw);  
        xw.WriteEndElement();  
    }  
  
    string str = File.ReadAllText("Output.xml");  
    Console.WriteLine(str);  
}  
```  
  
 <span data-ttu-id="2edcf-131">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2edcf-131">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0001</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0002</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0003</Key>  
  </Item>  
  <Item>  
    <Customer>A. Datum Corporation</Customer>  
    <Key>0004</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0005</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0006</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0007</Key>  
  </Item>  
  <Item>  
    <Customer>Fabrikam, Inc.</Customer>  
    <Key>0008</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0009</Key>  
  </Item>  
  <Item>  
    <Customer>Southridge Video</Customer>  
    <Key>0010</Key>  
  </Item>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2edcf-132">См. также</span><span class="sxs-lookup"><span data-stu-id="2edcf-132">See Also</span></span>  
 [<span data-ttu-id="2edcf-133">Расширенные методы программирования LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="2edcf-133">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
