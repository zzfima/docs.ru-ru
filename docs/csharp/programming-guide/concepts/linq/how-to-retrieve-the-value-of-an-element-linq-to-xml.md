---
title: Извлечение значений элемента (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 4228c007-07c9-4cf2-a45b-e7074c109581
ms.openlocfilehash: 775e7282408910cc06b7d660d84cb6f80ef47949
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347417"
---
# <a name="how-to-retrieve-the-value-of-an-element-linq-to-xml-c"></a><span data-ttu-id="52357-102">Извлечение значений элемента (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="52357-102">How to retrieve the value of an element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="52357-103">В этом разделе показано получение значений элементов.</span><span class="sxs-lookup"><span data-stu-id="52357-103">This topic shows how to get the value of elements.</span></span> <span data-ttu-id="52357-104">Это можно сделать двумя основными способами.</span><span class="sxs-lookup"><span data-stu-id="52357-104">There are two main ways to do this.</span></span> <span data-ttu-id="52357-105">Первый способ состоит в приведении <xref:System.Xml.Linq.XElement> или <xref:System.Xml.Linq.XAttribute> к желаемому типу.</span><span class="sxs-lookup"><span data-stu-id="52357-105">One way is to cast an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XAttribute> to the desired type.</span></span> <span data-ttu-id="52357-106">Оператор явного преобразования, который преобразует содержимое элемента или атрибута в указанный тип и присваивает полученное значение указанной переменной.</span><span class="sxs-lookup"><span data-stu-id="52357-106">The explicit conversion operator then converts the contents of the element or attribute to the specified type and assigns it to your variable.</span></span> <span data-ttu-id="52357-107">Иначе можно использовать свойство <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> или <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="52357-107">Alternatively, you can use the <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property or the <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
 <span data-ttu-id="52357-108">Однако при использовании C# приведение, как правило, является лучшим подходом.</span><span class="sxs-lookup"><span data-stu-id="52357-108">With C#, however, casting is generally the better approach.</span></span> <span data-ttu-id="52357-109">В частности, становится проще написание кода, обеспечивающего получение значения элемента или атрибута, который может существовать или не существовать, после приведения элемента (или атрибута) к типу, допускающему значение NULL.</span><span class="sxs-lookup"><span data-stu-id="52357-109">If you cast the element or attribute to a nullable type, the code is simpler to write when retrieving the value of an element (or attribute) that might or might not exist.</span></span> <span data-ttu-id="52357-110">Это демонстрирует последний пример из данного раздела.</span><span class="sxs-lookup"><span data-stu-id="52357-110">The last example in this topic demonstrates this.</span></span> <span data-ttu-id="52357-111">Однако нельзя так задать содержимое элемента через приведение, как через свойство <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="52357-111">However, you cannot set the contents of an element through casting, as you can through <xref:System.Xml.Linq.XElement.Value%2A?displayProperty=nameWithType> property.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52357-112">Пример</span><span class="sxs-lookup"><span data-stu-id="52357-112">Example</span></span>  
 <span data-ttu-id="52357-113">Для получения значения элемента нужно просто привести объект <xref:System.Xml.Linq.XElement> к желаемому типу.</span><span class="sxs-lookup"><span data-stu-id="52357-113">To retrieve the value of an element, you just cast the <xref:System.Xml.Linq.XElement> object to your desired type.</span></span> <span data-ttu-id="52357-114">Всегда можно привести элемент к строке следующим образом:</span><span class="sxs-lookup"><span data-stu-id="52357-114">You can always cast an element to a string, as follows:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (string)e);  
```  
  
 <span data-ttu-id="52357-115">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="52357-115">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="52357-116">Пример</span><span class="sxs-lookup"><span data-stu-id="52357-116">Example</span></span>  
 <span data-ttu-id="52357-117">Также можно приводить элементы к типам, отличным от строковых.</span><span class="sxs-lookup"><span data-stu-id="52357-117">You can also cast elements to types other than string.</span></span> <span data-ttu-id="52357-118">Например, если имеется элемент, содержащий целое число, его можно привести к типу `int`, как показано в следующем коде:</span><span class="sxs-lookup"><span data-stu-id="52357-118">For example, if you have an element that contains an integer, you can cast it to `int`, as shown in the following code:</span></span>  
  
```csharp  
XElement e = new XElement("Age", "44");  
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + (int)e);  
```  
  
 <span data-ttu-id="52357-119">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="52357-119">This example produces the following output:</span></span>  
  
```output  
<Age>44</Age>  
Value of e:44  
```  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <span data-ttu-id="52357-120">предусматривает операторы явного приведения для следующих типов данных: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID` и `GUID?`.</span><span class="sxs-lookup"><span data-stu-id="52357-120">provides explicit cast operators for the following data types: `string`, `bool`, `bool?`, `int`, `int?`, `uint`, `uint?`, `long`, `long?`, `ulong`, `ulong?`, `float`, `float?`, `double`, `double?`, `decimal`, `decimal?`, `DateTime`, `DateTime?`, `TimeSpan`, `TimeSpan?`, `GUID`, and `GUID?`.</span></span>  
  
 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]<span data-ttu-id="52357-121">предоставляет аналогичные операторы приведения для объектов <xref:System.Xml.Linq.XAttribute>.</span><span class="sxs-lookup"><span data-stu-id="52357-121">provides the same cast operators for <xref:System.Xml.Linq.XAttribute> objects.</span></span>  
  
