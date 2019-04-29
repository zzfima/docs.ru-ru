---
title: Изменение объектов DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 6e340b9b72735598650d2eefa6e19ab40fffc2e4
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61607418"
---
# <a name="modifying-dataviews"></a>Изменение объектов DataView
Объект <xref:System.Data.DataView> можно использовать, чтобы добавлять, удалять или изменять строки данных в базовой таблице. Возможность использования **DataView** для изменения данных в базовой таблице задается с помощью одного из трех логических свойств объекта **DataView**. А именно: <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> и <xref:System.Data.DataView.AllowDelete%2A>. Они задаются **true** по умолчанию.  
  
 Если **AllowNew** — **true**, можно использовать <xref:System.Data.DataView.AddNew%2A> метод **DataView** для создания нового <xref:System.Data.DataRowView>. Обратите внимание, что строки не были добавлены к базовому объекту <xref:System.Data.DataTable> пока <xref:System.Data.DataRowView.EndEdit%2A> метод **DataRowView** вызывается. Если <xref:System.Data.DataRowView.CancelEdit%2A> метод **DataRowView** является именем, новая строка удаляется. Обратите внимание, что можно изменять только один **DataRowView** за раз. При вызове метода **AddNew** или **BeginEdit** метод **DataRowView** пока существует ожидающая строка, **EndEdit** неявно вызывается Ожидающая строка. При **EndEdit** — вызывается, будут применены к базовому объекту **DataTable** и в дальнейшем можно будет зафиксировать или отклонить с помощью **AcceptChanges** или  **RejectChanges** методы **DataTable**, **набора данных**, или **DataRow** объекта. Если **AllowNew** — **false**, возникает исключение при вызове метода **AddNew** метод **DataRowView**.  
  
 Если **AllowEdit** — **true**, можно изменить содержимое **DataRow** через **DataRowView**. Можно проверить изменения в базовых строк с помощью **DataRowView.EndEdit** или отклонить изменения с помощью **DataRowView.CancelEdit**. Отметим, что одновременно можно изменять только одну строку. При вызове метода **AddNew** или **BeginEdit** методы **DataRowView** пока существует ожидающая строка, **EndEdit** неявно вызывается Ожидающая строка. Когда **EndEdit** вызывается, предложенные изменения помещаются в **текущей** версия строки базового **DataRow** и в дальнейшем можно будет зафиксировать или отклонить с помощью  **AcceptChanges** или **RejectChanges** методы **DataTable**, **набора данных**, или **DataRow** объект. Если **AllowEdit** — **false**, возникает исключение при попытке изменить значение в **DataView**.  
  
 Если в имеющемся **DataRowView** редактируется, события базового **DataTable** по-прежнему будет вызываться с предлагаемыми изменениями. Обратите внимание, что при вызове метода **EndEdit** или **CancelEdit** для базового **DataRow**, ожидающие изменения будут применены или отменены независимо от того, следует ли  **EndEdit** или **CancelEdit** вызывается для **DataRowView**.  
  
 Если **AllowDelete** — **true**, можно удалить строки из **DataView** с помощью **удалить** метод **DataView**  или **DataRowView** объекта и строки удаляются из базового **DataTable**. Вы можете зафиксировать или отменить удаление с помощью **AcceptChanges** или **RejectChanges** соответственно. Если **AllowDelete** — **false**, возникает исключение при вызове метода **удалить** метод **DataView** или  **DataRowView**.  
  
 В следующем примере кода отключает использование **DataView** для удаления строк и добавляет новую строку в базовую таблицу при помощи **DataView**.  
  
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
- [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
