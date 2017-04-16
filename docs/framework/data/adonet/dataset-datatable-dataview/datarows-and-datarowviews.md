---
title: "Объекты DataRow и DataRowView  | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Объекты DataRow и DataRowView 
Представление <xref:System.Data.DataView> предоставляет перечисляемую коллекцию объектов <xref:System.Data.DataRowView>.  Объекты **DataRowView** предоставляют значения в виде массивов объектов, которые индексируются либо по имени, либо по порядковому номеру столбца основной таблицы.  Обращаться к строке <xref:System.Data.DataRow>, предоставленной представлением **DataRowView**, можно с помощью свойства <xref:System.Data.DataRowView.Row%2A> представления **DataRowView**.  
  
 При просмотре значений с помощью **DataRowView** свойство <xref:System.Data.DataView.RowStateFilter%2A> представления **DataView** определяет, какая версия строки базового объекта **DataRow** будет показана.  Сведения о доступе к разным версиям строки при помощи объекта **DataRow** см. в разделе [Состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
 В следующем примере кода показаны все текущие и исходные значения в таблице.  
  
```vb  
Dim catView As DataView = New DataView(catDS.Tables("Categories"))  
Console.WriteLine("Current Values:")  
WriteView(catView)  
Console.WriteLine("Original Values:")  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal  
WriteView(catView)      
  
Public Shared Sub WriteView(thisDataView As DataView)  
  Dim rowView As DataRowView  
  Dim i As Integer  
  
  For Each rowView In thisDataView  
    For i = 0 To thisDataView.Table.Columns.Count - 1  
      Console.Write(rowView(i) & vbTab)  
    Next  
    Console.WriteLine()  
  Next  
End Sub  
  
```  
  
```csharp  
DataView catView = new DataView(catDS.Tables["Categories"]);  
Console.WriteLine("Current Values:");  
WriteView(catView);  
Console.WriteLine("Original Values:");  
catView.RowStateFilter = DataViewRowState.ModifiedOriginal;  
WriteView(catView);  
  
public static void WriteView(DataView thisDataView)  
{  
  foreach (DataRowView rowView in thisDataView)  
  {  
    for (int i = 0; i < thisDataView.Table.Columns.Count; i++)  
      Console.Write(rowView[i] + "\t");  
    Console.WriteLine();  
  }  
}  
```  
  
## См. также  
 <xref:System.Data.DataRowVersion>   
 <xref:System.Data.DataViewRowState>   
 <xref:System.Data.DataView>   
 <xref:System.Data.DataRowView>   
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)