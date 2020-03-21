---
title: Редактирование таблиц данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f08008a9-042e-4de9-94f3-4f0e502b1eb5
ms.openlocfilehash: 9e8c4204b51121b147fc7614066d9b849a687574
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151264"
---
# <a name="datatable-edits"></a><span data-ttu-id="a57bb-102">Редактирование таблиц данных</span><span class="sxs-lookup"><span data-stu-id="a57bb-102">DataTable Edits</span></span>
<span data-ttu-id="a57bb-103">При выполнении изменений значений столбцов в <xref:System.Data.DataRow>, изменения немедленно помещаются в текущее состояние строки.</span><span class="sxs-lookup"><span data-stu-id="a57bb-103">When you make changes to column values in a <xref:System.Data.DataRow>, the changes are immediately placed in the current state of the row.</span></span> <span data-ttu-id="a57bb-104">Затем <xref:System.Data.DataRowState> устанавливается на **изменение,** и изменения принимаются <xref:System.Data.DataRow.AcceptChanges%2A> или <xref:System.Data.DataRow.RejectChanges%2A> отклоняются с помощью или методов **DataRow.**</span><span class="sxs-lookup"><span data-stu-id="a57bb-104">The <xref:System.Data.DataRowState> is then set to **Modified**, and the changes are accepted or rejected using the <xref:System.Data.DataRow.AcceptChanges%2A> or <xref:System.Data.DataRow.RejectChanges%2A> methods of the **DataRow**.</span></span> <span data-ttu-id="a57bb-105">**DataRow** также предоставляет три метода, которые можно использовать для приостановки состояния строки во время редактирования.</span><span class="sxs-lookup"><span data-stu-id="a57bb-105">The **DataRow** also provides three methods that you can use to suspend the state of the row while you are editing it.</span></span> <span data-ttu-id="a57bb-106">Такими методами являются: <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A> и <xref:System.Data.DataRow.CancelEdit%2A>.</span><span class="sxs-lookup"><span data-stu-id="a57bb-106">These methods are <xref:System.Data.DataRow.BeginEdit%2A>, <xref:System.Data.DataRow.EndEdit%2A>, and <xref:System.Data.DataRow.CancelEdit%2A>.</span></span>  
  
 <span data-ttu-id="a57bb-107">При непосредственном изменении значений столбца в **DataRow** **DataRow DataRow** управляет значениями столбца с помощью версий **тока,** **по умолчанию**и **исходного** ряда.</span><span class="sxs-lookup"><span data-stu-id="a57bb-107">When you modify column values in a **DataRow** directly, the **DataRow** manages the column values using the **Current**, **Default**, and **Original** row versions.</span></span> <span data-ttu-id="a57bb-108">В дополнение к этим версиям строки, методы **BeginEdit,** **EndEdit**и **CancelEdit** используют версию четвертой строки: **Предложено.**</span><span class="sxs-lookup"><span data-stu-id="a57bb-108">In addition to these row versions, the **BeginEdit**, **EndEdit**, and **CancelEdit** methods use a fourth row version: **Proposed**.</span></span> <span data-ttu-id="a57bb-109">Для получения дополнительной информации о строке версии, см [строки государств и строки версии](row-states-and-row-versions.md).</span><span class="sxs-lookup"><span data-stu-id="a57bb-109">For more information about row versions, see [Row States and Row Versions](row-states-and-row-versions.md).</span></span>  
  
 <span data-ttu-id="a57bb-110">**Предлагаемая** строка версия существует во время операции по изменению, которая начинается с вызова **BeginEdit** и заканчивается либо с помощью **EndEdit** или **CancelEdit,** либо путем вызова **AcceptChanges** или **RejectChanges.**</span><span class="sxs-lookup"><span data-stu-id="a57bb-110">The **Proposed** row version exists during an edit operation that begins by calling **BeginEdit** and that ends either by using **EndEdit** or **CancelEdit,** or by calling **AcceptChanges** or **RejectChanges**.</span></span>  
  
 <span data-ttu-id="a57bb-111">Во время операции по изменению необходимо применить логику проверки к отдельным столбикам, оценив **ажиотальное значение** в случае **OfThe.** **DataTable**</span><span class="sxs-lookup"><span data-stu-id="a57bb-111">During the edit operation, you can apply validation logic to individual columns by evaluating the **ProposedValue** in the **ColumnChanged** event of the **DataTable**.</span></span> <span data-ttu-id="a57bb-112">Событие **ColumnChanged** содержит **DataColumnChangeEventArgs,** которые сохраняют ссылку на изменяемую колонку и на **предложенную стоимость.**</span><span class="sxs-lookup"><span data-stu-id="a57bb-112">The **ColumnChanged** event holds **DataColumnChangeEventArgs** that keep a reference to the column that is changing and to the **ProposedValue**.</span></span> <span data-ttu-id="a57bb-113">После оценки предложенного значения можно изменить его или отменить изменение.</span><span class="sxs-lookup"><span data-stu-id="a57bb-113">After you evaluate the proposed value, you can either modify it or cancel the edit.</span></span> <span data-ttu-id="a57bb-114">По окончании действия строки строка выходит из **состояния Предложенного.**</span><span class="sxs-lookup"><span data-stu-id="a57bb-114">When the edit is ended, the row moves out of the **Proposed** state.</span></span>  
  
 <span data-ttu-id="a57bb-115">Вы можете подтвердить правки, позвонив **в EndEdit,** или отменить их, позвонив **в CancelEdit.**</span><span class="sxs-lookup"><span data-stu-id="a57bb-115">You can confirm edits by calling **EndEdit**, or you can cancel them by calling **CancelEdit**.</span></span> <span data-ttu-id="a57bb-116">Обратите внимание, что в то время как **EndEdit** подтверждает ваши изменения, **DataSet** фактически не принимает изменения до тех пор, пока **acceptChanges** не будет вызван.</span><span class="sxs-lookup"><span data-stu-id="a57bb-116">Note that while **EndEdit** does confirm your edits, the **DataSet** does not actually accept the changes until **AcceptChanges** is called.</span></span> <span data-ttu-id="a57bb-117">Обратите внимание также, что если вы называете **AcceptChanges** до того, как закончите исправление с **помощью EndEdit** или **CancelEdit,** то изменение завершено, а значения **предлагаемых** строк принимаются как для **текущей,** так и **для исходной** версий строки.</span><span class="sxs-lookup"><span data-stu-id="a57bb-117">Note also that if you call **AcceptChanges** before you have ended the edit with **EndEdit** or **CancelEdit**, the edit is ended and the **Proposed** row values are accepted for both the **Current** and **Original** row versions.</span></span> <span data-ttu-id="a57bb-118">Таким же образом вызов **RejectChanges** завершает изменение и отбрасывает **версии текущей** и **предлагаемой** строки.</span><span class="sxs-lookup"><span data-stu-id="a57bb-118">In the same manner, calling **RejectChanges** ends the edit and discards the **Current** and **Proposed** row versions.</span></span> <span data-ttu-id="a57bb-119">Вызов **EndEdit** или **CancelEdit** после вызова **AcceptChanges** или **RejectChanges** не имеет никакого эффекта, поскольку изменение уже завершено.</span><span class="sxs-lookup"><span data-stu-id="a57bb-119">Calling **EndEdit** or **CancelEdit** after calling **AcceptChanges** or **RejectChanges** has no effect because the edit has already ended.</span></span>  
  
 <span data-ttu-id="a57bb-120">Следующий пример показывает, как использовать **BeginEdit** с **EndEdit** и **CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="a57bb-120">The following example demonstrates how to use **BeginEdit** with **EndEdit** and **CancelEdit**.</span></span> <span data-ttu-id="a57bb-121">Пример также проверяет **предлагаемое значение** в событии **ColumnChanged** и решает, следует ли отменить изменение.</span><span class="sxs-lookup"><span data-stu-id="a57bb-121">The example also checks the **ProposedValue** in the **ColumnChanged** event and decides whether to cancel the edit.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a57bb-122">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="a57bb-122">See also</span></span>

- <xref:System.Data.DataRow>
- <xref:System.Data.DataTable>
- <xref:System.Data.DataRowVersion>
- [<span data-ttu-id="a57bb-123">Управление данными в таблице данных</span><span class="sxs-lookup"><span data-stu-id="a57bb-123">Manipulating Data in a DataTable</span></span>](manipulating-data-in-a-datatable.md)
- [<span data-ttu-id="a57bb-124">Обработка событий таблиц данных</span><span class="sxs-lookup"><span data-stu-id="a57bb-124">Handling DataTable Events</span></span>](handling-datatable-events.md)
- [<span data-ttu-id="a57bb-125">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a57bb-125">ADO.NET Overview</span></span>](../ado-net-overview.md)
