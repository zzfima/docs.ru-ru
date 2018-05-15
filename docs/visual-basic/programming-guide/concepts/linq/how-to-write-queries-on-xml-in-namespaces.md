---
title: 'Как: создавать запросы к XML в пространствах имен (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
ms.openlocfilehash: f4e895e560d0fb11c128248e4f42d1d5124bc124
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a><span data-ttu-id="a7362-102">Как: создавать запросы к XML в пространствах имен (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7362-102">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>
<span data-ttu-id="a7362-103">Для записи XML-запросов в пространстве имен необходимо использовать объекты <xref:System.Xml.Linq.XName> с правильно заданным пространством имен.</span><span class="sxs-lookup"><span data-stu-id="a7362-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="a7362-104">В Visual Basic наиболее распространенным подходом является определение глобального пространства имен и последующее применение XML-литералов и XML-свойств, в которых указано это пространство имен.</span><span class="sxs-lookup"><span data-stu-id="a7362-104">In Visual Basic, the most common approach is to define a global namespace, and then use XML literals and XML properties that use the global namespace.</span></span> <span data-ttu-id="a7362-105">Можно определить глобальное пространство имен по умолчанию, и в этом случае элементы XML-литералов будут представлены в этом пространстве имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a7362-105">You can define a global default namespace, in which case elements in the XML literals will be in the namespace by default.</span></span> <span data-ttu-id="a7362-106">Иначе можно определить глобальное пространство имен с помощью префикса, а затем использовать этот префикс в XML-литералах и XML-свойствах в соответствии с необходимостью.</span><span class="sxs-lookup"><span data-stu-id="a7362-106">Alternatively, you can define a global namespace with a prefix, and then use the prefix as required in the XML literals, and in XML properties.</span></span> <span data-ttu-id="a7362-107">Как и в других формах XML, по умолчанию атрибуты всегда находятся вне пространства имен.</span><span class="sxs-lookup"><span data-stu-id="a7362-107">As with other forms of XML, attributes are always in no namespace by default.</span></span>  
  
 <span data-ttu-id="a7362-108">Первый набор примеров в данном разделе показывает порядок создания XML-дерева в пространстве имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a7362-108">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="a7362-109">Второй набор показывает порядок создания XML-дерева в пространстве имен с префиксом.</span><span class="sxs-lookup"><span data-stu-id="a7362-109">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a7362-110">Пример</span><span class="sxs-lookup"><span data-stu-id="a7362-110">Example</span></span>  
 <span data-ttu-id="a7362-111">В следующем примере создается XML-дерево, находящееся в пространстве имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a7362-111">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="a7362-112">Затем извлекается коллекция элементов.</span><span class="sxs-lookup"><span data-stu-id="a7362-112">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="a7362-113">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="a7362-113">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="a7362-114">Пример</span><span class="sxs-lookup"><span data-stu-id="a7362-114">Example</span></span>  
 <span data-ttu-id="a7362-115">Однако в Visual Basic при составлении запросов к XML-дереву, в котором используется пространство имен с префиксом, используется совершенно другой подход, чем при составлении запросов к XML-дереву, находящемуся в пространстве имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a7362-115">In Visual Basic, however, writing queries on an XML tree that uses a namespace with a prefix is quite different from querying an XML tree in a default namespace.</span></span> <span data-ttu-id="a7362-116">Как правило, пространство имен с префиксом импортируется с помощью инструкции `Imports`.</span><span class="sxs-lookup"><span data-stu-id="a7362-116">Typically you use the `Imports` statement to import the namespace with a prefix.</span></span> <span data-ttu-id="a7362-117">Затем префикс используется в именах элементов и атрибутов для построения XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="a7362-117">You then use the prefix in the element and attribute names when you construct the XML tree.</span></span> <span data-ttu-id="a7362-118">Префикс также используется при выполнении запросов к XML-дереву с помощью XML-свойств.</span><span class="sxs-lookup"><span data-stu-id="a7362-118">You also use the prefix when querying an XML tree using XML properties.</span></span>  
  
 <span data-ttu-id="a7362-119">В следующем примере создается XML-дерево, находящееся в пространстве имен с префиксом.</span><span class="sxs-lookup"><span data-stu-id="a7362-119">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="a7362-120">Затем извлекается коллекция элементов.</span><span class="sxs-lookup"><span data-stu-id="a7362-120">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>1</aw:Child>  
                <aw:Child>2</aw:Child>  
                <aw:Child>3</aw:Child>  
                <aw:AnotherChild>4</aw:AnotherChild>  
                <aw:AnotherChild>5</aw:AnotherChild>  
                <aw:AnotherChild>6</aw:AnotherChild>  
            </aw:Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<aw:Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="a7362-121">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="a7362-121">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="a7362-122">См. также</span><span class="sxs-lookup"><span data-stu-id="a7362-122">See Also</span></span>  
 [<span data-ttu-id="a7362-123">Работа с пространствами имен XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a7362-123">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
