---
title: Объекты DataRow и DataRowView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f5eec26-b809-4aca-8778-7e202356d856
ms.openlocfilehash: 14e7e1ccb051410c351e49afee9f2d6809264833
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151303"
---
# <a name="datarows-and-datarowviews"></a><span data-ttu-id="42a63-102">Объекты DataRow и DataRowView</span><span class="sxs-lookup"><span data-stu-id="42a63-102">DataRows and DataRowViews</span></span>
<span data-ttu-id="42a63-103">Представление <xref:System.Data.DataView> предоставляет перечисляемую коллекцию объектов <xref:System.Data.DataRowView>.</span><span class="sxs-lookup"><span data-stu-id="42a63-103">A <xref:System.Data.DataView> exposes an enumerable collection of <xref:System.Data.DataRowView> objects.</span></span> <span data-ttu-id="42a63-104">Объекты **DataRowView** разоблачают значения как объектные массивы, которые индексируются либо именем, либо обычной ссылкой столбца в основной таблице.</span><span class="sxs-lookup"><span data-stu-id="42a63-104">The **DataRowView** objects expose values as object arrays that are indexed by either the name or the ordinal reference of the column in the underlying table.</span></span> <span data-ttu-id="42a63-105">Вы можете <xref:System.Data.DataRow> получить доступ к тому, что <xref:System.Data.DataRowView.Row%2A> подвергается **DataRowView** с помощью свойства **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="42a63-105">You can access the <xref:System.Data.DataRow> that is exposed by the **DataRowView** by using the <xref:System.Data.DataRowView.Row%2A> property of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="42a63-106">При просмотре значений с помощью <xref:System.Data.DataView.RowStateFilter%2A> **DataRowView**свойство **DataView** определяет, какая строка версии базового **DataRow** подвергается воздействию.</span><span class="sxs-lookup"><span data-stu-id="42a63-106">When you view values by using a **DataRowView**, the <xref:System.Data.DataView.RowStateFilter%2A> property of the **DataView** determines which row version of the underlying **DataRow** is exposed.</span></span> <span data-ttu-id="42a63-107">Для получения информации о доступе к различным версиям строкс с помощью **DataRow** [см.](row-states-and-row-versions.md)</span><span class="sxs-lookup"><span data-stu-id="42a63-107">For information about accessing different row versions using a **DataRow**, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="42a63-108">В следующем примере кода показаны все текущие и исходные значения в таблице.</span><span class="sxs-lookup"><span data-stu-id="42a63-108">The following code example displays all the current and original values in a table.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="42a63-109">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="42a63-109">See also</span></span>

- <xref:System.Data.DataRowVersion>
- <xref:System.Data.DataViewRowState>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="42a63-110">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="42a63-110">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="42a63-111">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="42a63-111">ADO.NET Overview</span></span>](../ado-net-overview.md)
