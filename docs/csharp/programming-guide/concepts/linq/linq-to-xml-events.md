---
title: События LINQ to XML (C#)
ms.date: 07/20/2015
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: 3dd4eaa0261ae7d878e188572d260b34b64fc031
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2018
ms.locfileid: "42999945"
---
# <a name="linq-to-xml-events-c"></a><span data-ttu-id="474cf-102">События LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="474cf-102">LINQ to XML Events (C#)</span></span>
<span data-ttu-id="474cf-103">События [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяют получать уведомления, когда изменяется дерево XML.</span><span class="sxs-lookup"><span data-stu-id="474cf-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="474cf-104">Можно добавить события в экземпляр любого объекта <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="474cf-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="474cf-105">Обработчик события будет получать уведомления об изменениях объекта <xref:System.Xml.Linq.XObject> и всех его потомков.</span><span class="sxs-lookup"><span data-stu-id="474cf-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="474cf-106">Например, можно добавить обработчик события в корень дерева и обрабатывать все изменения дерева в этом обработчике события.</span><span class="sxs-lookup"><span data-stu-id="474cf-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="474cf-107">Примеры таких событий [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] см. в разделах <xref:System.Xml.Linq.XObject.Changing> и <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="474cf-107">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="474cf-108">Типы и события</span><span class="sxs-lookup"><span data-stu-id="474cf-108">Types and Events</span></span>  
 <span data-ttu-id="474cf-109">Используйте следующие типы при работе с событиями.</span><span class="sxs-lookup"><span data-stu-id="474cf-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="474cf-110">Тип</span><span class="sxs-lookup"><span data-stu-id="474cf-110">Type</span></span>|<span data-ttu-id="474cf-111">Описание:</span><span class="sxs-lookup"><span data-stu-id="474cf-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="474cf-112">Задает тип события, когда событие вызывается объектом <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="474cf-112">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="474cf-113">Предоставляет данные для событий <xref:System.Xml.Linq.XObject.Changing> и <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="474cf-113">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="474cf-114">При изменении дерева XML возникают следующие события.</span><span class="sxs-lookup"><span data-stu-id="474cf-114">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="474cf-115">событие</span><span class="sxs-lookup"><span data-stu-id="474cf-115">Event</span></span>|<span data-ttu-id="474cf-116">Описание:</span><span class="sxs-lookup"><span data-stu-id="474cf-116">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="474cf-117">Возникает непосредственно перед тем, как объект <xref:System.Xml.Linq.XObject> или какой-либо его потомок изменяется.</span><span class="sxs-lookup"><span data-stu-id="474cf-117">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="474cf-118">Возникает, когда изменился объект <xref:System.Xml.Linq.XObject> или один из его потомков.</span><span class="sxs-lookup"><span data-stu-id="474cf-118">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="474cf-119">Пример</span><span class="sxs-lookup"><span data-stu-id="474cf-119">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="474cf-120">Описание:</span><span class="sxs-lookup"><span data-stu-id="474cf-120">Description</span></span>  
 <span data-ttu-id="474cf-121">События полезны, когда нужно поддержать какие-либо статистические данные в дереве XML.</span><span class="sxs-lookup"><span data-stu-id="474cf-121">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="474cf-122">Например, нужно рассчитать сумму элементов строки.</span><span class="sxs-lookup"><span data-stu-id="474cf-122">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="474cf-123">Следующий пример использует события для подсчета суммы всех дочерних элементов сложного элемента `Items`.</span><span class="sxs-lookup"><span data-stu-id="474cf-123">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="474cf-124">Код</span><span class="sxs-lookup"><span data-stu-id="474cf-124">Code</span></span>  
  
```csharp  
XElement root = new XElement("Root",  
    new XElement("Total", "0"),  
    new XElement("Items")  
);  
XElement total = root.Element("Total");  
XElement items = root.Element("Items");  
items.Changed += (object sender, XObjectChangeEventArgs cea) =>  
{  
    switch (cea.ObjectChange)  
    {  
        case XObjectChange.Add:  
            if (sender is XElement)  
                total.Value = ((int)total + (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total + (int)((XText)sender).Parent).ToString();  
            break;  
        case XObjectChange.Remove:  
            if (sender is XElement)  
                total.Value = ((int)total - (int)(XElement)sender).ToString();  
            if (sender is XText)  
                total.Value = ((int)total - Int32.Parse(((XText)sender).Value)).ToString();  
            break;  
    }  
    Console.WriteLine("Changed {0} {1}",  
      sender.GetType().ToString(), cea.ObjectChange.ToString());  
};  
items.SetElementValue("Item1", 25);  
items.SetElementValue("Item2", 50);  
items.SetElementValue("Item2", 75);  
items.SetElementValue("Item3", 133);  
items.SetElementValue("Item1", null);  
items.SetElementValue("Item4", 100);  
Console.WriteLine("Total:{0}", (int)total);  
Console.WriteLine(root);  
```  
  
### <a name="comments"></a><span data-ttu-id="474cf-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="474cf-125">Comments</span></span>  
 <span data-ttu-id="474cf-126">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="474cf-126">This code produces the following output:</span></span>  
  
```  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XText Remove  
Changed System.Xml.Linq.XText Add  
Changed System.Xml.Linq.XElement Add  
Changed System.Xml.Linq.XElement Remove  
Changed System.Xml.Linq.XElement Add  
Total:308  
<Root>  
  <Total>308</Total>  
  <Items>  
    <Item2>75</Item2>  
    <Item3>133</Item3>  
    <Item4>100</Item4>  
  </Items>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="474cf-127">См. также</span><span class="sxs-lookup"><span data-stu-id="474cf-127">See Also</span></span>  
 [<span data-ttu-id="474cf-128">Расширенные методы программирования LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="474cf-128">Advanced LINQ to XML Programming (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
