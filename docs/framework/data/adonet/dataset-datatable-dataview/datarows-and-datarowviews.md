---
title: Объекты DataRow и DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: b7f92c0341a63df6bb5553d656469b374755aae7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54562652"
---
# <a name="datarows-and-datarowviews"></a>Объекты DataRow и DataRowView
Представление <xref:System.Data.DataView> предоставляет перечисляемую коллекцию объектов <xref:System.Data.DataRowView>. **DataRowView** объекты предоставляют значения в виде массивов объектов, которые индексируются по имени или по порядковому номеру столбца в базовой таблице. Вы можете получить доступ к <xref:System.Data.DataRow> , предоставляемая **DataRowView** с помощью <xref:System.Data.DataRowView.Row%2A> свойство **DataRowView**.  
  
 При просмотре значений с помощью **DataRowView**, <xref:System.Data.DataView.RowStateFilter%2A> свойство **DataView** определяет, какая версия строки базового **DataRow** предоставляется. Сведения о доступе к различным версиям строк с помощью **DataRow**, см. в разделе [строки состояния и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).  
  
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
  
## <a name="see-also"></a>См. также
- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
