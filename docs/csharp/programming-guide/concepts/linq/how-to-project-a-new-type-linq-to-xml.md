---
title: Как проецировать новый тип (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 48145cf9-1e0b-4e73-bbfd-28fc04800dc4
ms.openlocfilehash: 3a54677fa0fa2845dd635f89ddb7ed1c5c279e03
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/25/2019
ms.locfileid: "75345720"
---
# <a name="how-to-project-a-new-type-linq-to-xml-c"></a><span data-ttu-id="e857a-102">Как проецировать новый тип (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="e857a-102">How to project a new type (LINQ to XML) (C#)</span></span>

<span data-ttu-id="e857a-103">В других примерах данного раздела показаны запросы, возвращающие результаты в виде значений <xref:System.Collections.Generic.IEnumerable%601> типа <xref:System.Xml.Linq.XElement>, значений <xref:System.Collections.Generic.IEnumerable%601> типа `string` и значений <xref:System.Collections.Generic.IEnumerable%601> типа `int`.</span><span class="sxs-lookup"><span data-stu-id="e857a-103">Other examples in this section have shown queries that return results as <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement>, <xref:System.Collections.Generic.IEnumerable%601> of `string`, and <xref:System.Collections.Generic.IEnumerable%601> of `int`.</span></span> <span data-ttu-id="e857a-104">Это наиболее распространенные типы результатов, но подходят не для всех сценариев.</span><span class="sxs-lookup"><span data-stu-id="e857a-104">These are common result types, but they are not appropriate for every scenario.</span></span> <span data-ttu-id="e857a-105">Во многих случаях требуется, чтобы запросы возвращали <xref:System.Collections.Generic.IEnumerable%601> какого-то другого типа.</span><span class="sxs-lookup"><span data-stu-id="e857a-105">In many cases you will want your queries to return an <xref:System.Collections.Generic.IEnumerable%601> of some other type.</span></span>

## <a name="example"></a><span data-ttu-id="e857a-106">Пример</span><span class="sxs-lookup"><span data-stu-id="e857a-106">Example</span></span>

<span data-ttu-id="e857a-107">В данном примере показано, как создавать экземпляры объектов в предложении `select`.</span><span class="sxs-lookup"><span data-stu-id="e857a-107">This example shows how to instantiate objects in the `select` clause.</span></span> <span data-ttu-id="e857a-108">Сначала в коде определяется новый класс с помощью конструктора, а затем модифицируется инструкция `select`, чтобы это выражение представляло новый экземпляр нового класса.</span><span class="sxs-lookup"><span data-stu-id="e857a-108">The code first defines a new class with a constructor, and then modifies the `select` statement so that the expression is a new instance of the new class.</span></span>

<span data-ttu-id="e857a-109">В этом примере используется следующий XML-документ: [Пример XML-файла. Типичный заказ на покупку (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span><span class="sxs-lookup"><span data-stu-id="e857a-109">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>

```csharp
class NameQty 
{
    public string name;
    public int qty;
    public NameQty(string n, int q)
    {
        name = n;
        qty = q; 
    }
};

class Program {
    public static void Main() 
    {
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

<span data-ttu-id="e857a-110">В этом примере используется метод <xref:System.Xml.Linq.XContainer.Element%2A>, который был представлен в руководстве по [извлечению одного дочернего элемента (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span><span class="sxs-lookup"><span data-stu-id="e857a-110">This example uses the <xref:System.Xml.Linq.XContainer.Element%2A> method that was introduced in the topic [How to retrieve a single child element (LINQ to XML) (C#)](how-to-retrieve-a-single-child-element-linq-to-xml.md).</span></span> <span data-ttu-id="e857a-111">В нем также используется приведение для получения значений элементов, возвращаемых методом <xref:System.Xml.Linq.XContainer.Element%2A>.</span><span class="sxs-lookup"><span data-stu-id="e857a-111">It also uses casts to retrieve the values of the elements that are returned by the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  

<span data-ttu-id="e857a-112">В этом примере выводятся следующие данные:</span><span class="sxs-lookup"><span data-stu-id="e857a-112">This example produces the following output:</span></span>

```output
Lawnmower:1
Baby Monitor:2
```
