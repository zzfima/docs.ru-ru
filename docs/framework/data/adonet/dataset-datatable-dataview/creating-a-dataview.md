---
title: Создание DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: d118f97e425782dbdf89c7e5d1eccd4d371b419c
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32759118"
---
# <a name="creating-a-dataview"></a>Создание DataView
Есть два способа создания представления данных <xref:System.Data.DataView>. Можно использовать **DataView** конструктору, или вы можете создать ссылку на <xref:System.Data.DataTable.DefaultView%2A> свойство <xref:System.Data.DataTable>. **DataView** конструктор может быть пустым либо может принимать **DataTable** как один аргумент или **DataTable** вместе с критериями фильтрации, сортировки и строки фильтр состояния. Дополнительные сведения о дополнительных аргументов для использования с **DataView**, в разделе [Сортировка и фильтрация данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Так как индекс для **DataView** формируется как при **DataView** создается и если какие-либо **сортировки**, **RowFilter**, или  **RowStateFilter** свойства изменяются, добиться лучшей производительности, указав любой исходный порядок сортировки или критерии фильтрации как аргументы конструктора, при создании **DataView**. Создание **DataView** без указания критериев сортировки и фильтрации, а затем установить **сортировки**, **RowFilter**, или **RowStateFilter** свойства позже приводит индекса для создания по крайней мере дважды: после при **DataView** создается, и снова при любого из свойств сортировки или фильтрации, будут изменены.  
  
 Обратите внимание, что при создании **DataView** с помощью конструктора, который не принимает никаких аргументов, нельзя будет использовать **DataView** пока **таблицы** свойство .  
  
 В следующем примере кода показано, как создать **DataView** с помощью **DataView** конструктор. Объект **RowFilter**, **сортировки** столбца, и **DataViewRowState** передаются вместе с **DataTable**.  
  
```vb  
Dim custDV As DataView = New DataView(custDS.Tables("Customers"), _  
    "Country = 'USA'", _  
    "ContactName", _  
    DataViewRowState.CurrentRows)  
```  
  
```csharp  
DataView custDV = new DataView(custDS.Tables["Customers"],   
    "Country = 'USA'",   
    "ContactName",   
    DataViewRowState.CurrentRows);  
```  
  
 В следующем примере кода показано, как получить ссылку на значение по умолчанию **DataView** из **DataTable** с помощью **DefaultView** свойство таблицы.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Сортировка и фильтрация данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)  
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
