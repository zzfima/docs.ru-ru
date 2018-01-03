---
title: "Редактирование таблиц данных"
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
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 3d06fc3a82457972db94f82964942f446bb761be
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="datatable-edits"></a><span data-ttu-id="32ec1-102">Редактирование таблиц данных</span><span class="sxs-lookup"><span data-stu-id="32ec1-102">DataTable Edits</span></span>
<span data-ttu-id="32ec1-103">При выполнении изменений значений столбцов в <xref:System.Data.DataRow>, изменения немедленно помещаются в текущее состояние строки.</span><span class="sxs-lookup"><span data-stu-id="32ec1-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="32ec1-104"><xref:System.Data.DataRowState> Присваивается значение **Modified**, и изменения принимаются или отклонить при помощи <xref:System.Data.DataRow.AcceptChanges%2A> или <xref:System.Data.DataRow.RejectChanges%2A> методы **DataRow**.</span><span class="sxs-lookup"><span data-stu-id="32ec1-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="32ec1-105">**DataRow** также предоставляет три метода, которые можно использовать для приостановки состояния строки, пока вы работаете.</span><span class="sxs-lookup"><span data-stu-id="32ec1-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="32ec1-106">Такими методами являются: <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> и <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="32ec1-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="32ec1-107">При изменении значений столбцов **DataRow** напрямую, **DataRow** управляет значениями столбцов с помощью **текущей**, **по умолчанию**, и **Исходного** версий строк.</span><span class="sxs-lookup"><span data-stu-id="32ec1-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="32ec1-108">Помимо этих версий строки **BeginEdit**, **EndEdit**, и **CancelEdit** методы используют четвертая версия: **предложено**.</span><span class="sxs-lookup"><span data-stu-id="32ec1-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="32ec1-109">Дополнительные сведения о версиях строк см. в разделе [состояния строк и версии строк](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="32ec1-109">For more information about row versions, see [Row States and Row Versions](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="32ec1-110">**Предложено** версия строки существует во время операции изменения, которая начинается вызовом **BeginEdit** и заканчивающийся либо с помощью **EndEdit** или **CancelEdit**  или вызвав **AcceptChanges** или **RejectChanges**.</span><span class="sxs-lookup"><span data-stu-id="32ec1-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="32ec1-111">Во время операции изменения можно применить логику проверки в отдельные столбцы, оценивая **ProposedValue** в **ColumnChanged** событие **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="32ec1-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="32ec1-112">**ColumnChanged** содержит событие **DataColumnChangeEventArgs** , сохранить ссылку для изменяемого столбца и **ProposedValue**.</span><span class="sxs-lookup"><span data-stu-id="32ec1-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="32ec1-113">После оценки предложенного значения можно изменить его или отменить изменение.</span><span class="sxs-lookup"><span data-stu-id="32ec1-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="32ec1-114">Когда изменение заканчивается, строка переходит из **предложено** состояния.</span><span class="sxs-lookup"><span data-stu-id="32ec1-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="32ec1-115">Изменения можно подтвердить, вызвав **EndEdit**, или отменить, вызвав **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="32ec1-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="32ec1-116">Обратите внимание, что, хотя **EndEdit** подтвердить изменения, **DataSet** фактически не принимает изменения до **AcceptChanges** вызывается.</span><span class="sxs-lookup"><span data-stu-id="32ec1-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="32ec1-117">Обратите внимание, что при вызове метода **AcceptChanges** до окончания изменений при помощи **EndEdit** или **CancelEdit**, то изменение заканчивается и **предложено** значения строк принимаются для обоих **текущей** и **исходного** версий строк.</span><span class="sxs-lookup"><span data-stu-id="32ec1-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="32ec1-118">Таким же образом вызвав **RejectChanges** заканчивает изменения и отменяет **текущей** и **предложено** версий строк.</span><span class="sxs-lookup"><span data-stu-id="32ec1-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="32ec1-119">Вызов **EndEdit** или **CancelEdit** после вызова **AcceptChanges** или **RejectChanges** имеет смысл, поскольку редактирование уже завершено.</span><span class="sxs-lookup"><span data-stu-id="32ec1-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="32ec1-120">В следующем примере демонстрируется использование **BeginEdit** с **EndEdit** и **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="32ec1-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="32ec1-121">В примере также проверяется **ProposedValue** в **ColumnChanged** событий и решает, следует ли отменить изменение.</span><span class="sxs-lookup"><span data-stu-id="32ec1-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
```vb  
Dim workTable As DataTable = New DataTable  
workTable.Columns.Add("LastName", Type.GetType("System.String"))  
  
AddHandler workTable.ColumnChanged, _  
  New DataColumnChangeEventHandler(AddressOf OnColumnChanged)  
  
Dim workRow As DataRow = workTable.NewRow()  
workRow(0) = "Smith"  
workTable.Rows.Add(workRow)  
  
workRow.BeginEdit()  
' Causes the ColumnChanged event to write a message and cancel the edit.  
workRow(0) = ""       
workRow.EndEdit()  
  
' Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow(0), workRow.RowState)  
  
Private Shared Sub OnColumnChanged( _  
  sender As Object, args As DataColumnChangeEventArgs)  
  If args.Column.ColumnName = "LastName" Then  
    If args.ProposedValue.ToString() = "" Then  
      Console.WriteLine("Last Name cannot be blank.  Edit canceled.")  
      args.Row.CancelEdit()  
    End If  
  End If  
End Sub  
```  
  
```csharp  
DataTable workTable  = new DataTable();  
workTable.Columns.Add("LastName", typeof(String));  
  
workTable.ColumnChanged +=   
  new DataColumnChangeEventHandler(OnColumnChanged);  
  
DataRow workRow = workTable.NewRow();  
workRow[0] = "Smith";  
workTable.Rows.Add(workRow);  
  
workRow.BeginEdit();  
// Causes the ColumnChanged event to write a message and cancel the edit.  
workRow[0] = "";       
workRow.EndEdit();  
  
// Displays "Smith, New".  
Console.WriteLine("{0}, {1}", workRow[0], workRow.RowState);    
  
protected static void OnColumnChanged(  
  Object sender, DataColumnChangeEventArgs args)  
{  
  if (args.Column.ColumnName == "LastName")  
    if (args.ProposedValue.ToString() == "")  
    {  
      Console.WriteLine("Last Name cannot be blank. Edit canceled.");  
      args.Row.CancelEdit();  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="32ec1-122">См. также</span><span class="sxs-lookup"><span data-stu-id="32ec1-122">See Also</span></span>  
 <xref:System.Data.DataRow>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataRowVersion>  
 [<span data-ttu-id="32ec1-123">Управление данными в DataTable</span><span class="sxs-lookup"><span data-stu-id="32ec1-123">Manipulating Data in a DataTable</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/manipulating-data-in-a-datatable.md)  
 [<span data-ttu-id="32ec1-124">Обработка событий DataTable</span><span class="sxs-lookup"><span data-stu-id="32ec1-124">Handling DataTable Events</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md)  
 [<span data-ttu-id="32ec1-125">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="32ec1-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
