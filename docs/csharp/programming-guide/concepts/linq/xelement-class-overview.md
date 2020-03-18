---
title: Общие сведения о классе XElement (C#)
ms.date: 07/20/2015
ms.assetid: 2b9f0cd8-a1d1-4037-accf-0f38a410fa11
ms.openlocfilehash: 6a93dd4bdaf16fddff800b08b0f3146ecb63f9b7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "79167898"
---
# <a name="xelement-class-overview-c"></a><span data-ttu-id="f2ddb-102">Общие сведения о классе XElement (C#)</span><span class="sxs-lookup"><span data-stu-id="f2ddb-102">XElement Class Overview (C#)</span></span>
<span data-ttu-id="f2ddb-103">Класс <xref:System.Xml.Linq.XElement> - это один из фундаментальных классов в [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f2ddb-103">The <xref:System.Xml.Linq.XElement> class is one of the fundamental classes in [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)].</span></span> <span data-ttu-id="f2ddb-104">Он обозначает элемент XML.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-104">It represents an XML element.</span></span> <span data-ttu-id="f2ddb-105">Этот класс можно использовать для создания элементов, изменения содержимого элемента, добавления, изменения или удаления дочерних элементов, добавления к элементам атрибутов или сериализации содержимого элемента в текстовой форме.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-105">You can use this class to create elements; change the content of the element; add, change, or delete child elements; add attributes to an element; or serialize the contents of an element in text form.</span></span> <span data-ttu-id="f2ddb-106">Можно также настроить взаимодействие с другими классами в <xref:System.Xml?displayProperty=nameWithType>, например <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter> и <xref:System.Xml.Xsl.XslCompiledTransform>.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-106">You can also interoperate with other classes in <xref:System.Xml?displayProperty=nameWithType>, such as <xref:System.Xml.XmlReader>, <xref:System.Xml.XmlWriter>, and <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
<span data-ttu-id="f2ddb-107">В этом разделе рассматриваются функциональные особенности класса <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-107">This topic describes the functionality provided by the <xref:System.Xml.Linq.XElement> class.</span></span>  
  
## <a name="constructing-xml-trees"></a><span data-ttu-id="f2ddb-108">Создание XML-деревьев</span><span class="sxs-lookup"><span data-stu-id="f2ddb-108">Constructing XML Trees</span></span>  
 <span data-ttu-id="f2ddb-109">Можно создавать XML-деревья несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-109">You can construct XML trees in a variety of ways, including the following:</span></span>  
  
- <span data-ttu-id="f2ddb-110">Можно создать XML-дерево при помощи кода.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-110">You can construct an XML tree in code.</span></span> <span data-ttu-id="f2ddb-111">Дополнительные сведения см. в разделе [Создание деревьев XML (C#)](./linq-to-xml-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f2ddb-111">For more information, see [Creating XML Trees (C#)](./linq-to-xml-overview.md).</span></span>  
  
- <span data-ttu-id="f2ddb-112">Можно выполнить синтаксический анализ XML из нескольких источников, в том числе из <xref:System.IO.TextReader>, текстовых файлов или веб-адреса (URL-адреса).</span><span class="sxs-lookup"><span data-stu-id="f2ddb-112">You can parse XML from various sources, including a <xref:System.IO.TextReader>, text files, or a Web address (URL).</span></span> <span data-ttu-id="f2ddb-113">Дополнительные сведения см. в разделе [Анализ XML (C#)](./how-to-parse-a-string.md).</span><span class="sxs-lookup"><span data-stu-id="f2ddb-113">For more information, see [Parsing XML (C#)](./how-to-parse-a-string.md).</span></span>  
  
- <span data-ttu-id="f2ddb-114">Для распределения контента по дереву можно использовать <xref:System.Xml.XmlReader>.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-114">You can use an <xref:System.Xml.XmlReader> to populate the tree.</span></span> <span data-ttu-id="f2ddb-115">Дополнительные сведения см. в разделе <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-115">For more information, see <xref:System.Xml.Linq.XNode.ReadFrom%2A>.</span></span>  
  
- <span data-ttu-id="f2ddb-116">Если установлен модуль, позволяющий заносить содержимое в средство <xref:System.Xml.XmlWriter>, то можно использовать метод <xref:System.Xml.Linq.XContainer.CreateWriter%2A>, чтобы создать модуль записи, передать его этому модулю, после чего использовать контент, записанный в систему <xref:System.Xml.XmlWriter>, чтобы заполнить XML-дерево.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-116">If you have a module that can write content to an <xref:System.Xml.XmlWriter>, you can use the <xref:System.Xml.Linq.XContainer.CreateWriter%2A> method to create a writer, pass the writer to the module, and then use the content that is written to the <xref:System.Xml.XmlWriter> to populate the XML tree.</span></span>  
  
 <span data-ttu-id="f2ddb-117">Однако наиболее распространенным является такой метод создания XML-дерева:</span><span class="sxs-lookup"><span data-stu-id="f2ddb-117">However, the most common way to create an XML tree is as follows:</span></span>  
  
```csharp  
XElement contacts =  
    new XElement("Contacts",  
        new XElement("Contact",  
            new XElement("Name", "Patrick Hines"),
            new XElement("Phone", "206-555-0144"),  
            new XElement("Address",  
                new XElement("Street1", "123 Main St"),  
                new XElement("City", "Mercer Island"),  
                new XElement("State", "WA"),  
                new XElement("Postal", "68042")  
            )  
        )  
    );  
```  
  
 <span data-ttu-id="f2ddb-118">Другим распространенным способом создания дерева XML является использование результатов запроса LINQ для заполнения дерева XML, как показано в следующем примере:</span><span class="sxs-lookup"><span data-stu-id="f2ddb-118">Another very common technique for creating an XML tree involves using the results of a LINQ query to populate an XML tree, as shown in the following example:</span></span>  
  
```csharp  
XElement srcTree = new XElement("Root",  
    new XElement("Element", 1),  
    new XElement("Element", 2),  
    new XElement("Element", 3),  
    new XElement("Element", 4),  
    new XElement("Element", 5)  
);  
XElement xmlTree = new XElement("Root",  
    new XElement("Child", 1),  
    new XElement("Child", 2),  
    from el in srcTree.Elements()  
    where (int)el > 2  
    select el  
);  
Console.WriteLine(xmlTree);  
```  
  
 <span data-ttu-id="f2ddb-119">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="f2ddb-119">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child>1</Child>  
  <Child>2</Child>  
  <Element>3</Element>  
  <Element>4</Element>  
  <Element>5</Element>  
</Root>  
```  
  
## <a name="serializing-xml-trees"></a><span data-ttu-id="f2ddb-120">Сериализация деревьев XML</span><span class="sxs-lookup"><span data-stu-id="f2ddb-120">Serializing XML Trees</span></span>  
 <span data-ttu-id="f2ddb-121">Можно сериализовать XML-дерево в <xref:System.IO.File>, <xref:System.IO.TextWriter> или в <xref:System.Xml.XmlWriter>.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-121">You can serialize the XML tree to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="f2ddb-122">Дополнительные сведения см. в разделе [Сериализация XML-деревьев (C#)](./preserving-white-space-while-serializing.md).</span><span class="sxs-lookup"><span data-stu-id="f2ddb-122">For more information, see [Serializing XML Trees (C#)](./preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="retrieving-xml-data-via-axis-methods"></a><span data-ttu-id="f2ddb-123">Получение XML-данных через методы оси</span><span class="sxs-lookup"><span data-stu-id="f2ddb-123">Retrieving XML Data via Axis Methods</span></span>  
 <span data-ttu-id="f2ddb-124">Можно воспользоваться методами оси для получения свойств, дочерних элементов, элементов-потомков и элементов-предков.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-124">You can use axis methods to retrieve attributes, child elements, descendant elements, and ancestor elements.</span></span> <span data-ttu-id="f2ddb-125">При выполнении запросов LINQ используются методы оси и обеспечиваются гибкие и эффективные способы навигации по XML-дереву, а также его обработки.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-125">LINQ queries operate on axis methods, and provide several flexible and powerful ways to navigate through and process an XML tree.</span></span>  
  
 <span data-ttu-id="f2ddb-126">Дополнительные сведения см. в разделе [Оси LINQ to XML (C#)](./linq-to-xml-axes-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f2ddb-126">For more information, see [LINQ to XML Axes (C#)](./linq-to-xml-axes-overview.md).</span></span>  
  
## <a name="querying-xml-trees"></a><span data-ttu-id="f2ddb-127">Выполнение запросов деревьям XML</span><span class="sxs-lookup"><span data-stu-id="f2ddb-127">Querying XML Trees</span></span>  
 <span data-ttu-id="f2ddb-128">Вы можете создавать запросы LINQ, которые извлекают данные из дерева XML.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-128">You can write LINQ queries that extract data from an XML tree.</span></span>  
  
 <span data-ttu-id="f2ddb-129">Дополнительные сведения см. в разделе [Выполнение запросов к деревьям XML (C#)](./how-to-find-an-element-with-a-specific-attribute.md).</span><span class="sxs-lookup"><span data-stu-id="f2ddb-129">For more information, see [Querying XML Trees (C#)](./how-to-find-an-element-with-a-specific-attribute.md).</span></span>  
  
## <a name="modifying-xml-trees"></a><span data-ttu-id="f2ddb-130">Изменение деревьев XML</span><span class="sxs-lookup"><span data-stu-id="f2ddb-130">Modifying XML Trees</span></span>  
 <span data-ttu-id="f2ddb-131">Один и тот же элемент можно изменить несколькими способами, в том числе изменив содержимое или атрибуты.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-131">You can modify an element in a variety of ways, including changing its content or attributes.</span></span> <span data-ttu-id="f2ddb-132">Можно также удалить элемент из родительской структуры.</span><span class="sxs-lookup"><span data-stu-id="f2ddb-132">You can also remove an element from its parent.</span></span>  
  
 <span data-ttu-id="f2ddb-133">Дополнительные сведения см. в разделе [Изменение деревьев XML (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="f2ddb-133">For more information, see [Modifying XML Trees (LINQ to XML) (C#)](./in-memory-xml-tree-modification-vs-functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f2ddb-134">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="f2ddb-134">See also</span></span>

- [<span data-ttu-id="f2ddb-135">Общие сведения о программировании LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="f2ddb-135">LINQ to XML Programming Overview (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
