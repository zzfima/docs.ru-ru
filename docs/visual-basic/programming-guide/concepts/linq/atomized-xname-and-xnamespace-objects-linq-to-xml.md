---
title: "Атомизация объекты XName и XNamespace (LINQ to XML) (Visual Basic) | Документы Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 21ee7585-7df9-40b4-8c76-a12bb5f29bb3
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 1303d0be3715bb6462ef28b1b2286b999661d240
ms.contentlocale: ru-ru
ms.lasthandoff: 06/01/2017


---
# <a name="atomized-xname-and-xnamespace-objects-linq-to-xml-visual-basic"></a><span data-ttu-id="5a325-102">Атомизация объекты XName и XNamespace (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a325-102">Atomized XName and XNamespace Objects (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="5a325-103"><xref:System.Xml.Linq.XName>и <xref:System.Xml.Linq.XNamespace>объекты *атомизация*; то есть, если они имеют идентичное полное имя, они ссылаются на один объект.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5a325-103"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> objects are *atomized*; that is, if they contain the same qualified name, they refer to the same object.</span></span> <span data-ttu-id="5a325-104">Это способствует повышению производительности при выполнении запросов: при сравнении двух атомарных имен для проверки их равенства соответствующий промежуточный язык должен определить, ссылаются ли они на один и тот же объект.</span><span class="sxs-lookup"><span data-stu-id="5a325-104">This yields performance benefits for queries: When you compare two atomized names for equality, the underlying intermediate language only has to determine whether the two references point to the same object.</span></span> <span data-ttu-id="5a325-105">Эта операция используется в промежуточном коде вместо более длительной операции сравнения строк.</span><span class="sxs-lookup"><span data-stu-id="5a325-105">The underlying code does not have to do string comparisons, which would be time consuming.</span></span>  
  
## <a name="atomization-semantics"></a><span data-ttu-id="5a325-106">Семантика атомизации</span><span class="sxs-lookup"><span data-stu-id="5a325-106">Atomization Semantics</span></span>  
 <span data-ttu-id="5a325-107">Атомизация означает, что если два <xref:System.Xml.Linq.XName>объекты имеют одинаковое локальное имя и они находятся в том же пространстве имен, они совместно используют тот же экземпляр.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5a325-107">Atomization means that if two <xref:System.Xml.Linq.XName> objects have the same local name, and they are in the same namespace, they share the same instance.</span></span> <span data-ttu-id="5a325-108">Таким же образом, если два <xref:System.Xml.Linq.XNamespace>объекты имеют то же пространство имен URI, совместно используют тот же экземпляр.</xref:System.Xml.Linq.XNamespace></span><span class="sxs-lookup"><span data-stu-id="5a325-108">In the same way, if two <xref:System.Xml.Linq.XNamespace> objects have the same namespace URI, they share the same instance.</span></span>  
  
 <span data-ttu-id="5a325-109">Чтобы разрешить создание атомарных объектов класса, необходимо, чтобы конструктор класса был закрытым, а не открытым.</span><span class="sxs-lookup"><span data-stu-id="5a325-109">For a class to enable atomized objects, the constructor for the class must be private, not public.</span></span> <span data-ttu-id="5a325-110">Это требование основано на том, что если бы конструктор был открытым, можно было бы создавать неатомарные объекты.</span><span class="sxs-lookup"><span data-stu-id="5a325-110">This is because if the constructor were public, you could create a non-atomized object.</span></span> <span data-ttu-id="5a325-111"><xref:System.Xml.Linq.XName>И <xref:System.Xml.Linq.XNamespace>классы реализуют неявный оператор преобразования для преобразования строки в <xref:System.Xml.Linq.XName>или <xref:System.Xml.Linq.XNamespace>.</xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName> </xref:System.Xml.Linq.XNamespace> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5a325-111">The <xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> classes implement an implicit conversion operator to convert a string into an <xref:System.Xml.Linq.XName> or <xref:System.Xml.Linq.XNamespace>.</span></span> <span data-ttu-id="5a325-112">Экземпляры этих объектов могут быть получены только таким способом.</span><span class="sxs-lookup"><span data-stu-id="5a325-112">This is how you get an instance of these objects.</span></span> <span data-ttu-id="5a325-113">Создание экземпляров с помощью конструктора невозможно, так как конструктор недоступен.</span><span class="sxs-lookup"><span data-stu-id="5a325-113">You cannot get an instance by using a constructor, because the constructor is inaccessible.</span></span>  
  
 <span data-ttu-id="5a325-114"><xref:System.Xml.Linq.XName>и <xref:System.Xml.Linq.XNamespace>также реализуют операторы равенства и неравенства, определяющие ли два сравниваемых являются ссылками на том же экземпляре.</xref:System.Xml.Linq.XNamespace></xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5a325-114"><xref:System.Xml.Linq.XName> and <xref:System.Xml.Linq.XNamespace> also implement the equality and inequality operators, to determine whether the two objects being compared are references to the same instance.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5a325-115">Пример</span><span class="sxs-lookup"><span data-stu-id="5a325-115">Example</span></span>  
 <span data-ttu-id="5a325-116">Следующий код создает <xref:System.Xml.Linq.XElement>объектов и демонстрирует, что идентичные имена совместно используют тот же экземпляр.</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="5a325-116">The following code creates some <xref:System.Xml.Linq.XElement> objects and demonstrates that identical names share the same instance.</span></span>  
  
