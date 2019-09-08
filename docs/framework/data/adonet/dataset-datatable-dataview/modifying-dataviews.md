---
title: Изменение объектов DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 3e811410ea9fdd4be0cbd84b895483f69f58b0d0
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786054"
---
# <a name="modifying-dataviews"></a><span data-ttu-id="71374-102">Изменение объектов DataView</span><span class="sxs-lookup"><span data-stu-id="71374-102">Modifying DataViews</span></span>
<span data-ttu-id="71374-103">Объект <xref:System.Data.DataView> можно использовать, чтобы добавлять, удалять или изменять строки данных в базовой таблице.</span><span class="sxs-lookup"><span data-stu-id="71374-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="71374-104">Возможность использования **DataView** для изменения данных в базовой таблице контролируется путем установки одного из трех логических свойств **DataView**.</span><span class="sxs-lookup"><span data-stu-id="71374-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="71374-105">А именно: <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> и <xref:System.Data.DataView.AllowDelete%2A>.</span><span class="sxs-lookup"><span data-stu-id="71374-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="71374-106">По умолчанию для них задано **значение true** .</span><span class="sxs-lookup"><span data-stu-id="71374-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="71374-107">Если **AllowNew** имеет **значение true**, <xref:System.Data.DataView.AddNew%2A> можно использовать метод объекта **DataView** для создания нового <xref:System.Data.DataRowView>объекта.</span><span class="sxs-lookup"><span data-stu-id="71374-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="71374-108">Обратите внимание, что новая строка фактически не добавляется в <xref:System.Data.DataTable> базовую <xref:System.Data.DataRowView.EndEdit%2A> строку до тех пор, пока не будет вызван метод **DataRowView** .</span><span class="sxs-lookup"><span data-stu-id="71374-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="71374-109">При вызове метода DataRowView новая строка отбрасывается. <xref:System.Data.DataRowView.CancelEdit%2A></span><span class="sxs-lookup"><span data-stu-id="71374-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="71374-110">Обратите внимание, что в каждый момент времени можно изменять только один **DataRowView** .</span><span class="sxs-lookup"><span data-stu-id="71374-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="71374-111">При вызове метода **AddNew** или **BeginEdit** для **DataRowView** в случае существования ожидающей строки **EndEdit** вызывается неявно для ожидающей строки.</span><span class="sxs-lookup"><span data-stu-id="71374-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="71374-112">При вызове **EndEdit** изменения применяются к базовой **таблице** данных и затем могут быть зафиксированы или отклонены с помощью методов **AcceptChanges** или **RejectChanges** объекта **DataTable**, **DataSet**или  **Объект DataRow** .</span><span class="sxs-lookup"><span data-stu-id="71374-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="71374-113">Если **AllowNew** имеет **значение false**, то при вызове метода **AddNew** объекта **DataRowView**выдается исключение.</span><span class="sxs-lookup"><span data-stu-id="71374-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="71374-114">Если **AllowEdit** имеет **значение true**, можно изменить содержимое **DataRow** через **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="71374-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="71374-115">Вы можете подтвердить изменения в базовой строке с помощью **DataRowView. EndEdit** или отклонить изменения с помощью **DataRowView. CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="71374-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="71374-116">Отметим, что одновременно можно изменять только одну строку.</span><span class="sxs-lookup"><span data-stu-id="71374-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="71374-117">При вызове методов **AddNew** или **BeginEdit** для **DataRowView** при наличии ожидающей строки **EndEdit** вызывается неявно для ожидающей строки.</span><span class="sxs-lookup"><span data-stu-id="71374-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="71374-118">При вызове **EndEdit** предлагаемые изменения помещаются в **текущую** версию строки базового объекта **DataRow** и затем могут быть зафиксированы или отклонены с помощью методов **AcceptChanges** или **RejectChanges** класса  **Объект DataTable**, **DataSet**или **DataRow** .</span><span class="sxs-lookup"><span data-stu-id="71374-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="71374-119">Если **AllowEdit** имеет **значение false**, при попытке изменить значение в **объекте DataView**возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="71374-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="71374-120">При редактировании существующего **DataRowView** события базовой **таблицы DataTable** по-прежнему будут создаваться с предложенными изменениями.</span><span class="sxs-lookup"><span data-stu-id="71374-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="71374-121">Обратите внимание, что при вызове **EndEdit** или **CancelEdit** в базовой **DataRow**ожидающие изменения будут применены или отменены независимо от того, вызывается ли **EndEdit** или **CancelEdit** в **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="71374-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="71374-122">Если **алловделете** имеет **значение true**, строки из **DataView** можно удалить с помощью метода **Delete** объекта **DataView** или **DataRowView** , а строки будут удалены из базовой **таблицы**данных.</span><span class="sxs-lookup"><span data-stu-id="71374-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="71374-123">Позже можно зафиксировать или отклонить удаления с помощью **AcceptChanges** или **RejectChanges** соответственно.</span><span class="sxs-lookup"><span data-stu-id="71374-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="71374-124">Если **алловделете** имеет **значение false**, то при вызове метода **Delete** объекта **DataView** или **DataRowView**возникает исключение.</span><span class="sxs-lookup"><span data-stu-id="71374-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="71374-125">Следующий пример кода отключает использование **DataView** для удаления строк и добавляет новую строку в базовую таблицу с помощью **DataView**.</span><span class="sxs-lookup"><span data-stu-id="71374-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="71374-126">См. также</span><span class="sxs-lookup"><span data-stu-id="71374-126">See also</span></span>

- <xref:System.Data.DataTable>
- <xref:System.Data.DataView>
- <xref:System.Data.DataRowView>
- [<span data-ttu-id="71374-127">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="71374-127">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="71374-128">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="71374-128">ADO.NET Overview</span></span>](../ado-net-overview.md)
