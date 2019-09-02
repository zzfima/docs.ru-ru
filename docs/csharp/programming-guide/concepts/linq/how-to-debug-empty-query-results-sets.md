---
title: Практическое руководство. Отладка пустых наборов результатов запроса (C#)
ms.date: 07/20/2015
ms.assetid: b569f0dc-425e-45a6-acbf-770fb761c981
ms.openlocfilehash: 12d2132f1f088050fdd109d067069870b82f2661
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205316"
---
# <a name="how-to-debug-empty-query-results-sets-c"></a><span data-ttu-id="e482f-102">Практическое руководство. Отладка пустых наборов результатов запроса (C#)</span><span class="sxs-lookup"><span data-stu-id="e482f-102">How to: Debug Empty Query Results Sets (C#)</span></span>
<span data-ttu-id="e482f-103">Одной из наиболее типичных проблем при запросах к XML-деревьям является то, что, если XML-дерево содержит пространство имен по умолчанию, разработчик иногда пишет запрос так, как если бы XML-код не располагался в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="e482f-103">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="e482f-104">Первый набор примеров в данном разделе показывает типичный способ загрузки XML в пространстве имен по умолчанию и неправильного запроса к нему.</span><span class="sxs-lookup"><span data-stu-id="e482f-104">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, and is queried improperly.</span></span>  
  
 <span data-ttu-id="e482f-105">Второй набор примеров показывает необходимые исправления для запроса XML в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="e482f-105">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
 <span data-ttu-id="e482f-106">Дополнительные сведения см. в статье [Обзор пространств имен DFS (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e482f-106">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e482f-107">Пример</span><span class="sxs-lookup"><span data-stu-id="e482f-107">Example</span></span>  
 <span data-ttu-id="e482f-108">Этот пример показывает создание XML в пространстве имен, а также запрос, возвращающий пустой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="e482f-108">This example shows creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
```csharp  
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
    from el in root.Elements("Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 <span data-ttu-id="e482f-109">Этот пример выдает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="e482f-109">This example produces the following result:</span></span>  
  
```output  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="e482f-110">Пример</span><span class="sxs-lookup"><span data-stu-id="e482f-110">Example</span></span>  
 <span data-ttu-id="e482f-111">Этот пример показывает создание XML в пространстве имен, а также запрос, код которого написан правильно.</span><span class="sxs-lookup"><span data-stu-id="e482f-111">This example shows creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="e482f-112">Решение заключается в объявлении и инициализации объекта <xref:System.Xml.Linq.XNamespace> и его использовании при указании объектов <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="e482f-112">The solution is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="e482f-113">В данном случае аргументом для метода <xref:System.Xml.Linq.XContainer.Elements%2A> является объект <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="e482f-113">In this case, the argument to the <xref:System.Xml.Linq.XContainer.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
@"<Root xmlns='http://www.adventure-works.com'>  
    <Child>1</Child>  
    <Child>2</Child>  
    <Child>3</Child>  
    <AnotherChild>4</AnotherChild>  
    <AnotherChild>5</AnotherChild>  
    <AnotherChild>6</AnotherChild>  
</Root>");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> c1 =  
    from el in root.Elements(aw + "Child")  
    select el;  
Console.WriteLine("Result set follows:");  
foreach (XElement el in c1)  
    Console.WriteLine((int)el);  
Console.WriteLine("End of result set");  
```  
  
 <span data-ttu-id="e482f-114">Этот пример выдает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="e482f-114">This example produces the following result:</span></span>  
  
```output  
Result set follows:  
1  
2  
3  
End of result set  
```  
