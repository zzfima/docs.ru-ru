---
title: Создание набора данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: d2d17056e6dcd29ef9b5c5e8c3024a32fce32bd5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59118187"
---
# <a name="creating-a-dataset"></a><span data-ttu-id="d4197-102">Создание набора данных</span><span class="sxs-lookup"><span data-stu-id="d4197-102">Creating a DataSet</span></span>
<span data-ttu-id="d4197-103">Экземпляр объекта <xref:System.Data.DataSet> создается путем вызова конструктора <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="d4197-103">You create an instance of a <xref:System.Data.DataSet> by calling the <xref:System.Data.DataSet> constructor.</span></span> <span data-ttu-id="d4197-104">Кроме того, можно задать аргумент имени.</span><span class="sxs-lookup"><span data-stu-id="d4197-104">Optionally specify a name argument.</span></span> <span data-ttu-id="d4197-105">Если имя для объекта <xref:System.Data.DataSet> не задано, то ему присваивается имя «NewDataSet».</span><span class="sxs-lookup"><span data-stu-id="d4197-105">If you do not specify a name for the <xref:System.Data.DataSet>, the name is set to "NewDataSet".</span></span>  
  
 <span data-ttu-id="d4197-106">Также можно создать новый объект <xref:System.Data.DataSet> на базе существующего объекта <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="d4197-106">You can also create a new <xref:System.Data.DataSet> based on an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="d4197-107">Новый объект <xref:System.Data.DataSet> может быть точной копией существующего объекта <xref:System.Data.DataSet>, клоном объекта <xref:System.Data.DataSet>, который копирует реляционную структуру или схему, но не содержит каких-либо данных из существующего объекта <xref:System.Data.DataSet>, или сокращенной версией объекта <xref:System.Data.DataSet>, содержащей только строки из существующего объекта <xref:System.Data.DataSet>, измененные при помощи метода <xref:System.Data.DataSet.GetChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="d4197-107">The new <xref:System.Data.DataSet> can be an exact copy of the existing <xref:System.Data.DataSet>; a clone of the <xref:System.Data.DataSet> that copies the relational structure or schema but that does not contain any of the data from the existing <xref:System.Data.DataSet>; or a subset of the <xref:System.Data.DataSet>, containing only the modified rows from the existing <xref:System.Data.DataSet> using the <xref:System.Data.DataSet.GetChanges%2A> method.</span></span> <span data-ttu-id="d4197-108">Дополнительные сведения см. в разделе [копирование содержимого набора данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).</span><span class="sxs-lookup"><span data-stu-id="d4197-108">For more information, see [Copying DataSet Contents](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).</span></span>  
  
 <span data-ttu-id="d4197-109">Следующий пример кода демонстрирует, как построить экземпляр объекта <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="d4197-109">The following code example demonstrates how to construct an instance of a <xref:System.Data.DataSet>.</span></span>  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="d4197-110">См. также</span><span class="sxs-lookup"><span data-stu-id="d4197-110">See also</span></span>

- [<span data-ttu-id="d4197-111">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="d4197-111">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="d4197-112">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="d4197-112">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="d4197-113">Управляемые поставщики ADO.NET и центр разработчиков DataSet</span><span class="sxs-lookup"><span data-stu-id="d4197-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
