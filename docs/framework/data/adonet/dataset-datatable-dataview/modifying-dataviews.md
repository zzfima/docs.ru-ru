---
title: "изменение DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# изменение DataView
Объект <xref:System.Data.DataView> можно использовать, чтобы добавлять, удалять или изменять строки данных в базовой таблице.  Возможность использовать объект **DataView**, чтобы изменять данные в базовой таблице, управляется заданием одного из трех логических свойств объекта **DataView**.  А именно: <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> и <xref:System.Data.DataView.AllowDelete%2A>.  По умолчанию для них установлено значение **true**.  
  
 Если свойству **AllowNew** задано значение **true**, то метод <xref:System.Data.DataView.AddNew%2A> объекта **DataView** можно использовать для создания нового объекта <xref:System.Data.DataRowView>.  Отметим, что новая строка фактически не добавляется в базовую таблицу <xref:System.Data.DataTable>, пока не будет вызван метод <xref:System.Data.DataRowView.EndEdit%2A> объекта **DataRowView**.  Если вызывается метод <xref:System.Data.DataRowView.CancelEdit%2A> объекта **DataRowView**, то новая строка удаляется.  Отметим, что одновременно можно изменять только один объект **DataRowView**.  При вызове метода **AddNew** или **BeginEdit** объекта **DataRowView**, пока существует ожидающая строка, для нее неявно вызывается метод **EndEdit**.  При вызове метода **EndEdit** к базовой таблице **DataTable** применяются изменения, которые в дальнейшем можно будет зафиксировать или отклонить при помощи методов **AcceptChanges** или **RejectChanges** объекта **DataTable**, **DataSet** или **DataRow**.  Если свойству **AllowNew** задано значение **false**, то при вызове метода **AddNew** объекта **DataRowView** формируется исключение.  
  
 Если свойству **AllowEdit** задано значение **true**, содержимое объекта **DataRow** можно изменить через объект **DataRowView**.  Подтвердить изменения, внесенные в базовую строку, можно при помощи метода **DataRowView.EndEdit**, а отклонить \- при помощи метода **DataRowView.CancelEdit**.  Отметим, что одновременно можно изменять только одну строку.  При вызове метода **AddNew** или **BeginEdit** объекта **DataRowView**, пока существует ожидающая строка, для нее неявно вызывается метод **EndEdit**.  При вызове метода **EndEdit** предложенные изменения помещаются в версию строки **Current** базового объекта **DataRow**, после чего их можно будет зафиксировать или отклонить при помощи методов **AcceptChanges** или **RejectChanges** объекта **DataTable**, **DataSet** или **DataRow**.  Если свойству **AllowEdit** задано значение **false**, то при попытке изменить значение в объекте **DataView** формируется исключение.  
  
 При редактировании существующего объекта **DataRowView** предлагаемые изменения все равно будут вызывать события базового объекта **DataTable**.  Отметим, что при вызове метода **EndEdit** или **CancelEdit** для базового объекта **DataRow** отложенные изменения будут применены или отменены независимо от того, какой метод \- **EndEdit** или **CancelEdit** \- вызван для объекта **DataRowView**.  
  
 Если свойству **AllowDelete** задано значение **true**, то строки из базового объекта **DataView** можно удалять при помощи метода **Delete** объекта **DataView** или **DataRowView**, строки также удаляются из базового объекта **DataTable**.  Затем удаление можно зафиксировать или отменить при помощи метода **AcceptChanges** или **RejectChanges**, соответственно.  Если свойству **AllowDelete** задано значение **false**, то при вызове метода **Delete** объекта **DataView** или **DataRowView** формируется исключение.  
  
 Следующий пример кода отключает использование объекта **DataView** для удаления строк и добавляет новую строку в базовую таблицу при помощи объекта **DataView**.  
  
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
  
## См. также  
 <xref:System.Data.DataTable>   
 <xref:System.Data.DataView>   
 <xref:System.Data.DataRowView>   
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)