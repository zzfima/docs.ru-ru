---
title: Обработка событий наборов данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
ms.openlocfilehash: b2b71dac58838a826933af570934bf4bbb35e025
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784612"
---
# <a name="handling-dataset-events"></a><span data-ttu-id="e5ae5-102">Обработка событий наборов данных</span><span class="sxs-lookup"><span data-stu-id="e5ae5-102">Handling DataSet Events</span></span>
<span data-ttu-id="e5ae5-103">Объект <xref:System.Data.DataSet> предоставляет три события: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>и <xref:System.Data.DataSet.MergeFailed>.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-103">The <xref:System.Data.DataSet> object provides three events: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>, and <xref:System.Data.DataSet.MergeFailed>.</span></span>  
  
## <a name="the-mergefailed-event"></a><span data-ttu-id="e5ae5-104">Событие MergeFailed</span><span class="sxs-lookup"><span data-stu-id="e5ae5-104">The MergeFailed Event</span></span>  
 <span data-ttu-id="e5ae5-105">Наиболее часто используемым событием объекта `DataSet` является `MergeFailed`, которое вызывается, когда возникает конфликт в схеме объектов `DataSet` , подвергнутых слиянию.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-105">The most commonly used event of the `DataSet` object is `MergeFailed`, which is raised when the schema of the `DataSet` objects being merged are in conflict.</span></span> <span data-ttu-id="e5ae5-106">Это происходит, когда целевой и исходный объекты <xref:System.Data.DataRow> имеют одинаковое значение первичного ключа, и свойству <xref:System.Data.DataSet.EnforceConstraints%2A> присваивается значение `true`.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-106">This occurs when a target and source <xref:System.Data.DataRow> have the same primary key value, and the <xref:System.Data.DataSet.EnforceConstraints%2A> property is set to `true`.</span></span> <span data-ttu-id="e5ae5-107">Например, если столбцы первичного ключа таблицы, подвергнутые слиянию, совпадают в таблицах двух объектов `DataSet` , то возникает исключение и вызывается событие `MergeFailed` .</span><span class="sxs-lookup"><span data-stu-id="e5ae5-107">For example, if the primary key columns of a table being merged are the same between the tables in the two `DataSet` objects, an exception is thrown and the `MergeFailed` event is raised.</span></span> <span data-ttu-id="e5ae5-108">Объект <xref:System.Data.MergeFailedEventArgs> , переданный событию `MergeFailed` , имеет свойство <xref:System.Data.MergeFailedEventArgs.Conflict%2A> , определяющее конфликт в схеме между двумя объектами `DataSet` , и свойство <xref:System.Data.MergeFailedEventArgs.Table%2A> , определяющее имя таблицы, участвующей в конфликте.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-108">The <xref:System.Data.MergeFailedEventArgs> object passed to the `MergeFailed` event have a <xref:System.Data.MergeFailedEventArgs.Conflict%2A> property that identifies the conflict in schema between the two `DataSet` objects, and a <xref:System.Data.MergeFailedEventArgs.Table%2A> property that identifies the name of the table in conflict.</span></span>  
  
 <span data-ttu-id="e5ae5-109">В следующем фрагменте кода показан способ добавления обработчика события `MergeFailed` .</span><span class="sxs-lookup"><span data-stu-id="e5ae5-109">The following code fragment demonstrates how to add an event handler for the `MergeFailed` event.</span></span>  
  
```vb  
AddHandler workDS.MergeFailed, New MergeFailedEventHandler( _  
  AddressOf DataSetMergeFailed)  
  
Private Shared Sub DataSetMergeFailed(  _  
  sender As Object,args As MergeFailedEventArgs)  
  Console.WriteLine("Merge failed for table " & args.Table.TableName)  
  Console.WriteLine("Conflict = " & args.Conflict)  
End Sub  
```  
  
```csharp  
workDS.MergeFailed += new MergeFailedEventHandler(DataSetMergeFailed);  
  
private static void DataSetMergeFailed(  
  object sender, MergeFailedEventArgs args)  
{  
  Console.WriteLine("Merge failed for table " + args.Table.TableName);  
  Console.WriteLine("Conflict = " + args.Conflict);  
}  
```  
  
