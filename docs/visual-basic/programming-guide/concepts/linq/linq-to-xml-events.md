---
title: "События LINQ to XML (Visual Basic) | Документы Microsoft"
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
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: e2358808dfeafab1576a686563e6025f90e78954
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-events-visual-basic"></a><span data-ttu-id="9ab91-102">События LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ab91-102">LINQ to XML Events (Visual Basic)</span></span>
[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="9ab91-103">события позволяют получать уведомления при изменении XML-дерева.</span><span class="sxs-lookup"><span data-stu-id="9ab91-103"> events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="9ab91-104">Можно добавить события в экземпляр любого <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="9ab91-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="9ab91-105">Обработчик события будет получать уведомления об изменениях <xref:System.Xml.Linq.XObject>и всех его потомков.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="9ab91-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="9ab91-106">Например, можно добавить обработчик события в корень дерева и обрабатывать все изменения дерева в этом обработчике события.</span><span class="sxs-lookup"><span data-stu-id="9ab91-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="9ab91-107">Примеры [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] события, см. <xref:System.Xml.Linq.XObject.Changing>и <xref:System.Xml.Linq.XObject.Changed>.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></span><span class="sxs-lookup"><span data-stu-id="9ab91-107">For examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="9ab91-108">Типы и события</span><span class="sxs-lookup"><span data-stu-id="9ab91-108">Types and Events</span></span>  
 <span data-ttu-id="9ab91-109">Используйте следующие типы при работе с событиями.</span><span class="sxs-lookup"><span data-stu-id="9ab91-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="9ab91-110">Тип</span><span class="sxs-lookup"><span data-stu-id="9ab91-110">Type</span></span>|<span data-ttu-id="9ab91-111">Описание</span><span class="sxs-lookup"><span data-stu-id="9ab91-111">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="9ab91-112"><xref:System.Xml.Linq.XObjectChange></xref:System.Xml.Linq.XObjectChange></span><span class="sxs-lookup"><span data-stu-id="9ab91-112"><xref:System.Xml.Linq.XObjectChange></span></span>|<span data-ttu-id="9ab91-113">Указывает тип события, когда происходит событие <xref:System.Xml.Linq.XObject>.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="9ab91-113">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<span data-ttu-id="9ab91-114"><xref:System.Xml.Linq.XObjectChangeEventArgs></xref:System.Xml.Linq.XObjectChangeEventArgs></span><span class="sxs-lookup"><span data-stu-id="9ab91-114"><xref:System.Xml.Linq.XObjectChangeEventArgs></span></span>|<span data-ttu-id="9ab91-115">Предоставляет данные для <xref:System.Xml.Linq.XObject.Changing>и <xref:System.Xml.Linq.XObject.Changed>события.</xref:System.Xml.Linq.XObject.Changed> </xref:System.Xml.Linq.XObject.Changing></span><span class="sxs-lookup"><span data-stu-id="9ab91-115">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="9ab91-116">При изменении дерева XML возникают следующие события.</span><span class="sxs-lookup"><span data-stu-id="9ab91-116">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="9ab91-117">Событие</span><span class="sxs-lookup"><span data-stu-id="9ab91-117">Event</span></span>|<span data-ttu-id="9ab91-118">Описание</span><span class="sxs-lookup"><span data-stu-id="9ab91-118">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="9ab91-119"><xref:System.Xml.Linq.XObject.Changing></xref:System.Xml.Linq.XObject.Changing></span><span class="sxs-lookup"><span data-stu-id="9ab91-119"><xref:System.Xml.Linq.XObject.Changing></span></span>|<span data-ttu-id="9ab91-120">Происходит непосредственно перед тем, как <xref:System.Xml.Linq.XObject>или какой-либо из его потомков для изменения.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="9ab91-120">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<span data-ttu-id="9ab91-121"><xref:System.Xml.Linq.XObject.Changed></xref:System.Xml.Linq.XObject.Changed></span><span class="sxs-lookup"><span data-stu-id="9ab91-121"><xref:System.Xml.Linq.XObject.Changed></span></span>|<span data-ttu-id="9ab91-122">Происходит при <xref:System.Xml.Linq.XObject>был изменен или один из его наследников.</xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="9ab91-122">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="9ab91-123">Пример</span><span class="sxs-lookup"><span data-stu-id="9ab91-123">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="9ab91-124">Описание</span><span class="sxs-lookup"><span data-stu-id="9ab91-124">Description</span></span>  
 <span data-ttu-id="9ab91-125">События полезны, когда нужно поддержать какие-либо статистические данные в дереве XML.</span><span class="sxs-lookup"><span data-stu-id="9ab91-125">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="9ab91-126">Например, нужно рассчитать сумму элементов строки.</span><span class="sxs-lookup"><span data-stu-id="9ab91-126">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="9ab91-127">Следующий пример использует события для подсчета суммы всех дочерних элементов сложного элемента `Items`.</span><span class="sxs-lookup"><span data-stu-id="9ab91-127">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="9ab91-128">Код</span><span class="sxs-lookup"><span data-stu-id="9ab91-128">Code</span></span>  
  
```vb  
Module Module1  
    Dim WithEvents items As XElement = Nothing  
    Dim total As XElement = Nothing  
    Dim root As XElement = _  
            <Root>  
                <Total>0</Total>  
                <Items></Items>  
            </Root>  
  
    Private Sub XObjectChanged( _  
            ByVal sender As Object, _  
            ByVal cea As XObjectChangeEventArgs) _  
            Handles items.Changed  
        Select Case cea.ObjectChange  
            Case XObjectChange.Add  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) + _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
            Case XObjectChange.Remove  
                If sender.GetType() Is GetType(XElement) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XElement)).Value))  
                End If  
                If sender.GetType() Is GetType(XText) Then  
                    total.Value = CStr(CInt(total.Value) - _  
                            CInt((DirectCast(sender, XText)).Value))  
                End If  
        End Select  
        Console.WriteLine("Changed {0} {1}", _  
                            sender.GetType().ToString(), _  
                            cea.ObjectChange.ToString())  
    End Sub  
  
    Sub Main()  
        total = root.<Total>(0)  
        items = root.<Items>(0)  
        items.SetElementValue("Item1", 25)  
        items.SetElementValue("Item2", 50)  
        items.SetElementValue("Item2", 75)  
        items.SetElementValue("Item3", 133)  
        items.SetElementValue("Item1", Nothing)  
        items.SetElementValue("Item4", 100)  
        Console.WriteLine("Total:{0}", CInt(total))  
        Console.WriteLine(root)  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="9ab91-129">Комментарии</span><span class="sxs-lookup"><span data-stu-id="9ab91-129">Comments</span></span>  
 <span data-ttu-id="9ab91-130">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="9ab91-130">This code produces the following output:</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9ab91-131">См. также</span><span class="sxs-lookup"><span data-stu-id="9ab91-131">See Also</span></span>  
 [<span data-ttu-id="9ab91-132">Дополнительно программированию LINQ to XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9ab91-132">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
