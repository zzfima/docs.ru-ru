---
title: "Практическое руководство. Проецирование анонимного типа (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 5cb9be13-5ac4-4373-a034-b3520a5b2dec
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 31e0b9c5714c2365323d8c8f65659ee1b1ef5e2b
ms.contentlocale: ru-ru
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-project-an-anonymous-type-c"></a><span data-ttu-id="2b172-102">Практическое руководство. Проецирование анонимного типа (C#)</span><span class="sxs-lookup"><span data-stu-id="2b172-102">How to: Project an Anonymous Type (C#)</span></span>
<span data-ttu-id="2b172-103">В некоторых случаях может потребоваться проецировать запрос на новый тип, даже если известно, что этот тип будет использоваться недолго.</span><span class="sxs-lookup"><span data-stu-id="2b172-103">In some cases you might want to project a query to a new type, even though you know you will only use this type for a short while.</span></span> <span data-ttu-id="2b172-104">Создание нового типа для использования в проекции требует много дополнительной работы.</span><span class="sxs-lookup"><span data-stu-id="2b172-104">It is a lot of extra work to create a new type just to use in the projection.</span></span> <span data-ttu-id="2b172-105">Гораздо более эффективный подход заключается в проецировании на анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="2b172-105">A more efficient approach in this case is to project to an anonymous type.</span></span> <span data-ttu-id="2b172-106">Анонимные типы позволяют определять класс и инициализировать его объект, не присваивая имя этому классу.</span><span class="sxs-lookup"><span data-stu-id="2b172-106">Anonymous types allow you to define a class, then declare and initialize an object of that class, without giving the class a name.</span></span>  
  
 <span data-ttu-id="2b172-107">Анонимные типы являются реализацией в языке C# математического понятия *кортежа*.</span><span class="sxs-lookup"><span data-stu-id="2b172-107">Anonymous types are the C# implementation of the mathematical concept of a *tuple*.</span></span> <span data-ttu-id="2b172-108">Математический термин «кортеж» обозначает одноэлементные, двухэлементные, трехэлементные, четырехэлементные, пятиэлементные и n-элементные последовательности.</span><span class="sxs-lookup"><span data-stu-id="2b172-108">The mathematical term tuple originated from the sequence single, double, triple, quadruple, quintuple, n-tuple.</span></span> <span data-ttu-id="2b172-109">Он относится к конечной последовательности объектов, каждый из которых имеет конкретный тип.</span><span class="sxs-lookup"><span data-stu-id="2b172-109">It refers to a finite sequence of objects, each of a specific type.</span></span> <span data-ttu-id="2b172-110">Иногда такую последовательность называют списком пар «имя/значение».</span><span class="sxs-lookup"><span data-stu-id="2b172-110">Sometimes this is called a list of name/value pairs.</span></span> <span data-ttu-id="2b172-111">Например, содержимое адреса в XML-документе [Пример XML-файла. Стандартный заказ на покупку (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md) можно представить следующим образом.</span><span class="sxs-lookup"><span data-stu-id="2b172-111">For example, the contents of an address in the [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md) XML document could be expressed as follows:</span></span>  
  
```  
Name: Ellen Adams  
Street: 123 Maple Street  
City: Mill Valley  
State: CA  
Zip: 90952  
Country: USA  
```  
  
 <span data-ttu-id="2b172-112">Создание экземпляра анонимного типа удобно трактовать как создание n-элементного кортежа.</span><span class="sxs-lookup"><span data-stu-id="2b172-112">When you create an instance of an anonymous type, it is convenient to think of it as creating a tuple of order n.</span></span> <span data-ttu-id="2b172-113">При написании запроса, создающего кортеж в предложении `select`, запрос возвращает объект `IEnumerable` кортежа.</span><span class="sxs-lookup"><span data-stu-id="2b172-113">If you write a query that creates a tuple in the `select` clause, the query returns an `IEnumerable` of the tuple.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b172-114">Пример</span><span class="sxs-lookup"><span data-stu-id="2b172-114">Example</span></span>  
 <span data-ttu-id="2b172-115">В этом примере предложение `select` проецирует анонимный тип.</span><span class="sxs-lookup"><span data-stu-id="2b172-115">In this example, the `select` clause projects an anonymous type.</span></span> <span data-ttu-id="2b172-116">Затем в этом примере используется тип `var` для создания объекта `IEnumerable`.</span><span class="sxs-lookup"><span data-stu-id="2b172-116">The example then uses `var` to create the `IEnumerable` object.</span></span> <span data-ttu-id="2b172-117">В цикле `foreach` переменная итерации становится экземпляром анонимного типа, созданного в выражении запроса.</span><span class="sxs-lookup"><span data-stu-id="2b172-117">Within the `foreach` loop, the iteration variable becomes an instance of the anonymous type created in the query expression.</span></span>  
  
 <span data-ttu-id="2b172-118">В этом примере используется следующий XML-документ: [Пример XML-файла. Клиенты и заказы (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="2b172-118">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement custOrd = XElement.Load("CustomersOrders.xml");  
var custList =  
    from el in custOrd.Element("Customers").Elements("Customer")  
    select new {  
        CustomerID = (string)el.Attribute("CustomerID"),  
        CompanyName = (string)el.Element("CompanyName"),  
        ContactName = (string)el.Element("ContactName")  
    };  
foreach (var cust in custList)  
    Console.WriteLine("{0}:{1}:{2}", cust.CustomerID, cust.CompanyName, cust.ContactName);  
```  
  
 <span data-ttu-id="2b172-119">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="2b172-119">This code produces the following output:</span></span>  
  
```  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b172-120">См. также</span><span class="sxs-lookup"><span data-stu-id="2b172-120">See Also</span></span>  
 [<span data-ttu-id="2b172-121">Проекции и преобразования (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2b172-121">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)

