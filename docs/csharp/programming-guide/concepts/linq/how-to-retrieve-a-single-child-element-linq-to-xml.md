---
title: Практическое руководство. Извлечение одного дочернего элемента (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: ce37db9e-76fa-46eb-b4cc-e8f32d22ad90
ms.openlocfilehash: 5f2f675f5ce4914124f62981a2591441260b6976
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592628"
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-c"></a><span data-ttu-id="3cb0c-102">Практическое руководство. Извлечение одного дочернего элемента (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="3cb0c-102">How to: Retrieve a Single Child Element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="3cb0c-103">В этом разделе объясняется, как обеспечить получение отдельных дочерних элементов, когда известно имя этого дочернего элемента.</span><span class="sxs-lookup"><span data-stu-id="3cb0c-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="3cb0c-104">Если известно имя дочернего элемента, а также то, что есть только один элемент с таким именем, удобнее получить один элемент, а не целую коллекцию.</span><span class="sxs-lookup"><span data-stu-id="3cb0c-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="3cb0c-105">Метод <xref:System.Xml.Linq.XContainer.Element%2A> возвращает первый дочерний элемент <xref:System.Xml.Linq.XElement> с указанным именем <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="3cb0c-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="3cb0c-106">Если требуется получить отдельный дочерний элемент в Visual Basic, обычно используется XML-свойство, а затем происходит получение первого элемента при помощи обозначения индексатора массива.</span><span class="sxs-lookup"><span data-stu-id="3cb0c-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cb0c-107">Пример</span><span class="sxs-lookup"><span data-stu-id="3cb0c-107">Example</span></span>  
 <span data-ttu-id="3cb0c-108">В следующем примере иллюстрируется использование метода <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="3cb0c-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="3cb0c-109">В этом примере берется XML-дерево `po` и осуществляется поиск первого элемента с именем `Comment`.</span><span class="sxs-lookup"><span data-stu-id="3cb0c-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="3cb0c-110">В примере по Visual Basic демонстрируется использование обозначения индексатора массива для получения отдельного элемента.</span><span class="sxs-lookup"><span data-stu-id="3cb0c-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="3cb0c-111">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="3cb0c-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
XElement e = po.Element("DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="3cb0c-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3cb0c-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="3cb0c-113">Пример</span><span class="sxs-lookup"><span data-stu-id="3cb0c-113">Example</span></span>  
 <span data-ttu-id="3cb0c-114">В следующем примере демонстрируется тот же код XML-документа, который находится в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="3cb0c-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="3cb0c-115">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3cb0c-115">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="3cb0c-116">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку в пространстве имен](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="3cb0c-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](./sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement e = po.Element(aw + "DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="3cb0c-117">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="3cb0c-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="3cb0c-118">См. также</span><span class="sxs-lookup"><span data-stu-id="3cb0c-118">See also</span></span>

- [<span data-ttu-id="3cb0c-119">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="3cb0c-119">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
