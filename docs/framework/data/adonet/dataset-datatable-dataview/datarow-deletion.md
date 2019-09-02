---
title: Удаление DataRow
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c34f531d-4b9b-4071-b2d7-342c402aa586
ms.openlocfilehash: 46109ee1781b8b509df87b4203c51a55b9f596ae
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205103"
---
# <a name="datarow-deletion"></a><span data-ttu-id="59f55-102">Удаление DataRow</span><span class="sxs-lookup"><span data-stu-id="59f55-102">DataRow Deletion</span></span>
<span data-ttu-id="59f55-103">Существует два метода, которые <xref:System.Data.DataRow> можно использовать для удаления объекта <xref:System.Data.DataTable> из объекта: <xref:System.Data.DataRow.Delete%2A> метод <xref:System.Data.DataRowCollection> Remove объекта и метод объекта **DataRow** .</span><span class="sxs-lookup"><span data-stu-id="59f55-103">There are two methods you can use to delete a <xref:System.Data.DataRow> object from a <xref:System.Data.DataTable> object: the **Remove** method of the <xref:System.Data.DataRowCollection> object, and the <xref:System.Data.DataRow.Delete%2A> method of the **DataRow** object.</span></span> <span data-ttu-id="59f55-104">В <xref:System.Data.DataRowCollection.Remove%2A> то время как метод удаляет **DataRow** из **датаровколлектион**, <xref:System.Data.DataRow.Delete%2A> метод помечает только строку для удаления.</span><span class="sxs-lookup"><span data-stu-id="59f55-104">Whereas the <xref:System.Data.DataRowCollection.Remove%2A> method deletes a **DataRow** from the **DataRowCollection**, the <xref:System.Data.DataRow.Delete%2A> method only marks the row for deletion.</span></span> <span data-ttu-id="59f55-105">Фактическое удаление происходит, когда приложение вызывает метод **AcceptChanges** .</span><span class="sxs-lookup"><span data-stu-id="59f55-105">The actual removal occurs when the application calls the **AcceptChanges** method.</span></span> <span data-ttu-id="59f55-106">Использование метода <xref:System.Data.DataRow.Delete%2A> позволяет программно проверять, какие строки помечены для удаления, перед их фактическим удалением.</span><span class="sxs-lookup"><span data-stu-id="59f55-106">By using <xref:System.Data.DataRow.Delete%2A>, you can programmatically check which rows are marked for deletion before actually removing them.</span></span> <span data-ttu-id="59f55-107">Когда строка отмечена для удаления, ее свойство <xref:System.Data.DataRow.RowState%2A> имеет значение <xref:System.Data.DataRow.Delete%2A>.</span><span class="sxs-lookup"><span data-stu-id="59f55-107">When a row is marked for deletion, its <xref:System.Data.DataRow.RowState%2A> property is set to <xref:System.Data.DataRow.Delete%2A>.</span></span>  
  
 <span data-ttu-id="59f55-108">Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не должны вызываться в цикле foreach во время итерации по объекту <xref:System.Data.DataRowCollection>.</span><span class="sxs-lookup"><span data-stu-id="59f55-108">Neither <xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> should be called in a foreach loop while iterating through a <xref:System.Data.DataRowCollection> object.</span></span> <span data-ttu-id="59f55-109">Ни <xref:System.Data.DataRow.Delete%2A>, ни <xref:System.Data.DataRowCollection.Remove%2A> не изменяет состояние коллекции.</span><span class="sxs-lookup"><span data-stu-id="59f55-109"><xref:System.Data.DataRow.Delete%2A> nor <xref:System.Data.DataRowCollection.Remove%2A> modify the state of the collection.</span></span>  
  
 <span data-ttu-id="59f55-110">При использовании <xref:System.Data.DataSet> **таблицы** данных или в сочетании с **DataAdapter** и реляционным источником данных используйте метод **Delete** объекта **DataRow** для удаления строки.</span><span class="sxs-lookup"><span data-stu-id="59f55-110">When using a <xref:System.Data.DataSet> or **DataTable** in conjunction with a **DataAdapter** and a relational data source, use the **Delete** method of the **DataRow** to remove the row.</span></span> <span data-ttu-id="59f55-111">Метод **Delete** помечает строку как удаленную в наборе **данных** или **DataTable** , но не удаляет ее.</span><span class="sxs-lookup"><span data-stu-id="59f55-111">The **Delete** method marks the row as **Deleted** in the **DataSet** or **DataTable** but does not remove it.</span></span> <span data-ttu-id="59f55-112">Вместо этого, когда **DataAdapter** обнаруживает строку, помеченную как **Удаленная**, она выполняет метод **DeleteCommand** для удаления строки в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="59f55-112">Instead, when the **DataAdapter** encounters a row marked as **Deleted**, it executes its **DeleteCommand** method to delete the row at the data source.</span></span> <span data-ttu-id="59f55-113">Затем строку можно удалить без возможности восстановления с помощью метода **AcceptChanges** .</span><span class="sxs-lookup"><span data-stu-id="59f55-113">The row can then be permanently removed using the **AcceptChanges** method.</span></span> <span data-ttu-id="59f55-114">При использовании метода **Remove** для удаления строки строка удаляется полностью из таблицы, но **DataAdapter** не удаляет строку в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="59f55-114">If you use **Remove** to delete the row, the row is removed entirely from the table, but the **DataAdapter** will not delete the row at the data source.</span></span>  
  
 <span data-ttu-id="59f55-115">Метод **Remove** объекта **датаровколлектион** принимает **DataRow** в качестве аргумента и удаляет его из коллекции, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="59f55-115">The **Remove** method of the **DataRowCollection** takes a **DataRow** as an argument and removes it from the collection, as shown in the following example.</span></span>  
  
