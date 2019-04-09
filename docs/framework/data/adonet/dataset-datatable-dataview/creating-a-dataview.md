---
title: Создание DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 05122f7c980c4b7dfdb27eec73464a4f0556ba99
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59096684"
---
# <a name="creating-a-dataview"></a>Создание DataView
Есть два способа создания представления данных <xref:System.Data.DataView>. Можно использовать **DataView** конструктор, или можно создать ссылку на <xref:System.Data.DataTable.DefaultView%2A> свойство <xref:System.Data.DataTable>. **DataView** конструктор может быть пустым или может принимать **DataTable** как один аргумент, или **DataTable** вместе с критерии фильтрации, сортировки и строки фильтр состояния. Дополнительные сведения о других аргументах, доступных для использования с **DataView**, см. в разделе [Сортировка и фильтрация данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Так как индекс для **DataView** формируется как при **DataView** создается, а также при любой из **сортировки**, **RowFilter**, или  **RowStateFilter** изменяются свойства, для обеспечения лучшей производительности, указав любой исходный порядок сортировки или критерии фильтрации как аргументы конструктора, при создании **DataView**. Создание **DataView** без указания критериев сортировки или фильтрации, а затем установив **сортировки**, **RowFilter**, или **RowStateFilter** свойства позже приводит к менее двукратному построению индекса: после при **DataView** создается, и еще раз при изменении каких-либо свойств сортировки или фильтрации.  
  
 Обратите внимание, что при создании **DataView** с помощью конструктора, не принимающий никаких аргументов, нельзя будет использовать **DataView** пока **таблицы** свойство .  
  
 В следующем примере кода демонстрируется создание **DataView** с помощью **DataView** конструктор. Объект **RowFilter**, **сортировки** столбца, и **DataViewRowState** передаются вместе с **DataTable**.  
  
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

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [Сортировка и фильтрация данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)
- [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Управляемые поставщики ADO.NET и центр разработчиков DataSet](https://go.microsoft.com/fwlink/?LinkId=217917)