```vb  
Dim r1 As New XElement("Root", "data1")  
Dim r2 As XElement = XElement.Parse("<Root>data2</Root>")  
  
If DirectCast(r1.Name, Object) = DirectCast(r2.Name, Object) Then  
    Console.WriteLine("r1 and r2 have names that refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
  
Dim n As XName = "Root"  
  
If DirectCast(n, Object) = DirectCast(r1.Name, Object) Then  
    Console.WriteLine("The name of r1 and the name in 'n' refer to the same instance.")  
Else  
    Console.WriteLine("Different")  
End If  
```  
  
 <span data-ttu-id="5a325-117">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="5a325-117">This example produces the following output:</span></span>  
  
```  
r1 and r2 have names that refer to the same instance.  
The name of r1 and the name in 'n' refer to the same instance.  
```  
  
 <span data-ttu-id="5a325-118">Как упоминалось выше, преимущество атомарных объектов заключается в, при использовании одного из методов оси, принимающих <xref:System.Xml.Linq.XName>как параметр метода оси должен определить, что два имени ссылки один и тот же экземпляр для выбора необходимых элементов.</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5a325-118">As mentioned earlier, the benefit of atomized objects is that when you use one of the axis methods that take an <xref:System.Xml.Linq.XName> as a parameter, the axis method only has to determine that two names reference the same instance to select the desired elements.</span></span>  
  
 <span data-ttu-id="5a325-119">В следующем примере передается <xref:System.Xml.Linq.XName>для <xref:System.Xml.Linq.XContainer.Descendants%2A>вызова метода, для которого производительность за счет атомизации.</xref:System.Xml.Linq.XContainer.Descendants%2A> </xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="5a325-119">The following example passes an <xref:System.Xml.Linq.XName> to the <xref:System.Xml.Linq.XContainer.Descendants%2A> method call, which then has better performance because of the atomization pattern.</span></span>  
  
```vb  
Dim root As New XElement("Root", New XElement("C1", 1), New XElement("Z1", New XElement("C1", 2), New XElement("C1", 1)))  
  
Dim query = From e In root.Descendants("C1") Where CInt(e) = 1e  
  
For Each z As var In query  
    Console.WriteLine(z)  
Next  
```  
  
 <span data-ttu-id="5a325-120">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="5a325-120">This example produces the following output:</span></span>  
  
```xml  
<C1>1</C1>  
<C1>1</C1>  
```  
  
## <a name="see-also"></a><span data-ttu-id="5a325-121">См. также</span><span class="sxs-lookup"><span data-stu-id="5a325-121">See Also</span></span>  
 [<span data-ttu-id="5a325-122">Производительность (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5a325-122">Performance (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/performance-linq-to-xml.md)

