---
title: Обработка событий DataView
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
ms.openlocfilehash: b625fad846c4c6cf008843bff1f6b0eabe0e1de4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151108"
---
# <a name="handling-dataview-events"></a><span data-ttu-id="e54ee-102">Обработка событий DataView</span><span class="sxs-lookup"><span data-stu-id="e54ee-102">Handling DataView Events</span></span>
<span data-ttu-id="e54ee-103">Событие <xref:System.Data.DataView.ListChanged> объекта <xref:System.Data.DataView> используется для определения того, было ли обновлено представление.</span><span class="sxs-lookup"><span data-stu-id="e54ee-103">You can use the <xref:System.Data.DataView.ListChanged> event of the <xref:System.Data.DataView> to determine if a view has been updated.</span></span> <span data-ttu-id="e54ee-104">К обновлениям, которые вызывают это событие, относятся добавление, удаление или изменение строки в базовой таблице, добавление или удаление столбца из схемы базовой таблицы, изменение в родительской или дочерней связи.</span><span class="sxs-lookup"><span data-stu-id="e54ee-104">Updates that raise the event include adding, deleting, or modifying a row in the underlying table; adding or deleting a column to the schema of the underlying table; and a change in a parent or child relationship.</span></span> <span data-ttu-id="e54ee-105">Событие **ListChanged** также уведомляет вас, если список строк, которые вы просматриваете, значительно изменился из-за применения нового порядка сортировки или фильтра.</span><span class="sxs-lookup"><span data-stu-id="e54ee-105">The **ListChanged** event also notifies you if the list of rows you are viewing has changed significantly due to the application of a new sort order or a filter.</span></span>  
  
 <span data-ttu-id="e54ee-106">Событие **ListChanged** реализует делегирование **ListChangedEventHandler** пространства <xref:System.ComponentModel> имен и <xref:System.ComponentModel.ListChangedEventArgs> принимает в качестве ввода объекта.</span><span class="sxs-lookup"><span data-stu-id="e54ee-106">The **ListChanged** event implements the **ListChangedEventHandler** delegate of the <xref:System.ComponentModel> namespace and takes as input a <xref:System.ComponentModel.ListChangedEventArgs> object.</span></span> <span data-ttu-id="e54ee-107">Определить, какой тип изменений <xref:System.ComponentModel.ListChangedType> произошел, используя значение перечисления в свойстве **ListChangedType** объекта **ListChangedEventArgs.**</span><span class="sxs-lookup"><span data-stu-id="e54ee-107">You can determine what type of change has occurred using the <xref:System.ComponentModel.ListChangedType> enumeration value in the **ListChangedType** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="e54ee-108">Для изменений, связанных с добавлением, удалением или перемещением строк, новый индекс добавленной или перемещенной строки и предыдущий индекс удаленной строки можно получить с помощью свойства **NewIndex** объекта **ListChangedEventArgs.**</span><span class="sxs-lookup"><span data-stu-id="e54ee-108">For changes that involve adding, deleting, or moving rows, the new index of the added or moved row and the previous index of the deleted row can be accessed using the **NewIndex** property of the **ListChangedEventArgs** object.</span></span> <span data-ttu-id="e54ee-109">В случае перемещенной строки предыдущий индекс перемещенной строки может быть доступен с помощью свойства **OldIndex** объекта **ListChangedEventArgs.**</span><span class="sxs-lookup"><span data-stu-id="e54ee-109">In the case of a moved row, the previous index of the moved row can be accessed using the **OldIndex** property of the **ListChangedEventArgs** object.</span></span>  
  
 <span data-ttu-id="e54ee-110">**DataViewManager** также предоставляет событие **ListChanged,** чтобы уведомить вас, если таблица была добавлена или удалена, или если было внесено изменение в сбор **отношений** базового **DataSet.**</span><span class="sxs-lookup"><span data-stu-id="e54ee-110">The **DataViewManager** also exposes a **ListChanged** event to notify you if a table has been added or removed, or if a change has been made to the **Relations** collection of the underlying **DataSet**.</span></span>  
  
 <span data-ttu-id="e54ee-111">В следующем примере кода показано, как добавить обработчик событий **ListChanged.**</span><span class="sxs-lookup"><span data-stu-id="e54ee-111">The following code example shows how to add a **ListChanged** event handler.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="e54ee-112">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e54ee-112">See also</span></span>

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [<span data-ttu-id="e54ee-113">Объекты DataView</span><span class="sxs-lookup"><span data-stu-id="e54ee-113">DataViews</span></span>](dataviews.md)
- [<span data-ttu-id="e54ee-114">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e54ee-114">ADO.NET Overview</span></span>](../ado-net-overview.md)
