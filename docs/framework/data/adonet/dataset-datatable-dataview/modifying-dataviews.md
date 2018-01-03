---
title: "Изменение объектов DataView"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 921707b07f1e8c8a9208df7de74512325f3027d2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="modifying-dataviews"></a>Изменение объектов DataView
Объект <xref:System.Data.DataView> можно использовать, чтобы добавлять, удалять или изменять строки данных в базовой таблице. Возможность использования **DataView** для изменения данных в базовой таблице, управляется заданием одного из трех логических свойств объекта **DataView**. А именно: <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> и <xref:System.Data.DataView.AllowDelete%2A>. Устанавливается **true** по умолчанию.  
  
 Если **AllowNew** — **true**, можно использовать <xref:System.Data.DataView.AddNew%2A> метод **DataView** для создания нового <xref:System.Data.DataRowView>. Обратите внимание, что строки не были добавлены к базовому объекту <xref:System.Data.DataTable> до <xref:System.Data.DataRowView.EndEdit%2A> метод **DataRowView** вызывается. Если <xref:System.Data.DataRowView.CancelEdit%2A> метод **DataRowView** является именем, новая строка удаляется. Обратите внимание, что можно изменять только один **DataRowView** одновременно. При вызове метода **AddNew** или **BeginEdit** метод **DataRowView** пока существует ожидающая строка, **EndEdit** неявно вызывается Ожидающая строка. При **EndEdit** является именем, изменения будут применены к базовому объекту **DataTable** и в дальнейшем можно будет зафиксировать или отклонить с помощью **AcceptChanges** или  **RejectChanges** методы **DataTable**, **DataSet**, или **DataRow** объекта. Если **AllowNew** — **false**, создается исключение при вызове метода **AddNew** метод **DataRowView**.  
  
 Если **AllowEdit** — **true**, можно изменить содержимое **DataRow** через **DataRowView**. Можно подтвердить изменения в базовую строку при помощи **DataRowView.EndEdit** или отклонить изменения с помощью **DataRowView.CancelEdit**. Отметим, что одновременно можно изменять только одну строку. При вызове метода **AddNew** или **BeginEdit** методы **DataRowView** пока существует ожидающая строка, **EndEdit** неявно вызывается Ожидающая строка. Когда **EndEdit** вызывается, предложенные изменения помещаются в **текущей** версия строки базового **DataRow** и в дальнейшем можно будет зафиксировать или отклонить с помощью  **AcceptChanges** или **RejectChanges** методы **DataTable**, **DataSet**, или **DataRow** объект. Если **AllowEdit** — **false**, создается исключение при попытке изменить значение в **DataView**.  
  
 Если в имеющемся **DataRowView** редактируется, события базового **DataTable** по-прежнему будет вызываться с предлагаемыми изменениями. Обратите внимание, что при вызове метода **EndEdit** или **CancelEdit** для базового **DataRow**отложенные изменения будут применены или отменены независимо от того, следует ли  **EndEdit** или **CancelEdit** будет вызван на **DataRowView**.  
  
 Если **AllowDelete** — **true**, можно удалить строки из **DataView** с помощью **удаление** метод **DataView**  или **DataRowView** объекта и строки удаляются из основного **DataTable**. Можно зафиксировать или отклонить с помощью операции удаления **AcceptChanges** или **RejectChanges** соответственно. Если **AllowDelete** — **false**, создается исключение при вызове метода **удаление** метод **DataView** или  **DataRowView**.  
  
 Следующий пример кода отключает использование **DataView** для удаления строк и добавляет новую строку в базовую таблицу при помощи **DataView**.  
  
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
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