## <a name="the-initialized-event"></a><span data-ttu-id="e5ae5-110">Инициализированное событие</span><span class="sxs-lookup"><span data-stu-id="e5ae5-110">The Initialized Event</span></span>  
 <span data-ttu-id="e5ae5-111">Событие <xref:System.Data.DataSet.Initialized> происходит после инициализации нового экземпляра `DataSet` конструктором `DataSet`.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-111">The <xref:System.Data.DataSet.Initialized> event occurs after the `DataSet` constructor initializes a new instance of the `DataSet`.</span></span>  
  
 <span data-ttu-id="e5ae5-112">Свойство <xref:System.Data.DataSet.IsInitialized%2A> возвращает значение `true` , если `DataSet` выполнил инициализацию. В противном случае оно возвращает значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-112">The <xref:System.Data.DataSet.IsInitialized%2A> property returns `true` if the `DataSet` has completed initialization; otherwise it returns `false`.</span></span> <span data-ttu-id="e5ae5-113">Метод <xref:System.Data.DataSet.BeginInit%2A> , который начинает инициализацию `DataSet`, присваивает свойству <xref:System.Data.DataSet.IsInitialized%2A> значение `false`.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-113">The <xref:System.Data.DataSet.BeginInit%2A> method, which begins the initialization of a `DataSet`, sets <xref:System.Data.DataSet.IsInitialized%2A> to `false`.</span></span> <span data-ttu-id="e5ae5-114">Метод <xref:System.Data.DataSet.EndInit%2A> , который заканчивает инициализацию `DataSet`, присваивает свойству значение `true`.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-114">The <xref:System.Data.DataSet.EndInit%2A> method, which ends the initialization of the `DataSet`, sets it to `true`.</span></span> <span data-ttu-id="e5ae5-115">Эти методы используются средой разработки Visual Studio для инициализации `DataSet` , которая используется другим компонентом.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-115">These methods are used by the Visual Studio design environment to initialize a `DataSet` that is being used by another component.</span></span> <span data-ttu-id="e5ae5-116">Они редко используются в коде.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-116">You will not commonly use them in your code.</span></span>  
  
## <a name="the-disposed-event"></a><span data-ttu-id="e5ae5-117">Удаленное событие</span><span class="sxs-lookup"><span data-stu-id="e5ae5-117">The Disposed Event</span></span>  
 <span data-ttu-id="e5ae5-118">`DataSet` является производным от класса <xref:System.ComponentModel.MarshalByValueComponent> , который предоставляет и метод <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> , и событие <xref:System.ComponentModel.MarshalByValueComponent.Disposed> .</span><span class="sxs-lookup"><span data-stu-id="e5ae5-118">`DataSet` is derived from the <xref:System.ComponentModel.MarshalByValueComponent> class, which exposes both the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method and the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event.</span></span> <span data-ttu-id="e5ae5-119"><xref:System.ComponentModel.MarshalByValueComponent.Disposed> Событие добавляет обработчик событий для прослушивания ликвидированного события в компоненте.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-119">The <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event adds an event handler to listen to the disposed event on the component.</span></span> <span data-ttu-id="e5ae5-120">Если требуется выполнить код <xref:System.ComponentModel.MarshalByValueComponent.Disposed> при <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> вызове метода, можно использовать событие. `DataSet`</span><span class="sxs-lookup"><span data-stu-id="e5ae5-120">You can use the <xref:System.ComponentModel.MarshalByValueComponent.Disposed> event of a `DataSet` if you want to execute code when the <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> method is called.</span></span> <span data-ttu-id="e5ae5-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>Освобождает ресурсы, используемые <xref:System.ComponentModel.MarshalByValueComponent>.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-121"><xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> releases the resources used by the <xref:System.ComponentModel.MarshalByValueComponent>.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e5ae5-122">Объекты `DataSet` <xref:System.ComponentModel.MarshalByValueComponent> и `DataTable` наследуются от и поддерживают интерфейс<xref:System.Runtime.Serialization.ISerializable> для удаленного взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-122">The `DataSet` and `DataTable` objects inherit from <xref:System.ComponentModel.MarshalByValueComponent> and support the <xref:System.Runtime.Serialization.ISerializable> interface for remoting.</span></span> <span data-ttu-id="e5ae5-123">Это единственные объекты ADO.NET, которые разрешают удаленное взаимодействие.</span><span class="sxs-lookup"><span data-stu-id="e5ae5-123">These are the only ADO.NET objects that can be remoted.</span></span> <span data-ttu-id="e5ae5-124">Дополнительные сведения см. в разделе [удаленное взаимодействие .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="e5ae5-124">For more information, see [.NET Remoting](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).</span></span>  
  
 <span data-ttu-id="e5ae5-125">Сведения о других событиях `DataSet`, доступных при работе с, см. в разделе [Обработка событий DataTable](handling-datatable-events.md) и [Обработка событий DataAdapter](../handling-dataadapter-events.md).</span><span class="sxs-lookup"><span data-stu-id="e5ae5-125">For information about other events available when working with a `DataSet`, see [Handling DataTable Events](handling-datatable-events.md) and [Handling DataAdapter Events](../handling-dataadapter-events.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5ae5-126">См. также</span><span class="sxs-lookup"><span data-stu-id="e5ae5-126">See also</span></span>

- [<span data-ttu-id="e5ae5-127">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="e5ae5-127">DataSets, DataTables, and DataViews</span></span>](index.md)
- <span data-ttu-id="e5ae5-128">[Проверка данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="e5ae5-128">[Validating Data](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))</span></span>
- [<span data-ttu-id="e5ae5-129">Извлечение и изменение данных в ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e5ae5-129">Retrieving and Modifying Data in ADO.NET</span></span>](../retrieving-and-modifying-data.md)
- [<span data-ttu-id="e5ae5-130">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e5ae5-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
