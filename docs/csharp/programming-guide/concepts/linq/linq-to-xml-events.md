---
title: События LINQ to XML (C#)
ms.date: 07/20/2015
ms.assetid: ce7de951-cba7-4870-9962-733eb01cd680
ms.openlocfilehash: 8e0cb4519dd0fc2bed443d9a62b9a2545d10e161
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2020
ms.locfileid: "70253178"
---
# <a name="linq-to-xml-events-c"></a>События LINQ to XML (C#)
События [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] позволяют получать уведомления, когда изменяется дерево XML.  
  
 Можно добавить события в экземпляр любого объекта <xref:System.Xml.Linq.XObject>. Обработчик события будет получать уведомления об изменениях объекта <xref:System.Xml.Linq.XObject> и всех его потомков. Например, можно добавить обработчик события в корень дерева и обрабатывать все изменения дерева в этом обработчике события.  
  
 Примеры таких событий [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] см. в разделах <xref:System.Xml.Linq.XObject.Changing> и <xref:System.Xml.Linq.XObject.Changed>.  
  
## <a name="types-and-events"></a>Типы и события  
 Используйте следующие типы при работе с событиями.  
  
|Type|Описание:|  
|----------|-----------------|  
|<xref:System.Xml.Linq.XObjectChange>|Задает тип события, когда событие вызывается объектом <xref:System.Xml.Linq.XObject>.|  
|<xref:System.Xml.Linq.XObjectChangeEventArgs>|Предоставляет данные для событий <xref:System.Xml.Linq.XObject.Changing> и <xref:System.Xml.Linq.XObject.Changed>.|  
  
 При изменении дерева XML возникают следующие события.  
  
|Событие|Описание:|  
|-----------|-----------------|  
|<xref:System.Xml.Linq.XObject.Changing>|Возникает непосредственно перед тем, как объект <xref:System.Xml.Linq.XObject> или какой-либо его потомок изменяется.|  
|<xref:System.Xml.Linq.XObject.Changed>|Возникает, когда изменился объект <xref:System.Xml.Linq.XObject> или один из его потомков.|  
  
## <a name="example"></a>Пример  
  
### <a name="description"></a>Описание:  
 События полезны, когда нужно поддержать какие-либо статистические данные в дереве XML. Например, нужно рассчитать сумму элементов строки. Следующий пример использует события для подсчета суммы всех дочерних элементов сложного элемента `Items`.  
  
### <a name="code"></a>Код  
  
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
  
### <a name="comments"></a>Комментарии  
 Этот код выводит следующие результаты:  
  
```output  
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
  