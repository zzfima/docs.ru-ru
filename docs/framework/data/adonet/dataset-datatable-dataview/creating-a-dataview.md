---
title: Создание DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 9d21b17068ff3ce5b0bd3990144383d7f9ded2f9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151342"
---
# <a name="creating-a-dataview"></a>Создание DataView
Есть два способа создания представления данных <xref:System.Data.DataView>. Вы можете использовать конструктор **DataView,** или вы можете <xref:System.Data.DataTable.DefaultView%2A> создать <xref:System.Data.DataTable>ссылку на свойство . Конструктор **DataView** может быть пустым, или он может принять либо **DataTable** в качестве одного аргумента, либо **DataTable** вместе с критериями фильтра, критериями сортировки и фильтром состояния строки. Для получения дополнительной информации о дополнительных аргументах, доступных для использования в **DataView,** [см.](sorting-and-filtering-data.md)  
  
 Поскольку индекс **DataView** создается как при создании **DataView,** так и при изменении свойств **Sort,** **RowFilter**или **RowStateFilter,** вы достигаете наилучшей производительности, предоставляя какой-либо первоначальный порядок сортировки или критерии фильтрации в качестве аргументов конструктора при создании **DataView.** Создание **DataView** без указания критериев сортировки или фильтра, а затем настройки свойств **Sort,** **RowFilter**или **RowStateFilter** позже приводит к тому, что индекс будет построен по крайней мере дважды: один раз при создании **DataView** и снова, когда какие-либо свойства сортировки или фильтра изменяются.  
  
 Обратите внимание, что если вы создаете **DataView** с помощью конструктора, который не принимает никаких аргументов, вы не сможете использовать **DataView,** пока не установите свойство **таблицы.**  
  
 Следующий пример кода показывает, как создать **DataView** с помощью конструктора **DataView.** **СтрокаФильтр,** **Колонка сортировки** и **DataViewRowState** поставляются вместе с **DataTable.**  
  
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
  
 Следующий пример кода показывает, как получить ссылку на **DataView DataView** **DataTable** с помощью свойства **таблицы DefaultView.**  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [Объекты DataView](dataviews.md)
- [Сортировка и фильтрация данных](sorting-and-filtering-data.md)
- [DataTables](datatables.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
