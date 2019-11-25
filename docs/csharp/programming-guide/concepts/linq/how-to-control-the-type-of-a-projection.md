---
title: Практическое руководство. Управление типом проекции (C#)
ms.date: 07/20/2015
ms.assetid: e4db6b7e-4cc9-4c8f-af85-94acf32aa348
ms.openlocfilehash: cb7c272fbe67c0700b5740691befc483993f4e29
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141349"
---
# <a name="how-to-control-the-type-of-a-projection-c"></a><span data-ttu-id="679a7-102">Практическое руководство. Управление типом проекции (C#)</span><span class="sxs-lookup"><span data-stu-id="679a7-102">How to control the type of a projection (C#)</span></span>
<span data-ttu-id="679a7-103">Проекция - это процесс, включающий выбор одного набора данных, его фильтрацию, изменение его формы и даже изменение его типа.</span><span class="sxs-lookup"><span data-stu-id="679a7-103">Projection is the process of taking one set of data, filtering it, changing its shape, and even changing its type.</span></span> <span data-ttu-id="679a7-104">Почти все выражения запросов выполняют операции проекции.</span><span class="sxs-lookup"><span data-stu-id="679a7-104">Most query expressions perform projections.</span></span> <span data-ttu-id="679a7-105">Результатом вычисления почти всех выражений, представленных в этом разделе, должен быть элемент <xref:System.Collections.Generic.IEnumerable%601> <xref:System.Xml.Linq.XElement>, но пользователь может управлять типом проекции для создания коллекций других типов.</span><span class="sxs-lookup"><span data-stu-id="679a7-105">Most of the query expressions shown in this section evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, but you can control the type of the projection to create collections of other types.</span></span> <span data-ttu-id="679a7-106">В настоящем разделе показано, как это делается.</span><span class="sxs-lookup"><span data-stu-id="679a7-106">This topic shows how to do this.</span></span>  
  
## <a name="example"></a><span data-ttu-id="679a7-107">Пример</span><span class="sxs-lookup"><span data-stu-id="679a7-107">Example</span></span>  
 <span data-ttu-id="679a7-108">В следующем примере определяется новый тип - `Customer`.</span><span class="sxs-lookup"><span data-stu-id="679a7-108">The following example defines a new type, `Customer`.</span></span> <span data-ttu-id="679a7-109">Затем выражение запроса создает новые экземпляры `Customer` в предложении `Select`.</span><span class="sxs-lookup"><span data-stu-id="679a7-109">The query expression then instantiates new `Customer` objects in the `Select` clause.</span></span> <span data-ttu-id="679a7-110">В результате тип выражения запроса определяется как <xref:System.Collections.Generic.IEnumerable%601> `Customer`.</span><span class="sxs-lookup"><span data-stu-id="679a7-110">This causes the type of the query expression to be <xref:System.Collections.Generic.IEnumerable%601> of `Customer`.</span></span>  
  
 <span data-ttu-id="679a7-111">В этом примере используется следующий XML-документ: [Пример XML-файла. Заказчики и заказы (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span><span class="sxs-lookup"><span data-stu-id="679a7-111">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
public class Customer  
{  
    private string customerID;  
    public string CustomerID{ get{return customerID;} set{customerID = value;}}  
  
    private string companyName;  
    public string CompanyName{ get{return companyName;} set{companyName = value;}}  
  
    private string contactName;  
    public string ContactName { get{return contactName;} set{contactName = value;}}  
  
    public Customer(string customerID, string companyName, string contactName)  
    {  
        CustomerID = customerID;  
        CompanyName = companyName;  
        ContactName = contactName;  
    }  
  
    public override string ToString()  
    {  
        return $"{this.customerID}:{this.companyName}:{this.contactName}";
    }  
}  
  
class Program  
{  
    static void Main(string[] args)  
    {  
        XElement custOrd = XElement.Load("CustomersOrders.xml");  
        IEnumerable<Customer> custList =  
            from el in custOrd.Element("Customers").Elements("Customer")  
            select new Customer(  
                (string)el.Attribute("CustomerID"),  
                (string)el.Element("CompanyName"),  
                (string)el.Element("ContactName")  
            );  
        foreach (Customer cust in custList)  
            Console.WriteLine(cust);  
    }  
}  
```  
  
 <span data-ttu-id="679a7-112">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="679a7-112">This code produces the following output:</span></span>  
  
```output  
GREAL:Great Lakes Food Market:Howard Snyder  
HUNGC:Hungry Coyote Import Store:Yoshi Latimer  
LAZYK:Lazy K Kountry Store:John Steel  
LETSS:Let's Stop N Shop:Jaime Yorres  
```  
  
## <a name="see-also"></a><span data-ttu-id="679a7-113">См. также</span><span class="sxs-lookup"><span data-stu-id="679a7-113">See also</span></span>

- <xref:System.Linq.Enumerable.Select%2A>
