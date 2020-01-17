---
title: Объединение двух коллекций (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 7b817ede-911a-4cff-9dd3-639c3fc228c9
ms.openlocfilehash: a5044778bbfd9529faf5fe63c72076f6a973c815
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345863"
---
# <a name="how-to-join-two-collections-linq-to-xml-c"></a><span data-ttu-id="24e0d-102">Объединение двух коллекций (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="24e0d-102">How to join two collections (LINQ to XML) (C#)</span></span>

<span data-ttu-id="24e0d-103">Элемент или атрибут в XML-документе может иногда относиться к другому элементу или атрибуту.</span><span class="sxs-lookup"><span data-stu-id="24e0d-103">An element or attribute in an XML document can sometimes refer to another element or attribute.</span></span> <span data-ttu-id="24e0d-104">Например, XML-документ из раздела [Пример XML-файла. Заказчики и заказы (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) содержит список заказчиков и список заказов.</span><span class="sxs-lookup"><span data-stu-id="24e0d-104">For example, the [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md) XML document contains a list of customers and a list of orders.</span></span> <span data-ttu-id="24e0d-105">Каждый элемент `Customer` содержит атрибут `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="24e0d-105">Each `Customer` element contains a `CustomerID` attribute.</span></span> <span data-ttu-id="24e0d-106">Каждый элемент `Order` содержит элемент `CustomerID`.</span><span class="sxs-lookup"><span data-stu-id="24e0d-106">Each `Order` element contains a `CustomerID` element.</span></span> <span data-ttu-id="24e0d-107">Элемент `CustomerID` для каждого заказа ссылается на атрибут `CustomerID`, присвоенный также и клиенту.</span><span class="sxs-lookup"><span data-stu-id="24e0d-107">The `CustomerID` element in each order refers to the `CustomerID` attribute in a customer.</span></span>

<span data-ttu-id="24e0d-108">Раздел [Пример XSD-файла. Заказчики и заказы](./sample-xsd-file-customers-and-orders1.md) содержит XSD-файл, с помощью которого можно проверить этот документ.</span><span class="sxs-lookup"><span data-stu-id="24e0d-108">The topic [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md) contains an XSD that can be used to validate this document.</span></span> <span data-ttu-id="24e0d-109">Здесь используются функции XSD `xs:key` и `xs:keyref` для установления того, что атрибут `CustomerID` элемента `Customer` является ключом, а также для установления связи между элементом `CustomerID` каждого из элементов `Order` и атрибутом `CustomerID` каждого из элементов `Customer`.</span><span class="sxs-lookup"><span data-stu-id="24e0d-109">It uses the `xs:key` and `xs:keyref` features of XSD to establish that the `CustomerID` attribute of the `Customer` element is a key, and to establish a relationship between the `CustomerID` element in each `Order` element and the `CustomerID` attribute in each `Customer` element.</span></span>

<span data-ttu-id="24e0d-110">В [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] можно воспользоваться преимуществами таких связей элементов и атрибутов при помощи предложения `join`.</span><span class="sxs-lookup"><span data-stu-id="24e0d-110">With [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can take advantage of this relationship by using the `join` clause.</span></span>

<span data-ttu-id="24e0d-111">Так как индекс недоступен, такое соединение будет негативно влиять на производительность среды.</span><span class="sxs-lookup"><span data-stu-id="24e0d-111">Because there is no index available, such joining will have poor run-time performance.</span></span>

<span data-ttu-id="24e0d-112">Более подробные сведения о функции `join` см. в разделе [Операции соединения (C#)](./join-operations.md).</span><span class="sxs-lookup"><span data-stu-id="24e0d-112">For more detailed information about `join`, see [Join Operations (C#)](./join-operations.md).</span></span>

## <a name="example"></a><span data-ttu-id="24e0d-113">Пример</span><span class="sxs-lookup"><span data-stu-id="24e0d-113">Example</span></span>

<span data-ttu-id="24e0d-114">В следующем примере выполняется соединение элементов `Customer` с элементами `Order` и создается новый XML-документ, который включает элемент `CompanyName` в заказы.</span><span class="sxs-lookup"><span data-stu-id="24e0d-114">The following example joins the `Customer` elements to the `Order` elements, and generates a new XML document that includes the `CompanyName` element in the orders.</span></span>

<span data-ttu-id="24e0d-115">Перед выполнением запроса в примере выполняется проверка созданного документа по схеме, приведенной в разделе [Пример XSD-файла. Заказчики и заказы](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="24e0d-115">Before executing the query, the example validates that the document complies with the schema in [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span> <span data-ttu-id="24e0d-116">Это позволяет обеспечить бесперебойную работу предложения соединения.</span><span class="sxs-lookup"><span data-stu-id="24e0d-116">This ensures that the join clause will always work.</span></span>

<span data-ttu-id="24e0d-117">В этом запросе сначала выполняется получение всех элементов `Customer`, а затем присоединение их к элементам `Order`.</span><span class="sxs-lookup"><span data-stu-id="24e0d-117">This query first retrieves all `Customer` elements, and then joins them to the `Order` elements.</span></span> <span data-ttu-id="24e0d-118">Он отбирает только заказы от клиентов со значением `CustomerID` больше «K».</span><span class="sxs-lookup"><span data-stu-id="24e0d-118">It selects only the orders for customers with a `CustomerID` greater than "K".</span></span> <span data-ttu-id="24e0d-119">После этого выполняется проецирование нового элемента `Order`, который содержит сведения о клиентах внутри каждого заказа.</span><span class="sxs-lookup"><span data-stu-id="24e0d-119">It then projects a new `Order` element that contains the customer information within each order.</span></span>

<span data-ttu-id="24e0d-120">В этом примере используется следующий XML-документ: [Пример XML-файла. Заказчики и заказы (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="24e0d-120">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>

<span data-ttu-id="24e0d-121">В этом примере используется следующая XSD-схема: [Пример XSD-файла. Заказчики и заказы](./sample-xsd-file-customers-and-orders1.md).</span><span class="sxs-lookup"><span data-stu-id="24e0d-121">This example uses the following XSD schema: [Sample XSD File: Customers and Orders](./sample-xsd-file-customers-and-orders1.md).</span></span>

<span data-ttu-id="24e0d-122">Такое соединение не будет работать оптимально.</span><span class="sxs-lookup"><span data-stu-id="24e0d-122">Joining in this fashion will not perform well.</span></span> <span data-ttu-id="24e0d-123">Соединение осуществляется путем линейного поиска.</span><span class="sxs-lookup"><span data-stu-id="24e0d-123">Joins are performed via a linear search.</span></span> <span data-ttu-id="24e0d-124">Не используются хэш-таблицы и индексы, которые могли бы помочь оптимизировать производительность.</span><span class="sxs-lookup"><span data-stu-id="24e0d-124">There are no hash tables or indexes to help with performance.</span></span>

```csharp
XmlSchemaSet schemas = new XmlSchemaSet();
schemas.Add("", "CustomersOrders.xsd");

Console.Write("Attempting to validate, ");
XDocument custOrdDoc = XDocument.Load("CustomersOrders.xml");

bool errors = false;
custOrdDoc.Validate(schemas, (o, e) =>
                     {
                         Console.WriteLine("{0}", e.Message);
                         errors = true;
                     });
Console.WriteLine("custOrdDoc {0}", errors ? "did not validate" : "validated");

if (!errors)
{
    // Join customers and orders, and create a new XML document with
    // a different shape.

    // The new document contains orders only for customers with a
    // CustomerID > 'K'
    XElement custOrd = custOrdDoc.Element("Root");
    XElement newCustOrd = new XElement("Root",
        from c in custOrd.Element("Customers").Elements("Customer")
        join o in custOrd.Element("Orders").Elements("Order")
                   on (string)c.Attribute("CustomerID") equals
                      (string)o.Element("CustomerID")
        where ((string)c.Attribute("CustomerID")).CompareTo("K") > 0
        select new XElement("Order",
            new XElement("CustomerID", (string)c.Attribute("CustomerID")),
            new XElement("CompanyName", (string)c.Element("CompanyName")),
            new XElement("ContactName", (string)c.Element("ContactName")),
            new XElement("EmployeeID", (string)o.Element("EmployeeID")),
            new XElement("OrderDate", (DateTime)o.Element("OrderDate"))
        )
    );
    Console.WriteLine(newCustOrd);
}
```

<span data-ttu-id="24e0d-125">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="24e0d-125">This code produces the following output:</span></span>

```output
Attempting to validate, custOrdDoc validated
<Root>
  <Order>
    <CustomerID>LAZYK</CustomerID>
    <CompanyName>Lazy K Kountry Store</CompanyName>
    <ContactName>John Steel</ContactName>
    <EmployeeID>1</EmployeeID>
    <OrderDate>1997-03-21T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LAZYK</CustomerID>
    <CompanyName>Lazy K Kountry Store</CompanyName>
    <ContactName>John Steel</ContactName>
    <EmployeeID>8</EmployeeID>
    <OrderDate>1997-05-22T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>1</EmployeeID>
    <OrderDate>1997-06-25T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>8</EmployeeID>
    <OrderDate>1997-10-27T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>6</EmployeeID>
    <OrderDate>1997-11-10T00:00:00</OrderDate>
  </Order>
  <Order>
    <CustomerID>LETSS</CustomerID>
    <CompanyName>Let's Stop N Shop</CompanyName>
    <ContactName>Jaime Yorres</ContactName>
    <EmployeeID>4</EmployeeID>
    <OrderDate>1998-02-12T00:00:00</OrderDate>
  </Order>
</Root>
```
