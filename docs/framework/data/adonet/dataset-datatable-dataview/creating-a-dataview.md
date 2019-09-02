---
title: Создание DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
ms.openlocfilehash: 391c071f19149e9690c9121b1094aef5bfa605cd
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203841"
---
# <a name="creating-a-dataview"></a>Создание DataView
Есть два способа создания представления данных <xref:System.Data.DataView>. Можно использовать конструктор **DataView** или можно создать ссылку на <xref:System.Data.DataTable.DefaultView%2A> свойство объекта. <xref:System.Data.DataTable> Конструктор **DataView** может быть пустым или может принимать либо **DataTable** в виде одного аргумента, либо **DataTable** вместе с условиями фильтра, критерием сортировки и фильтром состояния строки. Дополнительные сведения о дополнительных аргументах, доступных для использования с **DataView**, см. в разделе [Сортировка и фильтрация данных](sorting-and-filtering-data.md).  
  
 Поскольку индекс для **объекта DataView** строится как при создании **DataView** , так и при изменении любого из свойств **Sort**, **RowFilter**или **RowStateFilter** , достижение лучшей производительности достигается за счет предоставления всех начальных порядок сортировки или критерий фильтрации в качестве аргументов конструктора при создании **DataView**. Создание **объекта DataView** без указания условия сортировки или фильтра, а затем Установка **свойств Sort**, **RowFilter**или **RowStateFilter** в дальнейшем приводит к тому, что индекс будет построен по крайней мере дважды: один раз, когда **DataView** создаются и снова при изменении любого свойства сортировки или фильтрации.  
  
 Обратите внимание, что при создании **DataView** с помощью конструктора, который не принимает никаких аргументов, вы не сможете использовать **DataView** до тех пор, пока не будет задано свойство **Table** .  
  
 В следующем примере кода показано, как создать объект **DataView** с помощью конструктора **DataView** . **RowFilter**, столбец **сортировки** и **DataViewRowState** предоставляются вместе с таблицей данных.  
  
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
  
 В следующем примере кода показано, как получить ссылку на **представление DataView** по умолчанию объекта **DataTable** с помощью свойства **DefaultView** таблицы.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- [Объекты DataView](dataviews.md)
- [Сортировка и фильтрация данных](sorting-and-filtering-data.md)
- [DataTables](datatables.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
