---
title: Редактирование таблиц данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: a970ebda76f5bb6bdea704dabef2ee305436c613
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70205013"
---
# <a name="datatable-edits"></a><span data-ttu-id="ae0ff-102">Редактирование таблиц данных</span><span class="sxs-lookup"><span data-stu-id="ae0ff-102">DataTable Edits</span></span>
<span data-ttu-id="ae0ff-103">При выполнении изменений значений столбцов в <xref:System.Data.DataRow>, изменения немедленно помещаются в текущее состояние строки.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="ae0ff-104"><xref:System.Data.DataRow.AcceptChanges%2A> <xref:System.Data.DataRow.RejectChanges%2A>Затем задается значение Modified, и изменения принимаются или отклоняются с помощью методов или объекта DataRow. <xref:System.Data.DataRowState></span><span class="sxs-lookup"><span data-stu-id="ae0ff-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="ae0ff-105">**DataRow** также предоставляет три метода, которые можно использовать для приостановки состояния строки при ее редактировании.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="ae0ff-106">Такими методами являются: <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> и <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="ae0ff-107">При непосредственном изменении значений столбцов в **DataRow** объект **DataRow** управляет значениями столбцов, используя **текущие**версии строк, **используемые по умолчанию**и **исходные** .</span><span class="sxs-lookup"><span data-stu-id="ae0ff-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="ae0ff-108">В дополнение к этим версиям строк методы **BeginEdit**, **EndEdit**и **CancelEdit** используют четвертую версию строки: **Предложено**.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="ae0ff-109">Дополнительные сведения о версиях строк см. в разделе [состояния строк и версии строк](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="ae0ff-109">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="ae0ff-110">Предлагаемая версия строки существует во время операции изменения, которая начинается с вызова **BeginEdit** и заканчивается либо с помощью **EndEdit** **, либо CancelEdit,** либо путем вызова **метода AcceptChanges** или **RejectChanges**.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="ae0ff-111">Во время операции редактирования можно применить логику проверки к отдельным столбцам, оценивая **пропоседвалуе** в событии **колумнчанжед** объекта **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="ae0ff-112">Событие **колумнчанжед** содержит **датаколумнчанжеевентаргс** , которые сохраняют ссылку на изменяемый столбец и на **пропоседвалуе**.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="ae0ff-113">После оценки предложенного значения можно изменить его или отменить изменение.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="ae0ff-114">После завершения редактирования строка перемещается из предложенного состояния.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="ae0ff-115">Вы можете подтвердить изменения, вызвав **EndEdit**, или отменить их, вызвав **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="ae0ff-116">Обратите внимание, что хотя **EndEdit** подтверждает изменения, **набор данных** фактически не принимает изменения, пока не будет вызван метод **AcceptChanges** .</span><span class="sxs-lookup"><span data-stu-id="ae0ff-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="ae0ff-117">Обратите внимание, что если метод **AcceptChanges** вызывается до завершения операции Edit с **EndEdit** или **CancelEdit**, то редактирование завершается и **предлагаемые** значения строки принимаются как для **текущей** , так и для **исходной** версий строк.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="ae0ff-118">Аналогичным образом, вызов **RejectChanges** завершает изменение и отменяет **текущую** и предлагаемую версию строки.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="ae0ff-119">Вызов метода **EndEdit** или **CancelEdit** после вызова **метода AcceptChanges** или **RejectChanges** не действует, так как редактирование уже завершено.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="ae0ff-120">В следующем примере показано, как использовать **BeginEdit** с **EndEdit** и **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="ae0ff-121">В примере также проверяется **пропоседвалуе** в событии **колумнчанжед** и принимается решение, следует ли отменить изменение.</span><span class="sxs-lookup"><span data-stu-id="ae0ff-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="ae0ff-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ae0ff-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="ae0ff-123">Управление данными в DataTable</span><span class="sxs-lookup"><span data-stu-id="ae0ff-123">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="ae0ff-124">Обработка событий DataTable</span><span class="sxs-lookup"><span data-stu-id="ae0ff-124">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="ae0ff-125">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="ae0ff-125">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
