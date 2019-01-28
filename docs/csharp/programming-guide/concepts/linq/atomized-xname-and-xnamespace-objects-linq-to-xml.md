---
title: Атомарные объекты XName и XNamespace (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: a5b21433-b49d-415c-b00e-bcbfb0d267d7
ms.openlocfilehash: ff5677e84d0a4401c9d3ce8c43e7743385cdd432
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557868"
---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-c"></a><span data-ttu-id="af724-102">Атомарные объекты XName и XNamespace (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="af724-102">Atomized XName and XNamespace Objects (LINQ to XML) (C#)</span></span>
<span data-ttu-id="af724-103">Объекты <xref:System.Xml.Linq.XName> и <xref:System.Xml.Linq.XNamespace> являются *атомарными*; иными словами, если они имеют идентичное полное имя, они ссылаются на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="af724-103"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> objects are *atomized*; that is, if they contain the same qualified name, they refer to the same object.</span></span> <span data-ttu-id="af724-104">Это способствует повышению производительности при использовании запросов. При сравнении двух атомарных имен для проверки их равенства соответствующий промежуточный язык должен определить, ссылаются ли они на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="af724-104">This yields performance benefits for queries: When you compare two atomized names for equality, the underlying intermediate language only has to determine whether the two references point to the same object.</span></span> <span data-ttu-id="af724-105">Эта операция используется в промежуточном коде вместо более длительной операции сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="af724-105">The underlying code does not have to do string comparisons, which would be time consuming.</span></span>  
  
## <a name="atomization-semantics"></a><span data-ttu-id="af724-106">Семантика атомизации</span><span class="sxs-lookup"><span data-stu-id="af724-106">Atomization Semantics</span></span>  
 <span data-ttu-id="af724-107">Атомизация означает, что два объекта <xref:System.Xml.Linq.XName> имеющие идентичное локальное имя и находящиеся в одном пространстве имен, совместно используют один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="af724-107">Atomization means that if two <xref:System.Xml.Linq.XName> objects have the same local name, and they are in the same namespace, they share the same instance.</span></span> <span data-ttu-id="af724-108">Аналогично, если два объекта <xref:System.Xml.Linq.XNamespace> имеют идентичный идентификатор URI пространства имен, то они совместно используют один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="af724-108">In the same way, if two <xref:System.Xml.Linq.XNamespace> objects have the same namespace URI, they share the same instance.</span></span>  
  
 <span data-ttu-id="af724-109">Чтобы разрешить создание атомарных объектов класса, необходимо, чтобы конструктор класса был закрытым, а не открытым.</span><span class="sxs-lookup"><span data-stu-id="af724-109">For a class to enable atomized objects, the constructor for the class must be private, not public.</span></span> <span data-ttu-id="af724-110">Это требование основано на том, что если бы конструктор был открытым, можно было бы создавать неатомарные объекты.</span><span class="sxs-lookup"><span data-stu-id="af724-110">This is because if the constructor were public, you could create a non-atomized object.</span></span> <span data-ttu-id="af724-111">Классы <xref:System.Xml.Linq.XName> и <xref:System.Xml.Linq.XNamespace> реализуют неявный оператор преобразования строки в объект <xref:System.Xml.Linq.XName> или <xref:System.Xml.Linq.XNamespace>.</span><span class="sxs-lookup"><span data-stu-id="af724-111">The <xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> classes implement an implicit conversion operator to convert a string into an <xref:System.Xml.Linq.XName> or <xref:System.Xml.Linq.XNamespace>.</span></span> <span data-ttu-id="af724-112">Экземпляры этих объектов могут быть получены только таким способом.</span><span class="sxs-lookup"><span data-stu-id="af724-112">This is how you get an instance of these objects.</span></span> <span data-ttu-id="af724-113">Создание экземпляров с помощью конструктора невозможно, так как конструктор недоступен.</span><span class="sxs-lookup"><span data-stu-id="af724-113">You cannot get an instance by using a constructor, because the constructor is inaccessible.</span></span>  
  
 <span data-ttu-id="af724-114">Классы <xref:System.Xml.Linq.XName> и<xref:System.Xml.Linq.XNamespace> также реализуют операторы для проверки равенства и неравенства, определяющие, ссылаются ли два сравниваемых объекта на один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="af724-114"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> also implement the equality and inequality operators, to determine whether the two objects being compared are references to the same instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="af724-115">Пример</span><span class="sxs-lookup"><span data-stu-id="af724-115">Example</span></span>  
 <span data-ttu-id="af724-116">Следующий код создает объекты <xref:System.Xml.Linq.XElement> и демонстрирует, что идентичные имена совместно используют один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="af724-116">The following code creates some <xref:System.Xml.Linq.XElement> objects and demonstrates that identical names share the same instance.</span></span>  
  
```csharp  
XElement r1 = new XElement("Root", "data1");  
XElement r2 = XElement.Parse("<Root>data2</Root>");  
  
if ((object)r1.Name == (object)r2.Name)  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.");  
else  
    Console.WriteLine("Different");  
  
XName n = "Root";  
  
if ((object)n == (object)r1.Name)  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.");  
else  
    Console.WriteLine("Different");  
```  
  
 <span data-ttu-id="af724-117">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="af724-117">This example produces the following output:</span></span>  
  
```  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 <span data-ttu-id="af724-118">Как отмечалось выше, преимущество атомарных объектов заключается в том, что при использовании одного из методов оси, принимающих в качестве параметра <xref:System.Xml.Linq.XName>, этому методу оси для выбора необходимых элементов достаточно определить, что два имени совместно используют один и тот же экземпляр.</span><span class="sxs-lookup"><span data-stu-id="af724-118">As mentioned earlier, the benefit of atomized objects is that when you use one of the axis methods that take an <xref:System.Xml.Linq.XName> as a parameter, the axis method only has to determine that two names reference the same instance to select the desired elements.</span></span>  
  
 <span data-ttu-id="af724-119">В следующем примере объект <xref:System.Xml.Linq.XName> передается при вызове метода <xref:System.Xml.Linq.XContainer.Descendants%2A>, производительность которого выше за счет использования атомизации.</span><span class="sxs-lookup"><span data-stu-id="af724-119">The following example passes an <xref:System.Xml.Linq.XName> to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method call, which then has better performance because of the atomization pattern.</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("C1", 1),  
    new XElement("Z1",  
        new XElement("C1", 2),  
        new XElement("C1", 1)  
    )  
);  
  
var query = from e in root.Descendants("C1")  
            where (int)e == 1  
            select e;  
  
foreach (var z in query)  
    Console.WriteLine(z);  
```  
  
 <span data-ttu-id="af724-120">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="af724-120">This example produces the following output:</span></span>  
  
```xml  
<C1>1</C1>  
<C1>1</C1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="af724-121">См. также</span><span class="sxs-lookup"><span data-stu-id="af724-121">See also</span></span>

- [<span data-ttu-id="af724-122">Производительность (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="af724-122">Performance (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/performance-linq-to-xml.md)