```vb  
workTable.Rows.Remove(workRow)  
```  
  
```csharp  
workTable.Rows.Remove(workRow);  
```  
  
 <span data-ttu-id="59f55-116">В следующем примере показано, как вызвать метод **Delete** для **DataRow** , чтобы изменить его свойство **RowState** на Deleted.</span><span class="sxs-lookup"><span data-stu-id="59f55-116">In contrast, the following example demonstrates how to call the **Delete** method on a **DataRow** to change its **RowState** to **Deleted**.</span></span>  
  
```vb  
workRow.Delete  
```  
  
```csharp  
workRow.Delete();  
```  
  
 <span data-ttu-id="59f55-117">Если строка помечена для удаления и вызывается метод **AcceptChanges** объекта **DataTable** , то строка удаляется из **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="59f55-117">If a row is marked for deletion and you call the **AcceptChanges** method of the **DataTable** object, the row is removed from the **DataTable**.</span></span> <span data-ttu-id="59f55-118">В отличие от этого, привызове RejectChanges **RowState** строки восстанавливается до того, как она была помечена как **Удаленная**.</span><span class="sxs-lookup"><span data-stu-id="59f55-118">In contrast, if you call **RejectChanges**, the **RowState** of the row reverts to what it was before being marked as **Deleted**.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="59f55-119">Если добавляется **RowState** объекта **DataRow** ,то есть он был только что добавлен в таблицу, а затем помечается как **Удаленный**, он удаляется из таблицы.</span><span class="sxs-lookup"><span data-stu-id="59f55-119">If the **RowState** of a **DataRow** is **Added**, meaning it has just been added to the table, and it is then marked as **Deleted**, it is removed from the table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59f55-120">См. также</span><span class="sxs-lookup"><span data-stu-id="59f55-120">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataRowCollection>
- <xref:System.Data.DataTable>
- [<span data-ttu-id="59f55-121">Управление данными в DataTable</span><span class="sxs-lookup"><span data-stu-id="59f55-121">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="59f55-122">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="59f55-122">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
