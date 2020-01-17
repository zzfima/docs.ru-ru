---
title: Потоковая передача фрагментов XML из XmlReader (C#)
ms.date: 07/20/2015
ms.assetid: 4a8f0e45-768a-42e2-bc5f-68bdf0e0a726
ms.openlocfilehash: f7914d33622518f983a685dd2e844a25fd3ca15f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714656"
---
# <a name="how-to-stream-xml-fragments-from-an-xmlreader-c"></a><span data-ttu-id="b6ef5-102">Потоковая передача фрагментов XML из XmlReader (C#)</span><span class="sxs-lookup"><span data-stu-id="b6ef5-102">How to stream XML fragments from an XmlReader (C#)</span></span>

<span data-ttu-id="b6ef5-103">При необходимости обработать большой XML-файл загрузка в память полного XML-дерева, возможно, будет неосуществима.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-103">When you have to process large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="b6ef5-104">В этом разделе показано, как обрабатывать фрагменты в потоке с помощью <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-104">This topic shows how to stream fragments using an <xref:System.Xml.XmlReader>.</span></span>  
  
 <span data-ttu-id="b6ef5-105">Одним из самых эффективных способов использования <xref:System.Xml.XmlReader> для чтения объектов <xref:System.Xml.Linq.XElement> является написание собственного метода оси.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-105">One of the most effective ways to use an <xref:System.Xml.XmlReader> to read <xref:System.Xml.Linq.XElement> objects is to write your own custom axis method.</span></span> <span data-ttu-id="b6ef5-106">Метод оси, как правило, возвращает коллекцию, например <xref:System.Collections.Generic.IEnumerable%601> элементов <xref:System.Xml.Linq.XElement>, как показано в примере этого раздела.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-106">An axis method typically returns a collection such as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, as shown in the example in this topic.</span></span> <span data-ttu-id="b6ef5-107">В пользовательском методе оси после создания XML-фрагмента с помощью вызова метода <xref:System.Xml.Linq.XNode.ReadFrom%2A> возвратите коллекцию, используя `yield return`.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-107">In the custom axis method, after you create the XML fragment by calling the <xref:System.Xml.Linq.XNode.ReadFrom%2A> method, return the collection using `yield return`.</span></span> <span data-ttu-id="b6ef5-108">Тем самым в пользовательском методе оси обеспечивается семантика отложенного выполнения.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-108">This provides deferred execution semantics to your custom axis method.</span></span>  
  
 <span data-ttu-id="b6ef5-109">При создании XML-дерева из объекта <xref:System.Xml.XmlReader> модулю чтения <xref:System.Xml.XmlReader> должен быть указан обрабатываемый элемент.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-109">When you create an XML tree from an <xref:System.Xml.XmlReader> object, the <xref:System.Xml.XmlReader> must be positioned on an element.</span></span> <span data-ttu-id="b6ef5-110">Метод <xref:System.Xml.Linq.XNode.ReadFrom%2A> не выполняет возврат до тех пор, пока не считает закрывающий тег элемента.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-110">The <xref:System.Xml.Linq.XNode.ReadFrom%2A> method does not return until it has read the close tag of the element.</span></span>  
  
 <span data-ttu-id="b6ef5-111">Если нужно создать частичное дерево, можно создать экземпляр <xref:System.Xml.XmlReader>, указать для модуля чтения узел, который должен быть преобразован в дерево <xref:System.Xml.Linq.XElement>, и создать объект <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-111">If you want to create a partial tree, you can instantiate an <xref:System.Xml.XmlReader>, position the reader on the node that you want to convert to an <xref:System.Xml.Linq.XElement> tree, and then create the <xref:System.Xml.Linq.XElement> object.</span></span>  
  
<span data-ttu-id="b6ef5-112">В [руководстве по выполнению потоковой передачи фрагментов XML с доступом к сведениям заголовка (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) приводятся сведения и пример потоковой передачи более сложного документа.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-112">The topic [How to stream XML fragments with access to header information (C#)](./how-to-stream-xml-fragments-with-access-to-header-information.md) contains information and an example on how to stream a more complex document.</span></span>
  
 <span data-ttu-id="b6ef5-113">[Руководство по выполнению потокового преобразования крупных XML-документов (C#)](./how-to-perform-streaming-transform-of-large-xml-documents.md) содержит пример использования LINQ to XML для преобразования чрезвычайно больших XML-документов, используя небольшой объем памяти.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-113">The topic [How to perform streaming transform of large XML documents (C#)](./how-to-perform-streaming-transform-of-large-xml-documents.md) contains an example of using LINQ to XML to transform extremely large XML documents while maintaining a small memory footprint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b6ef5-114">Пример</span><span class="sxs-lookup"><span data-stu-id="b6ef5-114">Example</span></span>  
 <span data-ttu-id="b6ef5-115">В следующем примере создается пользовательский метод оси.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-115">This example creates a custom axis method.</span></span> <span data-ttu-id="b6ef5-116">Его можно запросить с помощью запроса LINQ.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-116">You can query it by using a LINQ query.</span></span> <span data-ttu-id="b6ef5-117">Пользовательский метод оси `StreamRootChildDoc` специально разработан для чтения документа с повторяющимся элементом `Child`.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-117">The custom axis method, `StreamRootChildDoc`, is a method that is designed specifically to read a document that has a repeating `Child` element.</span></span>  
  
```csharp  
static IEnumerable<XElement> StreamRootChildDoc(StringReader stringReader)  
{  
    using (XmlReader reader = XmlReader.Create(stringReader))  
    {  
        reader.MoveToContent();  
        // Parse the file and display each of the nodes.  
        while (reader.Read())  
        {  
            switch (reader.NodeType)  
            {  
                case XmlNodeType.Element:  
                    if (reader.Name == "Child") {  
                        XElement el = XElement.ReadFrom(reader) as XElement;  
                        if (el != null)  
                            yield return el;  
                    }  
                    break;  
            }  
        }  
    }  
}  
  
static void Main(string[] args)  
{  
    string markup = @"<Root>  
      <Child Key=""01"">  
        <GrandChild>aaa</GrandChild>  
      </Child>  
      <Child Key=""02"">  
        <GrandChild>bbb</GrandChild>  
      </Child>  
      <Child Key=""03"">  
        <GrandChild>ccc</GrandChild>  
      </Child>  
    </Root>";  
  
    IEnumerable<string> grandChildData =  
        from el in StreamRootChildDoc(new StringReader(markup))  
        where (int)el.Attribute("Key") > 1  
        select (string)el.Element("GrandChild");  
  
    foreach (string str in grandChildData) {  
        Console.WriteLine(str);  
    }  
}  
```  
  
 <span data-ttu-id="b6ef5-118">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="b6ef5-118">This example produces the following output:</span></span>  
  
```output  
bbb  
ccc  
```  
  
 <span data-ttu-id="b6ef5-119">В этом примере документ-источник весьма невелик.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-119">In this example, the source document is very small.</span></span> <span data-ttu-id="b6ef5-120">Тем не менее, даже если бы он содержал миллионы элементов `Child`, для этого примера потребовался бы очень небольшой объем памяти.</span><span class="sxs-lookup"><span data-stu-id="b6ef5-120">However, even if there were millions of `Child` elements, this example would still have a small memory footprint.</span></span>  
