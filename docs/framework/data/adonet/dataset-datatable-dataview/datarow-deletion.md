---
title: Удаление DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 7c80294c4bc879e6a1df4c9d1170eef14b8b83de
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915810"
---
# <a name="datarow-deletion"></a>Удаление DataRow
Существует два метода, которые <xref:System.Data.DataRow> можно использовать для удаления объекта <xref:System.Data.DataTable> из объекта: <xref:System.Data.DataRow.Delete%2A> метод <xref:System.Data.DataRowCollection> Remove объекта и метод объекта **DataRow** . В <xref:System.Data.DataRowCollection.Remove%2A> то время как метод удаляет **DataRow** из **датаровколлектион**, <xref:System.Data.DataRow.Delete%2A> метод помечает только строку для удаления. Фактическое удаление происходит, когда приложение вызывает метод **AcceptChanges** . Использование метода <xref:System.Data.DataRow.Delete%2A> позволяет программно проверять, какие строки помечены для удаления, перед их фактическим удалением. Когда строка отмечена для удаления, ее свойство <xref:System.Data.DataRow.RowState%2A> имеет значение <xref:System.Data.DataRow.Delete%2A>.  
  
 Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не должны вызываться в цикле foreach во время итерации по объекту <xref:System.Data.DataRowCollection>. Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не изменяет состояние коллекции.  
  
 При использовании <xref:System.Data.DataSet> **таблицы** данных или в сочетании с **DataAdapter** и реляционным источником данных используйте метод **Delete** объекта **DataRow** для удаления строки. Метод **Delete** помечает строку как удаленную в наборе **данных** или **DataTable** , но не удаляет ее. Вместо этого, когда **DataAdapter** обнаруживает строку, помеченную как **Удаленная**, она выполняет метод **DeleteCommand** для удаления строки в источнике данных. Затем строку можно удалить без возможности восстановления с помощью метода **AcceptChanges** . При использовании метода **Remove** для удаления строки строка удаляется полностью из таблицы, но **DataAdapter** не удаляет строку в источнике данных.  
  
 Метод **Remove** объекта **датаровколлектион** принимает **DataRow** в качестве аргумента и удаляет его из коллекции, как показано в следующем примере.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 В следующем примере показано, как вызвать метод **Delete** для **DataRow** , чтобы изменить его свойство **RowState** на Deleted.  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Если строка помечена для удаления и вызывается метод **AcceptChanges** объекта **DataTable** , то строка удаляется из **DataTable**. В отличие от этого, привызове RejectChanges **RowState** строки восстанавливается до того, как она была помечена как **Удаленная**.  
  
> [!NOTE]
> Если добавляется **RowState** объекта **DataRow** ,то есть он был только что добавлен в таблицу, а затем помечается как **Удаленный**, он удаляется из таблицы.  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Управление данными в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
