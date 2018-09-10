---
title: Создание деревьев XML в C# (LINQ to XML)
ms.date: 08/31/2018
ms.assetid: cc74234a-0bac-4327-9c8c-5a2ead15b595
ms.openlocfilehash: 98bad6bfc3b563b39f9e58eadbff673f202646c1
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502288"
---
# <a name="creating-xml-trees-in-c-linq-to-xml"></a><span data-ttu-id="6154d-102">Создание деревьев XML на языке C# (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="6154d-102">Creating XML trees in C# (LINQ to XML)</span></span>
<span data-ttu-id="6154d-103">В этом разделе размещены сведения о создании XML-деревьев при помощи языка C#.</span><span class="sxs-lookup"><span data-stu-id="6154d-103">This section provides information about creating XML trees in C#.</span></span>  
  
 <span data-ttu-id="6154d-104">Дополнительные сведения об использовании результатов запросов LINQ как содержимого для <xref:System.Xml.Linq.XElement> см. в разделе [Функциональное построение (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="6154d-104">For information about using the results of LINQ queries as the content for an <xref:System.Xml.Linq.XElement>, see [Functional Construction (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/functional-construction-linq-to-xml.md).</span></span>  
  
## <a name="constructing-elements"></a><span data-ttu-id="6154d-105">Построение элементов</span><span class="sxs-lookup"><span data-stu-id="6154d-105">Constructing elements</span></span>
 <span data-ttu-id="6154d-106">Сигнатуры конструкторов <xref:System.Xml.Linq.XElement> и <xref:System.Xml.Linq.XAttribute> позволяют передать конструктору содержимое элемента или атрибута в качестве аргументов.</span><span class="sxs-lookup"><span data-stu-id="6154d-106">The signatures of the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XAttribute> constructors let you pass the contents of the element or attribute as arguments to the constructor.</span></span> <span data-ttu-id="6154d-107">Поскольку один из конструкторов принимает переменное количество аргументов, можно пропустить любое количество дочерних элементов.</span><span class="sxs-lookup"><span data-stu-id="6154d-107">Because one of the constructors takes a variable number of arguments, you can pass any number of child elements.</span></span> <span data-ttu-id="6154d-108">Естественно, каждый из этих дочерних элементов может содержать собственные дочерние элементы.</span><span class="sxs-lookup"><span data-stu-id="6154d-108">Of course, each of those child elements can contain their own child elements.</span></span> <span data-ttu-id="6154d-109">Для любого элемента можно добавить любое количество атрибутов.</span><span class="sxs-lookup"><span data-stu-id="6154d-109">For any element, you can add any number of attributes.</span></span>  
  
 <span data-ttu-id="6154d-110">При добавлении объектов <xref:System.Xml.Linq.XNode> (в т. ч. <xref:System.Xml.Linq.XElement>) или <xref:System.Xml.Linq.XAttribute>, если новое содержимое не обладает родительской структурой, объекты просто прикрепляются к XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="6154d-110">When adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="6154d-111">Если у нового содержимого уже есть родитель и оно является частью другого XML-дерева, то новое содержимое клонируется и присоединяется к XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="6154d-111">If the new content already is parented, and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span> <span data-ttu-id="6154d-112">Это демонстрирует последний пример из данного раздела.</span><span class="sxs-lookup"><span data-stu-id="6154d-112">The last example in this topic demonstrates this.</span></span>  
  
 <span data-ttu-id="6154d-113">Чтобы создать `contacts`<xref:System.Xml.Linq.XElement>, можно использовать следующий код:</span><span class="sxs-lookup"><span data-stu-id="6154d-113">To create a `contacts`<xref:System.Xml.Linq.XElement>, you could use the following code:</span></span>  
  
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
  
 <span data-ttu-id="6154d-114">Если цель определена верно, то код для создания объектов <xref:System.Xml.Linq.XElement> становится похож на структуру соответствующего XML.</span><span class="sxs-lookup"><span data-stu-id="6154d-114">If indented properly, the code to construct <xref:System.Xml.Linq.XElement> objects closely resembles the structure of the underlying XML.</span></span>  
  
## <a name="xelement-constructors"></a><span data-ttu-id="6154d-115">Конструкторы XElement</span><span class="sxs-lookup"><span data-stu-id="6154d-115">XElement constructors</span></span>  
 <span data-ttu-id="6154d-116">В классе <xref:System.Xml.Linq.XElement> используются следующие конструкторы для функционального построения.</span><span class="sxs-lookup"><span data-stu-id="6154d-116">The <xref:System.Xml.Linq.XElement> class uses the following constructors for functional construction.</span></span> <span data-ttu-id="6154d-117">Обратите внимание, что существуют другие конструкторы для <xref:System.Xml.Linq.XElement>, однако, поскольку они не используются для функциональных построений, они здесь не приводятся.</span><span class="sxs-lookup"><span data-stu-id="6154d-117">Note that there are some other constructors for <xref:System.Xml.Linq.XElement>, but because they are not used for functional construction they are not listed here.</span></span>  
  
|<span data-ttu-id="6154d-118">Конструктор</span><span class="sxs-lookup"><span data-stu-id="6154d-118">Constructor</span></span>|<span data-ttu-id="6154d-119">Описание:</span><span class="sxs-lookup"><span data-stu-id="6154d-119">Description</span></span>|  
|-----------------|-----------------|  
|`XElement(XName name, object content)`|<span data-ttu-id="6154d-120">Создает <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="6154d-120">Creates an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="6154d-121">Параметр `name` задает имя элемента; `content` задает содержание элемента.</span><span class="sxs-lookup"><span data-stu-id="6154d-121">The `name` parameter specifies the name of the element; `content` specifies the content of the element.</span></span>|  
|`XElement(XName name)`|<span data-ttu-id="6154d-122">Создает <xref:System.Xml.Linq.XElement> с инициализацией <xref:System.Xml.Linq.XName> в соответствии с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="6154d-122">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span>|  
|`XElement(XName name, params object[] content)`|<span data-ttu-id="6154d-123">Создает <xref:System.Xml.Linq.XElement> с инициализацией <xref:System.Xml.Linq.XName> в соответствии с указанным именем.</span><span class="sxs-lookup"><span data-stu-id="6154d-123">Creates an <xref:System.Xml.Linq.XElement> with its <xref:System.Xml.Linq.XName> initialized to the specified name.</span></span> <span data-ttu-id="6154d-124">Атрибуты и/или дочерние элементы создаются из содержимого списка параметров.</span><span class="sxs-lookup"><span data-stu-id="6154d-124">The attributes and/or child elements are created from the contents of the parameter list.</span></span>|  
  
 <span data-ttu-id="6154d-125">Параметр `content` чрезвычайно гибок.</span><span class="sxs-lookup"><span data-stu-id="6154d-125">The `content` parameter is extremely flexible.</span></span> <span data-ttu-id="6154d-126">Он поддерживает любой тип объекта, который является действительным дочерним объектом <xref:System.Xml.Linq.XElement>.</span><span class="sxs-lookup"><span data-stu-id="6154d-126">It supports any type of object that is a valid child of an <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="6154d-127">К различным типам объектов, передающимся в этом параметре, применимы следующие правила.</span><span class="sxs-lookup"><span data-stu-id="6154d-127">The following rules apply to different types of objects passed in this parameter:</span></span>  
  
-   <span data-ttu-id="6154d-128">Строка добавляется как текстовое содержимое.</span><span class="sxs-lookup"><span data-stu-id="6154d-128">A string is added as text content.</span></span>  
  
-   <span data-ttu-id="6154d-129"><xref:System.Xml.Linq.XElement> добавляется к дочернему элементу.</span><span class="sxs-lookup"><span data-stu-id="6154d-129">An <xref:System.Xml.Linq.XElement> is added as a child element.</span></span>  
  
-   <span data-ttu-id="6154d-130"><xref:System.Xml.Linq.XAttribute> добавляется как атрибут.</span><span class="sxs-lookup"><span data-stu-id="6154d-130">An <xref:System.Xml.Linq.XAttribute> is added as an attribute.</span></span>  
  
-   <span data-ttu-id="6154d-131"><xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment> или <xref:System.Xml.Linq.XText> добавляется в качестве дочернего содержимого.</span><span class="sxs-lookup"><span data-stu-id="6154d-131">An <xref:System.Xml.Linq.XProcessingInstruction>, <xref:System.Xml.Linq.XComment>, or <xref:System.Xml.Linq.XText> is added as child content.</span></span>  
  
-   <span data-ttu-id="6154d-132"><xref:System.Collections.IEnumerable> перечисляется, и эти правила рекурсивно применяются к результатам.</span><span class="sxs-lookup"><span data-stu-id="6154d-132">An <xref:System.Collections.IEnumerable> is enumerated, and these rules are applied recursively to the results.</span></span>  
  
-   <span data-ttu-id="6154d-133">Для любого другого типа вызывается метод `ToString`, при этом результат добавляется как текстовое содержимое.</span><span class="sxs-lookup"><span data-stu-id="6154d-133">For any other type, its `ToString` method is called and the result is added as text content.</span></span>  
  
### <a name="creating-an-xelement-with-content"></a><span data-ttu-id="6154d-134">Создание элемента XElement с содержимым</span><span class="sxs-lookup"><span data-stu-id="6154d-134">Creating an XElement with content</span></span>  
 <span data-ttu-id="6154d-135">Можно создать <xref:System.Xml.Linq.XElement> с простым содержимым при помощи одного вызова метода.</span><span class="sxs-lookup"><span data-stu-id="6154d-135">You can create an <xref:System.Xml.Linq.XElement> that contains simple content with a single method call.</span></span> <span data-ttu-id="6154d-136">Чтобы это сделать, укажите содержимое в качестве второго параметра следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6154d-136">To do this, specify the content as the second parameter, as follows:</span></span>  
  
```csharp  
XElement n = new XElement("Customer", "Adventure Works");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="6154d-137">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6154d-137">This example produces the following output:</span></span>  
  
```xml  
<Customer>Adventure Works</Customer>  
```  
  
 <span data-ttu-id="6154d-138">Содержимому можно передать любой тип объекта.</span><span class="sxs-lookup"><span data-stu-id="6154d-138">You can pass any type of object as the content.</span></span> <span data-ttu-id="6154d-139">Например, в следующем коде выполняется создание элемента, в котором в качестве содержимого содержится число с плавающей запятой:</span><span class="sxs-lookup"><span data-stu-id="6154d-139">For example, the following code creates an element that contains a floating point number as content:</span></span>  
  
```csharp  
XElement n = new XElement("Cost", 324.50);  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="6154d-140">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6154d-140">This example produces the following output:</span></span>  
  
```xml  
<Cost>324.5</Cost>  
```  
  
 <span data-ttu-id="6154d-141">Число с плавающей запятой помещается в контейнер и передается конструктору.</span><span class="sxs-lookup"><span data-stu-id="6154d-141">The floating point number is boxed and passed in to the constructor.</span></span> <span data-ttu-id="6154d-142">Это число в контейнере преобразуется в строку и используется в качестве содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="6154d-142">The boxed number is converted to a string and used as the content of the element.</span></span>  
  
### <a name="creating-an-xelement-with-a-child-element"></a><span data-ttu-id="6154d-143">Создание элемента XElement с дочерним элементом</span><span class="sxs-lookup"><span data-stu-id="6154d-143">Creating an XElement with a child element</span></span>  
 <span data-ttu-id="6154d-144">Если передать экземпляр класса <xref:System.Xml.Linq.XElement> как аргумент содержимого, конструктор создаст элемент с дочерним элементом:</span><span class="sxs-lookup"><span data-stu-id="6154d-144">If you pass an instance of the <xref:System.Xml.Linq.XElement> class for the content argument, the constructor creates an element with a child element:</span></span>  
  
```csharp  
XElement shippingUnit = new XElement("ShippingUnit",  
    new XElement("Cost", 324.50)  
);  
Console.WriteLine(shippingUnit);  
```  
  
 <span data-ttu-id="6154d-145">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6154d-145">This example produces the following output:</span></span>  
  
```xml  
<ShippingUnit>  
  <Cost>324.5</Cost>  
</ShippingUnit>  
```  
  
### <a name="creating-an-xelement-with-multiple-child-elements"></a><span data-ttu-id="6154d-146">Создание элемента XElement с несколькими дочерними элементами</span><span class="sxs-lookup"><span data-stu-id="6154d-146">Creating an XElement with multiple child elements</span></span>  
 <span data-ttu-id="6154d-147">Можно передать некоторое количество объектов <xref:System.Xml.Linq.XElement> в качестве содержимого.</span><span class="sxs-lookup"><span data-stu-id="6154d-147">You can pass in a number of <xref:System.Xml.Linq.XElement> objects for the content.</span></span> <span data-ttu-id="6154d-148">Каждый из объектов <xref:System.Xml.Linq.XElement> включается в качестве дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="6154d-148">Each of the <xref:System.Xml.Linq.XElement> objects is included as a child element.</span></span>  
  
```csharp  
XElement address = new XElement("Address",  
    new XElement("Street1", "123 Main St"),  
    new XElement("City", "Mercer Island"),  
    new XElement("State", "WA"),  
    new XElement("Postal", "68042")  
);  
Console.WriteLine(address);  
```  
  
 <span data-ttu-id="6154d-149">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6154d-149">This example produces the following output:</span></span>  
  
```xml  
<Address>  
  <Street1>123 Main St</Street1>  
  <City>Mercer Island</City>  
  <State>WA</State>  
  <Postal>68042</Postal>  
</Address>  
```  
  
 <span data-ttu-id="6154d-150">Расширив предыдущим пример, можно создать все XML-дерево следующим образом:</span><span class="sxs-lookup"><span data-stu-id="6154d-150">By extending the above example, you can create an entire XML tree, as follows:</span></span>  
  
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
Console.WriteLine(contacts);  
```  
  
 <span data-ttu-id="6154d-151">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6154d-151">This example produces the following output:</span></span>  
  
```xml  
<Contacts>  
  <Contact>  
    <Name>Patrick Hines</Name>  
    <Phone>206-555-0144</Phone>  
    <Address>  
      <Street1>123 Main St</Street1>  
      <City>Mercer Island</City>  
      <State>WA</State>  
      <Postal>68042</Postal>  
    </Address>  
  </Contact>  
</Contacts>  
```  
  
### <a name="creating-an-empty-element"></a><span data-ttu-id="6154d-152">Создание пустого элемента</span><span class="sxs-lookup"><span data-stu-id="6154d-152">Creating an empty element</span></span>  
 <span data-ttu-id="6154d-153">Чтобы создать пустой элемент <xref:System.Xml.Linq.XElement>, нужно просто не передавать никакого содержимого в конструктор.</span><span class="sxs-lookup"><span data-stu-id="6154d-153">To create an empty <xref:System.Xml.Linq.XElement>, you do not pass any content to the constructor.</span></span> <span data-ttu-id="6154d-154">На следующем примере показано создание пустого элемента:</span><span class="sxs-lookup"><span data-stu-id="6154d-154">The following example creates an empty element:</span></span>  
  
```csharp  
XElement n = new XElement("Customer");  
Console.WriteLine(n);  
```  
  
 <span data-ttu-id="6154d-155">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="6154d-155">This example produces the following output:</span></span>  
  
```xml  
<Customer />  
```  
  
### <a name="attaching-vs-cloning"></a><span data-ttu-id="6154d-156">Присоединение и клонирование</span><span class="sxs-lookup"><span data-stu-id="6154d-156">Attaching vs. cloning</span></span>  
 <span data-ttu-id="6154d-157">Как упоминалось ранее, при добавлении объектов <xref:System.Xml.Linq.XNode> (в т. ч. <xref:System.Xml.Linq.XElement>) или <xref:System.Xml.Linq.XAttribute>, если новое содержимое не обладает родительской структурой, объекты просто прикрепляются к XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="6154d-157">As mentioned previously, when adding <xref:System.Xml.Linq.XNode> (including <xref:System.Xml.Linq.XElement>) or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="6154d-158">Если у нового содержимого уже есть родитель и оно является частью другого XML-дерева, то новое содержимое клонируется и присоединяется к XML-дереву.</span><span class="sxs-lookup"><span data-stu-id="6154d-158">If the new content already is parented and is part of another XML tree, the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  

<span data-ttu-id="6154d-159">В следующем примере кода показано поведение при добавлении к дереву элемента с родителем и при добавлении к дереву элемента без родителей.</span><span class="sxs-lookup"><span data-stu-id="6154d-159">The following example demonstrates the behavior when you add a parented element to a tree, and when you add an element with no parent to a tree.</span></span>

```csharp  
// Create a tree with a child element.  
XElement xmlTree1 = new XElement("Root",  
    new XElement("Child1", 1)  
);  
  
// Create an element that is not parented.  
XElement child2 = new XElement("Child2", 2);  
  
// Create a tree and add Child1 and Child2 to it.  
XElement xmlTree2 = new XElement("Root",  
    xmlTree1.Element("Child1"),  
    child2  
);  
  
// Compare Child1 identity.  
Console.WriteLine("Child1 was {0}",  
    xmlTree1.Element("Child1") == xmlTree2.Element("Child1") ?  
    "attached" : "cloned");  
  
// Compare Child2 identity.  
Console.WriteLine("Child2 was {0}",  
    child2 == xmlTree2.Element("Child2") ?  
    "attached" : "cloned");  

// The example displays the following output:  
//    Child1 was cloned  
//    Child2 was attached  
```

## <a name="see-also"></a><span data-ttu-id="6154d-160">См. также</span><span class="sxs-lookup"><span data-stu-id="6154d-160">See Also</span></span>

- [<span data-ttu-id="6154d-161">Создание деревьев XML (C#)</span><span class="sxs-lookup"><span data-stu-id="6154d-161">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
