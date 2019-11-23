---
title: События LINQ to XML
ms.date: 07/20/2015
ms.assetid: 34923928-b99c-4004-956e-38f6db25e910
ms.openlocfilehash: 06191fb94f808d9a3ece8de000dec1c5de769dde
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351927"
---
# <a name="linq-to-xml-events-visual-basic"></a><span data-ttu-id="e0443-102">LINQ to XML Events (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0443-102">LINQ to XML Events (Visual Basic)</span></span>
<span data-ttu-id="e0443-103">События [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяют получать уведомления, когда изменяется дерево XML.</span><span class="sxs-lookup"><span data-stu-id="e0443-103">[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events enable you to be notified when an XML tree is altered.</span></span>  
  
 <span data-ttu-id="e0443-104">Можно добавить события в экземпляр любого объекта <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="e0443-104">You can add events to an instance of any <xref:System.Xml.Linq.XObject>.</span></span> <span data-ttu-id="e0443-105">Обработчик события будет получать уведомления об изменениях объекта <xref:System.Xml.Linq.XObject> и всех его потомков.</span><span class="sxs-lookup"><span data-stu-id="e0443-105">The event handler will then receive events for modifications to that <xref:System.Xml.Linq.XObject> and any of its descendants.</span></span> <span data-ttu-id="e0443-106">Например, можно добавить обработчик события в корень дерева и обрабатывать все изменения дерева в этом обработчике события.</span><span class="sxs-lookup"><span data-stu-id="e0443-106">For example, you can add an event handler to the root of the tree, and handle all modifications to the tree from that event handler.</span></span>  
  
 <span data-ttu-id="e0443-107">Примеры таких событий [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] см. в разделах <xref:System.Xml.Linq.XObject.Changing> и <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="e0443-107">For examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] events, see <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed>.</span></span>  
  
## <a name="types-and-events"></a><span data-ttu-id="e0443-108">Типы и события</span><span class="sxs-lookup"><span data-stu-id="e0443-108">Types and Events</span></span>  
 <span data-ttu-id="e0443-109">Используйте следующие типы при работе с событиями.</span><span class="sxs-lookup"><span data-stu-id="e0443-109">You use the following types when working with events:</span></span>  
  
|<span data-ttu-id="e0443-110">Type</span><span class="sxs-lookup"><span data-stu-id="e0443-110">Type</span></span>|<span data-ttu-id="e0443-111">Описание</span><span class="sxs-lookup"><span data-stu-id="e0443-111">Description</span></span>|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|<span data-ttu-id="e0443-112">Задает тип события, когда событие вызывается объектом <xref:System.Xml.Linq.XObject>.</span><span class="sxs-lookup"><span data-stu-id="e0443-112">Specifies the event type when an event is raised for an <xref:System.Xml.Linq.XObject>.</span></span>|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|<span data-ttu-id="e0443-113">Предоставляет данные для событий <xref:System.Xml.Linq.XObject.Changing> и <xref:System.Xml.Linq.XObject.Changed>.</span><span class="sxs-lookup"><span data-stu-id="e0443-113">Provides data for the <xref:System.Xml.Linq.XObject.Changing> and <xref:System.Xml.Linq.XObject.Changed> events.</span></span>|  
  
 <span data-ttu-id="e0443-114">При изменении дерева XML возникают следующие события.</span><span class="sxs-lookup"><span data-stu-id="e0443-114">The following events are raised when you modify an XML tree:</span></span>  
  
|<span data-ttu-id="e0443-115">событие</span><span class="sxs-lookup"><span data-stu-id="e0443-115">Event</span></span>|<span data-ttu-id="e0443-116">Описание</span><span class="sxs-lookup"><span data-stu-id="e0443-116">Description</span></span>|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|<span data-ttu-id="e0443-117">Возникает непосредственно перед тем, как объект <xref:System.Xml.Linq.XObject> или какой-либо его потомок изменяется.</span><span class="sxs-lookup"><span data-stu-id="e0443-117">Occurs just before this <xref:System.Xml.Linq.XObject> or any of its descendants is going to change.</span></span>|  
|<xref:System.Xml.Linq.XObject.Changed>|<span data-ttu-id="e0443-118">Возникает, когда изменился объект <xref:System.Xml.Linq.XObject> или один из его потомков.</span><span class="sxs-lookup"><span data-stu-id="e0443-118">Occurs when an <xref:System.Xml.Linq.XObject> has changed or any of its descendants have changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e0443-119">Пример</span><span class="sxs-lookup"><span data-stu-id="e0443-119">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="e0443-120">Описание</span><span class="sxs-lookup"><span data-stu-id="e0443-120">Description</span></span>  
 <span data-ttu-id="e0443-121">События полезны, когда нужно поддержать какие-либо статистические данные в дереве XML.</span><span class="sxs-lookup"><span data-stu-id="e0443-121">Events are useful when you want to maintain some aggregate information in an XML tree.</span></span> <span data-ttu-id="e0443-122">Например, нужно рассчитать сумму элементов строки.</span><span class="sxs-lookup"><span data-stu-id="e0443-122">For example, you may want maintain an invoice total that is the sum of the line items of the invoice.</span></span> <span data-ttu-id="e0443-123">Следующий пример использует события для подсчета суммы всех дочерних элементов сложного элемента `Items`.</span><span class="sxs-lookup"><span data-stu-id="e0443-123">This example uses events to maintain the total of all of the child elements under the complex element `Items`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="e0443-124">Код</span><span class="sxs-lookup"><span data-stu-id="e0443-124">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="e0443-125">Комментарии</span><span class="sxs-lookup"><span data-stu-id="e0443-125">Comments</span></span>  
 <span data-ttu-id="e0443-126">Этот код выводит следующие результаты:</span><span class="sxs-lookup"><span data-stu-id="e0443-126">This code produces the following output:</span></span>  
  
```console  
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
  
## <a name="see-also"></a><span data-ttu-id="e0443-127">См. также</span><span class="sxs-lookup"><span data-stu-id="e0443-127">See also</span></span>

- [<span data-ttu-id="e0443-128">Advanced LINQ to XML Programming (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e0443-128">Advanced LINQ to XML Programming (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