## <a name="example"></a><span data-ttu-id="52357-122">Пример</span><span class="sxs-lookup"><span data-stu-id="52357-122">Example</span></span>  
 <span data-ttu-id="52357-123">Свойство <xref:System.Xml.Linq.XElement.Value%2A> может использоваться для получения содержимого элемента.</span><span class="sxs-lookup"><span data-stu-id="52357-123">You can use the <xref:System.Xml.Linq.XElement.Value%2A> property to retrieve the contents of an element:</span></span>  
  
```csharp  
XElement e = new XElement("StringElement", "abcde");   
Console.WriteLine(e);  
Console.WriteLine("Value of e:" + e.Value);  
```  
  
 <span data-ttu-id="52357-124">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="52357-124">This example produces the following output:</span></span>  
  
```output  
<StringElement>abcde</StringElement>  
Value of e:abcde  
```  
  
## <a name="example"></a><span data-ttu-id="52357-125">Пример</span><span class="sxs-lookup"><span data-stu-id="52357-125">Example</span></span>  
 <span data-ttu-id="52357-126">Иногда осуществляются попытки получить значение элемента, в отношении которого неизвестно, существует ли он.</span><span class="sxs-lookup"><span data-stu-id="52357-126">Sometimes you try to retrieve the value of an element even though you are not sure it exists.</span></span> <span data-ttu-id="52357-127">Таким образом, при назначении приведенного элемента типу, допускающему значение NULL (`string` или одному из таких типов в .NET Framework), если элемент не существует, переменной просто присваивается `null`.</span><span class="sxs-lookup"><span data-stu-id="52357-127">In this case, when you assign the casted element to a nullable type (either `string` or one of the nullable types in the .NET Framework), if the element does not exist the assigned variable is just set to `null`.</span></span> <span data-ttu-id="52357-128">В следующем коде показано, что при отсутствии сведений о том, существует ли элемент, проще использовать приведение типа, чем свойство <xref:System.Xml.Linq.XElement.Value%2A>.</span><span class="sxs-lookup"><span data-stu-id="52357-128">The following code shows that when the element might or might not exist, it is easier to use casting than to use the <xref:System.Xml.Linq.XElement.Value%2A> property.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Child1", "child 1 content"),  
    new XElement("Child2", "2")  
);  
  
// The following assignments show why it is easier to use  
// casting when the element might or might not exist.  
  
string c1 = (string)root.Element("Child1");  
Console.WriteLine("c1:{0}", c1 == null ? "element does not exist" : c1);  
  
int? c2 = (int?)root.Element("Child2");  
Console.WriteLine("c2:{0}", c2 == null ? "element does not exist" : c2.ToString());  
  
string c3 = (string)root.Element("Child3");  
Console.WriteLine("c3:{0}", c3 == null ? "element does not exist" : c3);  
  
int? c4 = (int?)root.Element("Child4");  
Console.WriteLine("c4:{0}", c4 == null ? "element does not exist" : c4.ToString());  
  
Console.WriteLine();  
  
// The following assignments show the required code when using  
// the Value property when the element might or might not exist.  
// Notice that this is more difficult than the casting approach.  
  
XElement e1 = root.Element("Child1");  
string v1;  
if (e1 == null)  
    v1 = null;  
else  
    v1 = e1.Value;  
Console.WriteLine("v1:{0}", v1 == null ? "element does not exist" : v1);  
  
XElement e2 = root.Element("Child2");  
int? v2;  
if (e2 == null)  
    v2 = null;  
else  
    v2 = Int32.Parse(e2.Value);  
Console.WriteLine("v2:{0}", v2 == null ? "element does not exist" : v2.ToString());  
  
XElement e3 = root.Element("Child3");  
string v3;  
if (e3 == null)  
    v3 = null;  
else  
    v3 = e3.Value;  
Console.WriteLine("v3:{0}", v3 == null ? "element does not exist" : v3);  
  
XElement e4 = root.Element("Child4");  
int? v4;  
if (e4 == null)  
    v4 = null;  
else  
    v4 = Int32.Parse(e4.Value);  
Console.WriteLine("v4:{0}", v4 == null ? "element does not exist" : v4.ToString());  
```  
  
 <span data-ttu-id="52357-129">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="52357-129">This code produces the following output:</span></span>  
  
```output  
c1:child 1 content  
c2:2  
c3:element does not exist  
c4:element does not exist  
  
v1:child 1 content  
v2:2  
v3:element does not exist  
v4:element does not exist  
```  
  
 <span data-ttu-id="52357-130">Как правило, использование приведения для получения содержимого элементов и атрибутов позволяет создавать более простой код.</span><span class="sxs-lookup"><span data-stu-id="52357-130">In general, you can write simpler code when using casting to retrieve the contents of elements and attributes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52357-131">См. также</span><span class="sxs-lookup"><span data-stu-id="52357-131">See also</span></span>

- [<span data-ttu-id="52357-132">Оси LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="52357-132">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
