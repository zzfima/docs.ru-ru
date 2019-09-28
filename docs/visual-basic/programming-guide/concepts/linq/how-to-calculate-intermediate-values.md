---
title: Практическое руководство. Вычислить промежуточные значения (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 933a97b2-dfe7-4f4d-94ad-e6e20df84abd
ms.openlocfilehash: 63067c42da37d71ad0fc5488c68d296ac7589aec
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/27/2019
ms.locfileid: "71352910"
---
# <a name="how-to-calculate-intermediate-values-visual-basic"></a><span data-ttu-id="3ae96-102">Практическое руководство. Вычислить промежуточные значения (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ae96-102">How to: Calculate Intermediate Values (Visual Basic)</span></span>
<span data-ttu-id="3ae96-103">В этом примере показано, как вычислять промежуточные значения, которые используются в сортировке, фильтрации и выборке.</span><span class="sxs-lookup"><span data-stu-id="3ae96-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3ae96-104">Пример</span><span class="sxs-lookup"><span data-stu-id="3ae96-104">Example</span></span>  
 <span data-ttu-id="3ae96-105">В следующем примере используется предложение `Let`.</span><span class="sxs-lookup"><span data-stu-id="3ae96-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="3ae96-106">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3ae96-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim extensions As IEnumerable(Of Decimal) = _  
    From el In root.<Data> _  
    Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
    Where extension > 25 _  
    Order By extension _  
    Select extension  
For Each ex As Decimal In extensions  
    Console.WriteLine(ex)  
Next  
```  
  
 <span data-ttu-id="3ae96-107">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="3ae96-107">This code produces the following output:</span></span>  
  
```console  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="3ae96-108">Пример</span><span class="sxs-lookup"><span data-stu-id="3ae96-108">Example</span></span>  
 <span data-ttu-id="3ae96-109">Следующий пример демонстрирует тот же запрос XML, что и в пространстве имен.</span><span class="sxs-lookup"><span data-stu-id="3ae96-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="3ae96-110">Дополнительные сведения см. в разделе [Общие сведения о пространствах имен (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="3ae96-110">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="3ae96-111">В этом примере используется следующий XML-документ: [Пример XML-файла. Числовые данные в пространстве имен](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span><span class="sxs-lookup"><span data-stu-id="3ae96-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns="http://www.adatum.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("DataInNamespace.xml")  
        Dim extensions As IEnumerable(Of Decimal) = _  
            From el In root.<Data> _  
            Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
            Where extension > 25 _  
            Order By extension _  
            Select extension  
        For Each ex As Decimal In extensions  
            Console.WriteLine(ex)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="3ae96-112">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="3ae96-112">This code produces the following output:</span></span>  
  
```console  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="3ae96-113">См. также</span><span class="sxs-lookup"><span data-stu-id="3ae96-113">See also</span></span>

- [<span data-ttu-id="3ae96-114">Основные запросы (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3ae96-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
