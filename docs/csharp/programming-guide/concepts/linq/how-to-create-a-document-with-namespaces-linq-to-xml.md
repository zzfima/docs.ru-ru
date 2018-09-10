---
title: Практическое руководство. Создание документа с пространствами имен (C#) (LINQ to XML)
ms.date: 07/20/2015
ms.assetid: 37e63c57-f86d-47ac-88a7-2c2d107def30
ms.openlocfilehash: 5937639fc48b82ee155450a3eaa1c7715ee3f9b9
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2018
ms.locfileid: "43478030"
---
# <a name="how-to-create-a-document-with-namespaces-c-linq-to-xml"></a><span data-ttu-id="1840d-102">Практическое руководство. Создание документа с пространствами имен (C#) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="1840d-102">How to: Create a Document with Namespaces (C#) (LINQ to XML)</span></span>
<span data-ttu-id="1840d-103">В этом разделе описано, как создавать документы с пространствами имен.</span><span class="sxs-lookup"><span data-stu-id="1840d-103">This topic shows how to create documents with namespaces.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1840d-104">Пример</span><span class="sxs-lookup"><span data-stu-id="1840d-104">Example</span></span>  
 <span data-ttu-id="1840d-105">Чтобы создать элемент или атрибут, находящийся в пространстве имен, необходимо сначала объявить и инициализировать объект <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="1840d-105">To create an element or an attribute that is in a namespace, you first declare and initialize an <xref:System.Xml.Linq.XNamespace> object.</span></span> <span data-ttu-id="1840d-106">Затем следует использовать перегруженный оператор сложения для объединения пространства имен с локальным именем, выраженным строкой.</span><span class="sxs-lookup"><span data-stu-id="1840d-106">You then use the addition operator overload to combine the namespace with the local name, expressed as a string.</span></span>  
  
 <span data-ttu-id="1840d-107">В следующем примере создается документ с одним пространством имен.</span><span class="sxs-lookup"><span data-stu-id="1840d-107">The following example creates a document with one namespace.</span></span> <span data-ttu-id="1840d-108">По умолчанию [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] сериализует документ с использованием пространства имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1840d-108">By default, [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] serializes this document with a default namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="1840d-109">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="1840d-109">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com">  
  <Child>child content</Child>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="1840d-110">Пример</span><span class="sxs-lookup"><span data-stu-id="1840d-110">Example</span></span>  
 <span data-ttu-id="1840d-111">В следующем примере создается документ с одним пространством имен.</span><span class="sxs-lookup"><span data-stu-id="1840d-111">The following example creates a document with one namespace.</span></span> <span data-ttu-id="1840d-112">Он также создает атрибут, который объявляет пространство имен с префиксом пространства имен.</span><span class="sxs-lookup"><span data-stu-id="1840d-112">It also creates an attribute that declares the namespace with a namespace prefix.</span></span> <span data-ttu-id="1840d-113">Создать атрибут, объявляющий пространство имен с префиксом, можно, указав имя атрибута в качестве префикса пространства имен и поместив его в пространство имен <xref:System.Xml.Linq.XNamespace.Xmlns%2A>.</span><span class="sxs-lookup"><span data-stu-id="1840d-113">To create an attribute that declares a namespace with a prefix, you create an attribute where the name of the attribute is the namespace prefix, and this name is in the <xref:System.Xml.Linq.XNamespace.Xmlns%2A> namespace.</span></span> <span data-ttu-id="1840d-114">Значение этого атрибута представляет собой URI пространства имен.</span><span class="sxs-lookup"><span data-stu-id="1840d-114">The value of this attribute is the URI of the namespace.</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement(aw + "Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="1840d-115">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="1840d-115">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="1840d-116">Пример</span><span class="sxs-lookup"><span data-stu-id="1840d-116">Example</span></span>  
 <span data-ttu-id="1840d-117">Следующий пример иллюстрирует создание документа, содержащего два пространства имен.</span><span class="sxs-lookup"><span data-stu-id="1840d-117">The following example shows the creation of a document that contains two namespaces.</span></span> <span data-ttu-id="1840d-118">Одно из них - пространство имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1840d-118">One is the default namespace.</span></span> <span data-ttu-id="1840d-119">Другое - пространство имен с префиксом.</span><span class="sxs-lookup"><span data-stu-id="1840d-119">Another is a namespace with a prefix.</span></span>  
  
 <span data-ttu-id="1840d-120">При включении атрибутов пространств имен в корневой элемент пространства имен сериализуются, поэтому `http://www.adventure-works.com` становится пространством имен по умолчанию, а `www.fourthcoffee.com` сериализуется с префиксом "fc".</span><span class="sxs-lookup"><span data-stu-id="1840d-120">By including namespace attributes in the root element, the namespaces are serialized so that `http://www.adventure-works.com` is the default namespace, and `www.fourthcoffee.com` is serialized with a prefix of "fc".</span></span> <span data-ttu-id="1840d-121">Чтобы создать атрибут, объявляющий применяемое по умолчанию пространство имен, необходимо создать атрибут с именем «xmlns» без пространства имен.</span><span class="sxs-lookup"><span data-stu-id="1840d-121">To create an attribute that declares a default namespace, you create an attribute with the name "xmlns", without a namespace.</span></span> <span data-ttu-id="1840d-122">Значение этого атрибута является используемым по умолчанию идентификатором URI пространства имен.</span><span class="sxs-lookup"><span data-stu-id="1840d-122">The value of the attribute is the default namespace URI.</span></span>  
  
```csharp  
// The http://www.adventure-works.com namespace is forced to be the default namespace.  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute("xmlns", "http://www.adventure-works.com"),  
    new XAttribute(XNamespace.Xmlns + "fc", "www.fourthcoffee.com"),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="1840d-123">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="1840d-123">This example produces the following output:</span></span>  
  
```xml  
<Root xmlns="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <DifferentChild>other content</DifferentChild>  
  </fc:Child>  
  <Child2>c2 content</Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</Root>  
```  
  
## <a name="example"></a><span data-ttu-id="1840d-124">Пример</span><span class="sxs-lookup"><span data-stu-id="1840d-124">Example</span></span>  
 <span data-ttu-id="1840d-125">В этом примере создается документ, который содержит два пространства имен с префиксами.</span><span class="sxs-lookup"><span data-stu-id="1840d-125">The following example creates a document that contains two namespaces, both with namespace prefixes.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XNamespace fc = "www.fourthcoffee.com";  
XElement root = new XElement(aw + "Root",  
    new XAttribute(XNamespace.Xmlns + "aw", aw.NamespaceName),  
    new XAttribute(XNamespace.Xmlns + "fc", fc.NamespaceName),  
    new XElement(fc + "Child",  
        new XElement(aw + "DifferentChild", "other content")  
    ),  
    new XElement(aw + "Child2", "c2 content"),  
    new XElement(fc + "Child3", "c3 content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="1840d-126">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="1840d-126">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com" xmlns:fc="www.fourthcoffee.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="example"></a><span data-ttu-id="1840d-127">Пример</span><span class="sxs-lookup"><span data-stu-id="1840d-127">Example</span></span>  
 <span data-ttu-id="1840d-128">Другой метод получения того же результата состоит в использовании развернутых имен вместо объявления и создания объекта <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="1840d-128">Another way to accomplish the same result is to use expanded names instead of declaring and creating an <xref:System.Xml.Linq.XNamespace> object.</span></span>  
  
 <span data-ttu-id="1840d-129">Этот подход влияет на производительность.</span><span class="sxs-lookup"><span data-stu-id="1840d-129">This approach has performance implications.</span></span> <span data-ttu-id="1840d-130">Всякий раз при передаче [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] строки, содержащей развернутое имя, система [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] должна проанализировать это имя, обнаружить атомизированное пространство имен и атомарное имя.</span><span class="sxs-lookup"><span data-stu-id="1840d-130">Each time you pass a string that contains an expanded name to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] must parse the name, find the atomized namespace, and find the atomized name.</span></span> <span data-ttu-id="1840d-131">Этот процесс требует затрат процессорного времени.</span><span class="sxs-lookup"><span data-stu-id="1840d-131">This process takes CPU time.</span></span> <span data-ttu-id="1840d-132">Если производительность является важным фактором, целесообразнее объявить и использовать объект <xref:System.Xml.Linq.XNamespace> явным образом.</span><span class="sxs-lookup"><span data-stu-id="1840d-132">If performance is important, you might want to declare and use an <xref:System.Xml.Linq.XNamespace> object explicitly.</span></span>  
  
 <span data-ttu-id="1840d-133">Если производительность важна, дополнительные сведения см. в разделе [Предварительная атомизация объектов XName (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/pre-atomization-of-xname-objects-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="1840d-133">If performance is an important issue, see [Pre-Atomization of XName Objects (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/pre-atomization-of-xname-objects-linq-to-xml.md) for more information</span></span>  
  
```csharp  
// Create an XML tree in a namespace, with a specified prefix  
XElement root = new XElement("{http://www.adventure-works.com}Root",  
    new XAttribute(XNamespace.Xmlns + "aw", "http://www.adventure-works.com"),  
    new XElement("{http://www.adventure-works.com}Child", "child content")  
);  
Console.WriteLine(root);  
```  
  
 <span data-ttu-id="1840d-134">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="1840d-134">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:aw="http://www.adventure-works.com">  
  <aw:Child>child content</aw:Child>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="1840d-135">См. также</span><span class="sxs-lookup"><span data-stu-id="1840d-135">See Also</span></span>  
 [<span data-ttu-id="1840d-136">Работа с пространствами имен XML (C#)</span><span class="sxs-lookup"><span data-stu-id="1840d-136">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
