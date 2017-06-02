---
title: "Создание DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b1cc02d1-23b1-4439-a998-0da1899f3442
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Создание DataView
Есть два способа создания представления данных <xref:System.Data.DataView>.  Можно использовать конструктор **DataView** или создать ссылку на свойство <xref:System.Data.DataTable.DefaultView%2A> таблицы <xref:System.Data.DataTable>.  Конструктор **DataView** может быть пустым либо может принимать **DataTable** в виде одного аргумента или **DataTable** вместе с критериями фильтрации, критериями сортировки и фильтром состояния строк.  Дополнительные сведения о других аргументах, доступных для использования с **DataView**, см. в разделе [Сортировка и фильтрация данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md).  
  
 Так как индекс для представления **DataView** строится при создании этого **DataView**, а также при изменении любого из свойств **Sort**, **RowFilter** или **RowStateFilter**, наивысшая производительность достигается при предоставлении первоначального порядка сортировки или критериев фильтрации в виде аргументов конструктора во время создания **DataView**.  При создании **DataView** без указания условий фильтра и сортировки с последующим заданием свойств **Sort**, **RowFilter** или **RowStateFilter** индекс будет построен как минимум дважды: один раз при создании **DataView**, а затем при изменении свойств сортировки или фильтрации.  
  
 Имейте в виду, что при создании **DataView** при помощи конструктора без аргументов представление **DataView** нельзя будет использовать, пока не будет задано свойство **Table**.  
  
 В следующем примере кода демонстрируется, как создавать представление **DataView** при помощи конструктора **DataView**.  Значение **RowFilter**, столбец **Sort** и состояние **DataViewRowState** передаются вместе с **DataTable**.  
  
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
  
 В следующем примере кода демонстрируется, как получать ссылку на представление **DataView** по умолчанию таблицы **DataTable** при помощи свойства **DefaultView** этой таблицы.  
  
```vb  
Dim custDV As DataView = custDS.Tables("Customers").DefaultView  
  
```  
  
```csharp  
DataView custDV = custDS.Tables["Customers"].DefaultView;  
```  
  
## См. также  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Сортировка и фильтрация данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/sorting-and-filtering-data.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)