---
title: Удаление DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 128c41e1906b17e7f42458e8a5f1b3d3ec9cc449
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="datarow-deletion"></a>Удаление DataRow
Существует два метода, которые можно использовать для удаления <xref:System.Data.DataRow> объекта из <xref:System.Data.DataTable> объект: **удалить** метод <xref:System.Data.DataRowCollection> объекта и <xref:System.Data.DataRow.Delete%2A> метод **DataRow**объекта. В то время как <xref:System.Data.DataRowCollection.Remove%2A> метод удаления **DataRow** из **DataRowCollection**, <xref:System.Data.DataRow.Delete%2A> только помечает строку для удаления. Фактическое удаление происходит, когда приложение вызывает **AcceptChanges** метод. Использование метода <xref:System.Data.DataRow.Delete%2A> позволяет программно проверять, какие строки помечены для удаления, перед их фактическим удалением. Когда строка отмечена для удаления, ее свойство <xref:System.Data.DataRow.RowState%2A> имеет значение <xref:System.Data.DataRow.Delete%2A>.  
  
 Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не должны вызываться в цикле foreach во время итерации по объекту <xref:System.Data.DataRowCollection>. Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не изменяет состояние коллекции.  
  
 При использовании <xref:System.Data.DataSet> или **DataTable** в сочетании с **DataAdapter** и реляционного источника данных, используйте **удаление** метод  **DataRow** для удаления строки. **Удаление** помечает строку как **Deleted** в **DataSet** или **DataTable** , но не удаляет его. Вместо этого, когда **DataAdapter** обнаруживает строку, помеченную как **Deleted**, он выполняет его **DeleteCommand** метод, чтобы удалить строку в источнике данных. Строки могут затем быть окончательно удалить с помощью **AcceptChanges** метод. При использовании **удалить** для удаления строки, строка удаляется из таблицы, но **DataAdapter** не будет удалять строки в источнике данных.  
  
 **Удалить** метод **DataRowCollection** принимает **DataRow** в качестве аргумента и удаляет его из коллекции, как показано в следующем примере.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 Напротив, следующий пример демонстрирует вызов **удаление** метод **DataRow** для изменения его **RowState** для **Deleted** .  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Если строка помечена для удаления и вызывается **AcceptChanges** метод **DataTable** объект, строка удаляется из **DataTable**. В отличие от этого, при вызове метода **RejectChanges**, **RowState** строки возвращается к до помечается как **Deleted**.  
  
> [!NOTE]
>  Если **RowState** из **DataRow** — **Added**, что означает, что был только что добавлен в таблицу и затем она помечается как **Deleted**, это удалить из таблицы.  
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataRowCollection>  
 <xref:System.Data.DataTable>  
 [Управление данными в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
