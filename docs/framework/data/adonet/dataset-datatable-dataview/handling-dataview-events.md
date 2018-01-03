---
title: "Обработка событий DataView"
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
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 1f12dc41421090615e640fac4cc7bfb0fa08bb00
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="handling-dataview-events"></a><span data-ttu-id="a55c7-102">Обработка событий DataView</span><span class="sxs-lookup"><span data-stu-id="a55c7-102">Handling DataView Events</span></span>
<span data-ttu-id="a55c7-103">Событие <xref:System.Data.DataView.ListChanged> объекта <xref:System.Data.DataView> используется для определения того, было ли обновлено представление.</span><span class="sxs-lookup"><span data-stu-id="a55c7-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="a55c7-104">К обновлениям, которые вызывают это событие, относятся добавление, удаление или изменение строки в базовой таблице, добавление или удаление столбца из схемы базовой таблицы, изменение в родительской или дочерней связи.</span><span class="sxs-lookup"><span data-stu-id="a55c7-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="a55c7-105">**ListChanged** событий также уведомляет пользователя, если список строк существенно изменился из-за применения нового порядка сортировки или фильтра.</span><span class="sxs-lookup"><span data-stu-id="a55c7-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="a55c7-106">**ListChanged** реализует событие **ListChangedEventHandler** делегат типа <xref:System.ComponentModel> пространства имен и принимает в качестве ввода <xref:System.ComponentModel.ListChangedEventArgs> объекта.</span><span class="sxs-lookup"><span data-stu-id="a55c7-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="a55c7-107">Чтобы выяснить, какие изменения фиксируется с помощью <xref:System.ComponentModel.ListChangedType> значения перечисления в **ListChangedType** свойство **ListChangedEventArgs** объекта.</span><span class="sxs-lookup"><span data-stu-id="a55c7-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="a55c7-108">Для внесения изменений, которые включают добавление, удаление или перемещение строк, новому индексу добавленной или перемещенной строки и к прежнему индексу удаленной строки можно осуществлять с помощью **NewIndex** свойство **ListChangedEventArgs** объекта.</span><span class="sxs-lookup"><span data-stu-id="a55c7-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="a55c7-109">В случае перемещение строки, к прежнему индексу перемещенной строки можно осуществлять с помощью **OldIndex** свойство **ListChangedEventArgs** объекта.</span><span class="sxs-lookup"><span data-stu-id="a55c7-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="a55c7-110">**DataViewManager** также предоставляет **ListChanged** событий для уведомления о том, если при добавлении или удалении таблицы или изменений и **отношений** коллекцию базовый **набора данных**.</span><span class="sxs-lookup"><span data-stu-id="a55c7-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="a55c7-111">В следующем примере кода показано, как добавить **ListChanged** обработчика событий.</span><span class="sxs-lookup"><span data-stu-id="a55c7-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
```vb  
AddHandler custView.ListChanged, _  
  New System.ComponentModel.ListChangedEventHandler( _  
  AddressOf OnListChanged)  
  
Private Shared Sub OnListChanged( _  
  sender As Object, args As System.ComponentModel.ListChangedEventArgs)  
  Console.WriteLine("ListChanged:")  
  Console.WriteLine(vbTab & "    Type = " & _  
    System.Enum.GetName(args.ListChangedType.GetType(), _  
    args.ListChangedType))  
  Console.WriteLine(vbTab & "OldIndex = " & args.OldIndex)  
  Console.WriteLine(vbTab & "NewIndex = " & args.NewIndex)  
End Sub  
```  
  
```csharp  
custView.ListChanged  += new   
  System.ComponentModel.ListChangedEventHandler(OnListChanged);  
  
protected static void OnListChanged(object sender,   
  System.ComponentModel.ListChangedEventArgs args)  
{  
  Console.WriteLine("ListChanged:");  
  Console.WriteLine("\t    Type = " + args.ListChangedType);  
  Console.WriteLine("\tOldIndex = " + args.OldIndex);  
  Console.WriteLine("\tNewIndex = " + args.NewIndex);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a55c7-112">См. также</span><span class="sxs-lookup"><span data-stu-id="a55c7-112">See Also</span></span>  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [<span data-ttu-id="a55c7-113">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="a55c7-113">DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [<span data-ttu-id="a55c7-114">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="a55c7-114">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
