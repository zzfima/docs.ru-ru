---
title: Удаление DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 57f51ada00bf24617ca3e295a010aae64f0aa849
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879870"
---
# <a name="datarow-deletion"></a>Удаление DataRow
Существует два способа, можно использовать для удаления <xref:System.Data.DataRow> объекта из <xref:System.Data.DataTable> объект: **удалить** метод <xref:System.Data.DataRowCollection> объекта и <xref:System.Data.DataRow.Delete%2A> метод **DataRow**объекта. Тогда как <xref:System.Data.DataRowCollection.Remove%2A> метод удаления **DataRow** из **DataRowCollection**, <xref:System.Data.DataRow.Delete%2A> метод только помечает строку для удаления. Фактическое удаление происходит, когда приложение вызывает **AcceptChanges** метод. Использование метода <xref:System.Data.DataRow.Delete%2A> позволяет программно проверять, какие строки помечены для удаления, перед их фактическим удалением. Когда строка отмечена для удаления, ее свойство <xref:System.Data.DataRow.RowState%2A> имеет значение <xref:System.Data.DataRow.Delete%2A>.  
  
 Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не должны вызываться в цикле foreach во время итерации по объекту <xref:System.Data.DataRowCollection>. Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не изменяет состояние коллекции.  
  
 При использовании <xref:System.Data.DataSet> или **DataTable** в сочетании с **DataAdapter** и реляционного источника данных, используйте **удалить** метод  **DataRow** для удаления строки. **Удалить** метод помечает строку как **Deleted** в **набора данных** или **DataTable** , но не удаляет ее. Вместо этого, когда **DataAdapter** обнаруживает строку, помеченную как **Deleted**, он выполняет его **DeleteCommand** метод для удаления строки в источнике данных. Строки могут затем быть окончательно удалить с помощью **AcceptChanges** метод. Если вы используете **удалить** для удаления строки, строка удаляется из таблицы, но **DataAdapter** не приведет к удалению строки в источнике данных.  
  
 **Удалить** метод **DataRowCollection** принимает **DataRow** в качестве аргумента и удаляет его из коллекции, как показано в следующем примере.  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 Напротив, следующий пример демонстрирует вызов **удалить** метод **DataRow** для изменения его **RowState** для **Deleted** .  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 Если строка помечена для удаления и вызывается **AcceptChanges** метод **DataTable** объект, строка удаляется из **DataTable**. Напротив, при вызове метода **RejectChanges**, **RowState** строки возвращается к до помечается как **Deleted**.  
  
> [!NOTE]
>  Если **RowState** из **DataRow** — **Added**, означающее, что она недавно была добавлена в таблицу и затем она помечается как **Deleted**, это удаляется из таблицы.  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [Управление данными в DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
