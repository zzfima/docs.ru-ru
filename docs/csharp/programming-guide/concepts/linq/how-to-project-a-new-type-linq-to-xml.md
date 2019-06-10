---
title: Практическое руководство. Проецирование нового типа (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 70053a2457005f6751075b33e8e49851d7127446
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486586"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="92f28-102">Практическое руководство. Проецирование нового типа (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="92f28-102">How to: Project a New Type (LINQ to XML) (C#)</span></span>
<span data-ttu-id="92f28-103">В других примерах данного раздела показаны запросы, возвращающие результаты в виде значений <xref:System.Collections.Generic.IEnumerable%601> типа <xref:System.Xml.Linq.XElement>, значений <xref:System.Collections.Generic.IEnumerable%601> типа `string` и значений <xref:System.Collections.Generic.IEnumerable%601> типа `int`.</span><span class="sxs-lookup"><span data-stu-id="92f28-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="92f28-104">Это наиболее распространенные типы результатов, но подходят не для всех сценариев.</span><span class="sxs-lookup"><span data-stu-id="92f28-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="92f28-105">Во многих случаях требуется, чтобы запросы возвращали <xref:System.Collections.Generic.IEnumerable%601> какого-то другого типа.</span><span class="sxs-lookup"><span data-stu-id="92f28-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="92f28-106">Пример</span><span class="sxs-lookup"><span data-stu-id="92f28-106">Example</span></span>  
 <span data-ttu-id="92f28-107">В данном примере показано, как создавать экземпляры объектов в предложении `select`.</span><span class="sxs-lookup"><span data-stu-id="92f28-107">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="92f28-108">Сначала в коде определяется новый класс с помощью конструктора, а затем модифицируется инструкция `select`, чтобы это выражение представляло новый экземпляр нового класса.</span><span class="sxs-lookup"><span data-stu-id="92f28-108">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>  
  
 <span data-ttu-id="92f28-109">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="92f28-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
class NameQty {  
    public string name;  
    public int qty;  
    public NameQty(string n, int q)  
    {  
        name = n;  
        qty = q;  
    }  
};  
  
class Program {  
    public static void Main() {  
        XElement po = XElement.Load("PurchaseOrder.xml");  
  
        IEnumerable<NameQty> nqList =  
            from n in po.Descendants("Item")  
            select new NameQty(  
                    (string)n.Element("ProductName"),  
                    (int)n.Element("Quantity")  
                );  
  
        foreach (NameQty n in nqList)  
            Console.WriteLine(n.name + ":" + n.qty);  
    }  
}  
```  
  
 <span data-ttu-id="92f28-110">В данном примере используется метод `M:System.Xml.Linq.XElement.Element`, представленный в разделе [Практическое руководство. Извлечение одного дочернего элемента (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="92f28-110">This example uses the `M:System.Xml.Linq.XElement.Element` method that was introduced in the topic [How to: Retrieve a Single Child Element (LINQ to XML) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="92f28-111">В нем также используется приведение для получения значений элементов, возвращаемых методом `M:System.Xml.Linq.XElement.Element`.</span><span class="sxs-lookup"><span data-stu-id="92f28-111">It also uses casts to retrieve the values of the elements that are returned by the `M:System.Xml.Linq.XElement.Element` method.</span></span>  
  
 <span data-ttu-id="92f28-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="92f28-112">This example produces the following output:</span></span>  
  
```  
Lawnmower:1  
Baby Monitor:2  
```  
  