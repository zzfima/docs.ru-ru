---
title: Области пространств имен по умолчанию в C#
ms.date: 07/20/2015
ms.assetid: fe826236-830f-457a-9027-7ad62c909fae
ms.openlocfilehash: 7615351f6e5f8b18bd6466a83d54aa65a6c99b50
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253038"
---
# <a name="scope-of-default-namespaces-in-c"></a><span data-ttu-id="9cf3c-102">Области пространств имен по умолчанию в C\#</span><span class="sxs-lookup"><span data-stu-id="9cf3c-102">Scope of Default Namespaces in C\#</span></span>
<span data-ttu-id="9cf3c-103">Применяемые по умолчанию пространства имен, представленные в XML-дереве, находятся вне области запросов.</span><span class="sxs-lookup"><span data-stu-id="9cf3c-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="9cf3c-104">Если имеется XML, расположенный в используемом по умолчанию пространстве имен, для получения полного имени, которое может быть применено в запросе, то необходимо объявить переменную <xref:System.Xml.Linq.XNamespace> и использовать ее в сочетании с локальным именем.</span><span class="sxs-lookup"><span data-stu-id="9cf3c-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="9cf3c-105">Одной из наиболее типичных проблем при запросах к XML-деревьям является то, что, если XML-дерево содержит пространство имен по умолчанию, разработчик иногда пишет запрос так, как если бы XML-код не располагался в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="9cf3c-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="9cf3c-106">Первый набор примеров в данном разделе показывает типичный способ загрузки XML в пространстве имен по умолчанию и неправильного запроса к нему.</span><span class="sxs-lookup"><span data-stu-id="9cf3c-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="9cf3c-107">Второй набор примеров показывает необходимые исправления для запроса XML в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="9cf3c-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9cf3c-108">Пример</span><span class="sxs-lookup"><span data-stu-id="9cf3c-108">Example</span></span>  
 <span data-ttu-id="9cf3c-109">Этот пример показывает создание XML в пространстве имен, а также запрос, возвращающий пустой результирующий набор.</span><span class="sxs-lookup"><span data-stu-id="9cf3c-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9cf3c-110">Код</span><span class="sxs-lookup"><span data-stu-id="9cf3c-110">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="9cf3c-111">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9cf3c-111">Comments</span></span>  
 <span data-ttu-id="9cf3c-112">Этот пример выдает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="9cf3c-112">This example produces the following result:</span></span>  
  
```output  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="9cf3c-113">Пример</span><span class="sxs-lookup"><span data-stu-id="9cf3c-113">Example</span></span>  
 <span data-ttu-id="9cf3c-114">Этот пример показывает создание XML в пространстве имен, а также запрос, код которого написан правильно.</span><span class="sxs-lookup"><span data-stu-id="9cf3c-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="9cf3c-115">В отличие от вышеприведенного примера с неправильным кодом, правильный подход с использованием C# заключается в объявлении и инициализации объекта <xref:System.Xml.Linq.XNamespace> и его использовании при указании объектов <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="9cf3c-115">In contrast to the incorrectly coded example above, the correct approach when using C# is to declare and initialize an <xref:System.Xml.Linq.XNamespace> object, and to use it when specifying <xref:System.Xml.Linq.XName> objects.</span></span> <span data-ttu-id="9cf3c-116">В данном случае аргументом для метода <xref:System.Xml.Linq.XContainer.Elements%2A> является объект <xref:System.Xml.Linq.XName>.</span><span class="sxs-lookup"><span data-stu-id="9cf3c-116">In this case, the argument to the <xref:System.Xml.Linq.XContainer.Elements%2A> method is an <xref:System.Xml.Linq.XName> object.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9cf3c-117">Код</span><span class="sxs-lookup"><span data-stu-id="9cf3c-117">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="9cf3c-118">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9cf3c-118">Comments</span></span>  
 <span data-ttu-id="9cf3c-119">Этот пример выдает следующий результат:</span><span class="sxs-lookup"><span data-stu-id="9cf3c-119">This example produces the following result:</span></span>  
  
```output  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="9cf3c-120">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="9cf3c-120">See also</span></span>

- [<span data-ttu-id="9cf3c-121">Обзор пространств имен (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="9cf3c-121">Namespaces Overview (LINQ to XML) (C#)</span></span>](namespaces-overview-linq-to-xml.md)
