---
title: Как выполнить Создание запросов к XML в пространствах имен (C#)
ms.date: 07/20/2015
ms.assetid: 7c54df81-15e4-4091-8c81-a87637029130
ms.openlocfilehash: e6b966e90d1f7fc86efaa422ecd8afb030d97163
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722106"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-c"></a><span data-ttu-id="831c7-102">Как выполнить Создание запросов к XML в пространствах имен (C#)</span><span class="sxs-lookup"><span data-stu-id="831c7-102">How to: Write Queries on XML in Namespaces (C#)</span></span>
<span data-ttu-id="831c7-103">Для записи XML-запросов в пространстве имен необходимо использовать объекты <xref:System.Xml.Linq.XName> с правильно заданным пространством имен.</span><span class="sxs-lookup"><span data-stu-id="831c7-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="831c7-104">Что касается языка C#, то наиболее распространенный подход состоит в инициализации <xref:System.Xml.Linq.XNamespace> с помощью строки, содержащей URI, а затем использовании перегруженного оператора сложения для объединения пространства имен с локальным именем.</span><span class="sxs-lookup"><span data-stu-id="831c7-104">For C#, the most common approach is to initialize an <xref:System.Xml.Linq.XNamespace> using a string that contains the URI, then use the addition operator overload to combine the namespace with the local name.</span></span>  
  
 <span data-ttu-id="831c7-105">Первый набор примеров в данном разделе показывает порядок создания XML-дерева в пространстве имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="831c7-105">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="831c7-106">Второй набор показывает порядок создания XML-дерева в пространстве имен с префиксом.</span><span class="sxs-lookup"><span data-stu-id="831c7-106">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="831c7-107">Пример</span><span class="sxs-lookup"><span data-stu-id="831c7-107">Example</span></span>  
 <span data-ttu-id="831c7-108">В следующем примере создается XML-дерево, находящееся в пространстве имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="831c7-108">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="831c7-109">Затем извлекается коллекция элементов.</span><span class="sxs-lookup"><span data-stu-id="831c7-109">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="831c7-110">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="831c7-110">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="831c7-111">Пример</span><span class="sxs-lookup"><span data-stu-id="831c7-111">Example</span></span>  
 <span data-ttu-id="831c7-112">В C# порядок составления запросов одинаков как при выполнении запросов к XML-дереву, использующему пространство имен с префиксом, так и при выполнении запросов к XML-дереву, находящемуся в пространстве имен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="831c7-112">In C#, you write queries in the same way regardless of whether you are writing queries on an XML tree that uses a namespace with a prefix or on an XML tree with a default namespace.</span></span>  
  
 <span data-ttu-id="831c7-113">В следующем примере создается XML-дерево, находящееся в пространстве имен с префиксом.</span><span class="sxs-lookup"><span data-stu-id="831c7-113">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="831c7-114">Затем извлекается коллекция элементов.</span><span class="sxs-lookup"><span data-stu-id="831c7-114">It then retrieves a collection of elements.</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement root = XElement.Parse(  
@"<aw:Root xmlns:aw='http://www.adventure-works.com'>  
    <aw:Child>1</aw:Child>  
    <aw:Child>2</aw:Child>  
    <aw:Child>3</aw:Child>  
    <aw:AnotherChild>4</aw:AnotherChild>  
    <aw:AnotherChild>5</aw:AnotherChild>  
    <aw:AnotherChild>6</aw:AnotherChild>  
</aw:Root>");  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
```  
  
 <span data-ttu-id="831c7-115">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="831c7-115">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="831c7-116">См. также</span><span class="sxs-lookup"><span data-stu-id="831c7-116">See also</span></span>

- [<span data-ttu-id="831c7-117">Работа с пространствами имен XML (C#)</span><span class="sxs-lookup"><span data-stu-id="831c7-117">Working with XML Namespaces (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)
