---
title: Создание набора данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: d496167b7bce31491402414c43ae0bcdee423b89
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786505"
---
# <a name="creating-a-dataset"></a><span data-ttu-id="c31cf-102">Создание набора данных</span><span class="sxs-lookup"><span data-stu-id="c31cf-102">Creating a DataSet</span></span>
<span data-ttu-id="c31cf-103">Экземпляр объекта <xref:System.Data.DataSet> создается путем вызова конструктора <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c31cf-103">You create an instance of a <xref:System.Data.DataSet> by calling the <xref:System.Data.DataSet> constructor.</span></span> <span data-ttu-id="c31cf-104">Кроме того, можно задать аргумент имени.</span><span class="sxs-lookup"><span data-stu-id="c31cf-104">Optionally specify a name argument.</span></span> <span data-ttu-id="c31cf-105">Если имя для объекта <xref:System.Data.DataSet> не задано, то ему присваивается имя «NewDataSet».</span><span class="sxs-lookup"><span data-stu-id="c31cf-105">If you do not specify a name for the <xref:System.Data.DataSet>, the name is set to "NewDataSet".</span></span>  
  
 <span data-ttu-id="c31cf-106">Также можно создать новый объект <xref:System.Data.DataSet> на базе существующего объекта <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c31cf-106">You can also create a new <xref:System.Data.DataSet> based on an existing <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="c31cf-107">Новый объект <xref:System.Data.DataSet> может быть точной копией существующего объекта <xref:System.Data.DataSet>, клоном объекта <xref:System.Data.DataSet>, который копирует реляционную структуру или схему, но не содержит каких-либо данных из существующего объекта <xref:System.Data.DataSet>, или сокращенной версией объекта <xref:System.Data.DataSet>, содержащей только строки из существующего объекта <xref:System.Data.DataSet>, измененные при помощи метода <xref:System.Data.DataSet.GetChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="c31cf-107">The new <xref:System.Data.DataSet> can be an exact copy of the existing <xref:System.Data.DataSet>; a clone of the <xref:System.Data.DataSet> that copies the relational structure or schema but that does not contain any of the data from the existing <xref:System.Data.DataSet>; or a subset of the <xref:System.Data.DataSet>, containing only the modified rows from the existing <xref:System.Data.DataSet> using the <xref:System.Data.DataSet.GetChanges%2A> method.</span></span> <span data-ttu-id="c31cf-108">Дополнительные сведения см. в разделе [копирование содержимого набора данных](copying-dataset-contents.md).</span><span class="sxs-lookup"><span data-stu-id="c31cf-108">For more information, see [Copying DataSet Contents](copying-dataset-contents.md).</span></span>  
  
 <span data-ttu-id="c31cf-109">Следующий пример кода демонстрирует, как построить экземпляр объекта <xref:System.Data.DataSet>.</span><span class="sxs-lookup"><span data-stu-id="c31cf-109">The following code example demonstrates how to construct an instance of a <xref:System.Data.DataSet>.</span></span>  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a><span data-ttu-id="c31cf-110">См. также</span><span class="sxs-lookup"><span data-stu-id="c31cf-110">See also</span></span>

- [<span data-ttu-id="c31cf-111">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="c31cf-111">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="c31cf-112">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="c31cf-112">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="c31cf-113">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="c31cf-113">ADO.NET Overview</span></span>](../ado-net-overview.md)
