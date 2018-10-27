---
title: Изменение объектов DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 697a3991-b660-4a5a-8a54-1a2304ff158e
ms.openlocfilehash: 3b1e0cbfc6118ad9ca670f5d91183b78b2c99d89
ms.sourcegitcommit: b22705f1540b237c566721018f974822d5cd8758
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/19/2018
ms.locfileid: "49453035"
---
# <a name="modifying-dataviews"></a><span data-ttu-id="018d5-102">Изменение объектов DataView</span><span class="sxs-lookup"><span data-stu-id="018d5-102">Modifying DataViews</span></span>
<span data-ttu-id="018d5-103">Объект <xref:System.Data.DataView> можно использовать, чтобы добавлять, удалять или изменять строки данных в базовой таблице.</span><span class="sxs-lookup"><span data-stu-id="018d5-103">You can use the <xref:System.Data.DataView> to add, delete, or modify rows of data in the underlying table.</span></span> <span data-ttu-id="018d5-104">Возможность использования **DataView** для изменения данных в базовой таблице задается с помощью одного из трех логических свойств объекта **DataView**.</span><span class="sxs-lookup"><span data-stu-id="018d5-104">The ability to use the **DataView** to modify data in the underlying table is controlled by setting one of three Boolean properties of the **DataView**.</span></span> <span data-ttu-id="018d5-105">А именно: <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A> и <xref:System.Data.DataView.AllowDelete%2A>.</span><span class="sxs-lookup"><span data-stu-id="018d5-105">These properties are <xref:System.Data.DataView.AllowNew%2A>, <xref:System.Data.DataView.AllowEdit%2A>, and <xref:System.Data.DataView.AllowDelete%2A>.</span></span> <span data-ttu-id="018d5-106">Они задаются **true** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="018d5-106">They are set to **true** by default.</span></span>  
  
 <span data-ttu-id="018d5-107">Если **AllowNew** — **true**, можно использовать <xref:System.Data.DataView.AddNew%2A> метод **DataView** для создания нового <xref:System.Data.DataRowView>.</span><span class="sxs-lookup"><span data-stu-id="018d5-107">If **AllowNew** is **true**, you can use the <xref:System.Data.DataView.AddNew%2A> method of the **DataView** to create a new <xref:System.Data.DataRowView>.</span></span> <span data-ttu-id="018d5-108">Обратите внимание, что строки не были добавлены к базовому объекту <xref:System.Data.DataTable> пока <xref:System.Data.DataRowView.EndEdit%2A> метод **DataRowView** вызывается.</span><span class="sxs-lookup"><span data-stu-id="018d5-108">Note that a new row is not actually added to the underlying <xref:System.Data.DataTable> until the <xref:System.Data.DataRowView.EndEdit%2A> method of the **DataRowView** is called.</span></span> <span data-ttu-id="018d5-109">Если <xref:System.Data.DataRowView.CancelEdit%2A> метод **DataRowView** является именем, новая строка удаляется.</span><span class="sxs-lookup"><span data-stu-id="018d5-109">If the <xref:System.Data.DataRowView.CancelEdit%2A> method of the **DataRowView** is called, the new row is discarded.</span></span> <span data-ttu-id="018d5-110">Обратите внимание, что можно изменять только один **DataRowView** за раз.</span><span class="sxs-lookup"><span data-stu-id="018d5-110">Note also that you can edit only one **DataRowView** at a time.</span></span> <span data-ttu-id="018d5-111">При вызове метода **AddNew** или **BeginEdit** метод **DataRowView** пока существует ожидающая строка, **EndEdit** неявно вызывается Ожидающая строка.</span><span class="sxs-lookup"><span data-stu-id="018d5-111">If you call the **AddNew** or **BeginEdit** method of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="018d5-112">При **EndEdit** — вызывается, будут применены к базовому объекту **DataTable** и в дальнейшем можно будет зафиксировать или отклонить с помощью **AcceptChanges** или  **RejectChanges** методы **DataTable**, **набора данных**, или **DataRow** объекта.</span><span class="sxs-lookup"><span data-stu-id="018d5-112">When **EndEdit** is called, the changes are applied to the underlying **DataTable** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="018d5-113">Если **AllowNew** — **false**, возникает исключение при вызове метода **AddNew** метод **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="018d5-113">If **AllowNew** is **false**, an exception is thrown if you call the **AddNew** method of the **DataRowView**.</span></span>  
  
 <span data-ttu-id="018d5-114">Если **AllowEdit** — **true**, можно изменить содержимое **DataRow** через **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="018d5-114">If **AllowEdit** is **true**, you can modify the contents of a **DataRow** via the **DataRowView**.</span></span> <span data-ttu-id="018d5-115">Можно проверить изменения в базовых строк с помощью **DataRowView.EndEdit** или отклонить изменения с помощью **DataRowView.CancelEdit**.</span><span class="sxs-lookup"><span data-stu-id="018d5-115">You can confirm changes to the underlying row using **DataRowView.EndEdit** or reject the changes using **DataRowView.CancelEdit**.</span></span> <span data-ttu-id="018d5-116">Отметим, что одновременно можно изменять только одну строку.</span><span class="sxs-lookup"><span data-stu-id="018d5-116">Note that only one row can be edited at a time.</span></span> <span data-ttu-id="018d5-117">При вызове метода **AddNew** или **BeginEdit** методы **DataRowView** пока существует ожидающая строка, **EndEdit** неявно вызывается Ожидающая строка.</span><span class="sxs-lookup"><span data-stu-id="018d5-117">If you call the **AddNew** or **BeginEdit** methods of the **DataRowView** while a pending row exists, **EndEdit** is implicitly called on the pending row.</span></span> <span data-ttu-id="018d5-118">Когда **EndEdit** вызывается, предложенные изменения помещаются в **текущей** версия строки базового **DataRow** и в дальнейшем можно будет зафиксировать или отклонить с помощью  **AcceptChanges** или **RejectChanges** методы **DataTable**, **набора данных**, или **DataRow** объект.</span><span class="sxs-lookup"><span data-stu-id="018d5-118">When **EndEdit** is called, proposed changes are placed in the **Current** row version of the underlying **DataRow** and can later be committed or rejected using the **AcceptChanges** or **RejectChanges** methods of the **DataTable**, **DataSet**, or **DataRow** object.</span></span> <span data-ttu-id="018d5-119">Если **AllowEdit** — **false**, возникает исключение при попытке изменить значение в **DataView**.</span><span class="sxs-lookup"><span data-stu-id="018d5-119">If **AllowEdit** is **false**, an exception is thrown if you attempt to modify a value in the **DataView**.</span></span>  
  
 <span data-ttu-id="018d5-120">Если в имеющемся **DataRowView** редактируется, события базового **DataTable** по-прежнему будет вызываться с предлагаемыми изменениями.</span><span class="sxs-lookup"><span data-stu-id="018d5-120">When an existing **DataRowView** is being edited, events of the underlying **DataTable** will still be raised with the proposed changes.</span></span> <span data-ttu-id="018d5-121">Обратите внимание, что при вызове метода **EndEdit** или **CancelEdit** для базового **DataRow**, ожидающие изменения будут применены или отменены независимо от того, следует ли  **EndEdit** или **CancelEdit** вызывается для **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="018d5-121">Note that if you call **EndEdit** or **CancelEdit** on the underlying **DataRow**, pending changes will be applied or canceled regardless of whether **EndEdit** or **CancelEdit** is called on the **DataRowView**.</span></span>  
  
 <span data-ttu-id="018d5-122">Если **AllowDelete** — **true**, можно удалить строки из **DataView** с помощью **удалить** метод **DataView**  или **DataRowView** объекта и строки удаляются из базового **DataTable**.</span><span class="sxs-lookup"><span data-stu-id="018d5-122">If **AllowDelete** is **true**, you can delete rows from the **DataView** by using the **Delete** method of the **DataView** or **DataRowView** object, and the rows are deleted from the underlying **DataTable**.</span></span> <span data-ttu-id="018d5-123">Вы можете зафиксировать или отменить удаление с помощью **AcceptChanges** или **RejectChanges** соответственно.</span><span class="sxs-lookup"><span data-stu-id="018d5-123">You can later commit or reject the deletes using **AcceptChanges** or **RejectChanges** respectively.</span></span> <span data-ttu-id="018d5-124">Если **AllowDelete** — **false**, возникает исключение при вызове метода **удалить** метод **DataView** или  **DataRowView**.</span><span class="sxs-lookup"><span data-stu-id="018d5-124">If **AllowDelete** is **false**, an exception is thrown if you call the **Delete** method of the **DataView** or **DataRowView**.</span></span>  
  
 <span data-ttu-id="018d5-125">В следующем примере кода отключает использование **DataView** для удаления строк и добавляет новую строку в базовую таблицу при помощи **DataView**.</span><span class="sxs-lookup"><span data-stu-id="018d5-125">The following code example disables using the **DataView** to delete rows  and adds a new row to the underlying table using the **DataView**.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="018d5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="018d5-126">See Also</span></span>  
 <xref:System.Data.DataTable>  
 <xref:System.Data.DataView>  
 <xref:System.Data.DataRowView>  
 [<span data-ttu-id="018d5-127">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="018d5-127">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="018d5-128">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="018d5-128">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
