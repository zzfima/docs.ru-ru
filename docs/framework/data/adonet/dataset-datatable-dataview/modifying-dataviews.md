---
title: Изменение объектов DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 3e811410ea9fdd4be0cbd84b895483f69f58b0d0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786054"
---
# <a name="modifying-dataviews"></a>Изменение объектов DataView
Объект <xref:System.Data.DataView> можно использовать, чтобы добавлять, удалять или изменять строки данных в базовой таблице. Возможность использования **DataView** для изменения данных в базовой таблице контролируется путем установки одного из трех логических свойств **DataView**. А именно: <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> и <xref:System.Data.DataView.AllowDelete%2A>. По умолчанию для них задано **значение true** .  
  
 Если **AllowNew** имеет **значение true**, <xref:System.Data.DataView.AddNew%2A> можно использовать метод объекта **DataView** для создания нового <xref:System.Data.DataRowView>объекта. Обратите внимание, что новая строка фактически не добавляется в <xref:System.Data.DataTable> базовую <xref:System.Data.DataRowView.EndEdit%2A> строку до тех пор, пока не будет вызван метод **DataRowView** . При вызове метода DataRowView новая строка отбрасывается. <xref:System.Data.DataRowView.CancelEdit%2A> Обратите внимание, что в каждый момент времени можно изменять только один **DataRowView** . При вызове метода **AddNew** или **BeginEdit** для **DataRowView** в случае существования ожидающей строки **EndEdit** вызывается неявно для ожидающей строки. При вызове **EndEdit** изменения применяются к базовой **таблице** данных и затем могут быть зафиксированы или отклонены с помощью методов **AcceptChanges** или **RejectChanges** объекта **DataTable**, **DataSet**или  **Объект DataRow** . Если **AllowNew** имеет **значение false**, то при вызове метода **AddNew** объекта **DataRowView**выдается исключение.  
  
 Если **AllowEdit** имеет **значение true**, можно изменить содержимое **DataRow** через **DataRowView**. Вы можете подтвердить изменения в базовой строке с помощью **DataRowView. EndEdit** или отклонить изменения с помощью **DataRowView. CancelEdit**. Отметим, что одновременно можно изменять только одну строку. При вызове методов **AddNew** или **BeginEdit** для **DataRowView** при наличии ожидающей строки **EndEdit** вызывается неявно для ожидающей строки. При вызове **EndEdit** предлагаемые изменения помещаются в **текущую** версию строки базового объекта **DataRow** и затем могут быть зафиксированы или отклонены с помощью методов **AcceptChanges** или **RejectChanges** класса  **Объект DataTable**, **DataSet**или **DataRow** . Если **AllowEdit** имеет **значение false**, при попытке изменить значение в **объекте DataView**возникает исключение.  
  
 При редактировании существующего **DataRowView** события базовой **таблицы DataTable** по-прежнему будут создаваться с предложенными изменениями. Обратите внимание, что при вызове **EndEdit** или **CancelEdit** в базовой **DataRow**ожидающие изменения будут применены или отменены независимо от того, вызывается ли **EndEdit** или **CancelEdit** в **DataRowView**.  
  
 Если **алловделете** имеет **значение true**, строки из **DataView** можно удалить с помощью метода **Delete** объекта **DataView** или **DataRowView** , а строки будут удалены из базовой **таблицы**данных. Позже можно зафиксировать или отклонить удаления с помощью **AcceptChanges** или **RejectChanges** соответственно. Если **алловделете** имеет **значение false**, то при вызове метода **Delete** объекта **DataView** или **DataRowView**возникает исключение.  
  
 Следующий пример кода отключает использование **DataView** для удаления строк и добавляет новую строку в базовую таблицу с помощью **DataView**.  
  
```vb  
Dim custTable As DataTable = custDS.Tables("Customers")  
Dim custView As DataView = custTable.DefaultView  
custView.Sort = "CompanyName"  
  
custView.AllowDelete = False  
  
Dim newDRV As DataRowView = custView.AddNew()  
newDRV("CustomerID") = "ABCDE"  
newDRV("CompanyName") = "ABC Products"  
newDRV.EndEdit()  
```  
  
```csharp  
DataTable custTable = custDS.Tables["Customers"];  
DataView custView = custTable.DefaultView;  
custView.Sort = "CompanyName";  
  
custView.AllowDelete = false;  
  
DataRowView newDRV = custView.AddNew();  
newDRV["CustomerID"] = "ABCDE";  
newDRV["CompanyName"] = "ABC Products";  
newDRV.EndEdit();  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [Объекты DataView](dataviews.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
