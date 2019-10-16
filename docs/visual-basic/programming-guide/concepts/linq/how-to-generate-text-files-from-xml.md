---
title: Как создавать текстовые файлы из XML (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 3b33f191-4abe-4419-b81b-3cb81d9a317f
ms.openlocfilehash: 1b383a0f3656558286bfe449ed72c633426b9410
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "72320538"
---
# <a name="how-to-generate-text-files-from-xml-visual-basic"></a><span data-ttu-id="e03c3-102">Как создавать текстовые файлы из XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e03c3-102">How to: Generate Text Files from XML (Visual Basic)</span></span>
<span data-ttu-id="e03c3-103">В этом примере показано, как создавать файл с разделителями-запятыми (csv) из XML-файла.</span><span class="sxs-lookup"><span data-stu-id="e03c3-103">This example shows how to generate a comma-separated values (CSV) file from an XML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e03c3-104">Пример</span><span class="sxs-lookup"><span data-stu-id="e03c3-104">Example</span></span>  
 <span data-ttu-id="e03c3-105">Версия Visual Basic использует процедурный код для статистической обработки коллекции строк в одной строке.</span><span class="sxs-lookup"><span data-stu-id="e03c3-105">The Visual Basic version uses procedural code to aggregate the collection of strings into a single string.</span></span>  
  
 <span data-ttu-id="e03c3-106">В этом примере используется следующий XML-документ: [Пример XML-файла. Клиенты и заказы (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e03c3-106">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim custOrd As XElement = XElement.Load("CustomersOrders.xml")  
Dim strCollection As IEnumerable(Of String) = _  
    From el In custOrd.<Customers>.<Customer> _  
    Select _  
        String.Format("{0},{1},{2},{3},{4},{5},{6},{7},{8},{9}{10}", _  
            el.@CustomerID, _  
            el.<CompanyName>.Value, _  
            el.<ContactName>.Value, _  
            el.<ContactTitle>.Value, _  
            el.<Phone>.Value, _  
            el.<FullAddress>.<Address>.Value, _  
            el.<FullAddress>.<City>.Value, _  
            el.<FullAddress>.<Region>.Value, _  
            el.<FullAddress>.<PostalCode>.Value, _  
            el.<FullAddress>.<Country>.Value, _  
            Environment.NewLine _  
        )  
Dim sb As StringBuilder = New StringBuilder()  
For Each str As String In strCollection  
    sb.Append(str)  
Next  
Console.WriteLine(sb.ToString())  
```  
  
 <span data-ttu-id="e03c3-107">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="e03c3-107">This code produces the following output:</span></span>  
  
```console  
GREAL,Great Lakes Food Market,Howard Snyder,Marketing Manager,(503) 555-7555,2732 Baker Blvd.,Eugene,OR,97403,USA  
HUNGC,Hungry Coyote Import Store,Yoshi Latimer,Sales Representative,(503) 555-6874,City Center Plaza 516 Main St.,Elgin,OR,97827,USA  
LAZYK,Lazy K Kountry Store,John Steel,Marketing Manager,(509) 555-7969,12 Orchestra Terrace,Walla Walla,WA,99362,USA  
LETSS,Let's Stop N Shop,Jaime Yorres,Owner,(415) 555-5938,87 Polk St. Suite 5,San Francisco,CA,94117,USA  
```  
  
## <a name="see-also"></a><span data-ttu-id="e03c3-108">См. также</span><span class="sxs-lookup"><span data-stu-id="e03c3-108">See also</span></span>

- [<span data-ttu-id="e03c3-109">Проекции и преобразования (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e03c3-109">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
