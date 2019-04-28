---
title: Создание набора данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 57629d8f-393e-4677-8b83-29ffde27f5fc
ms.openlocfilehash: d2d17056e6dcd29ef9b5c5e8c3024a32fce32bd5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61879883"
---
# <a name="creating-a-dataset"></a>Создание набора данных
Экземпляр объекта <xref:System.Data.DataSet> создается путем вызова конструктора <xref:System.Data.DataSet>. Кроме того, можно задать аргумент имени. Если имя для объекта <xref:System.Data.DataSet> не задано, то ему присваивается имя «NewDataSet».  
  
 Также можно создать новый объект <xref:System.Data.DataSet> на базе существующего объекта <xref:System.Data.DataSet>. Новый объект <xref:System.Data.DataSet> может быть точной копией существующего объекта <xref:System.Data.DataSet>, клоном объекта <xref:System.Data.DataSet>, который копирует реляционную структуру или схему, но не содержит каких-либо данных из существующего объекта <xref:System.Data.DataSet>, или сокращенной версией объекта <xref:System.Data.DataSet>, содержащей только строки из существующего объекта <xref:System.Data.DataSet>, измененные при помощи метода <xref:System.Data.DataSet.GetChanges%2A>. Дополнительные сведения см. в разделе [копирование содержимого набора данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/copying-dataset-contents.md).  
  
 Следующий пример кода демонстрирует, как построить экземпляр объекта <xref:System.Data.DataSet>.  
  
```vb  
Dim customerOrders As DataSet = New DataSet("CustomerOrders")  
```  
  
```csharp  
DataSet customerOrders = new DataSet("CustomerOrders");  
```  
  
## <a name="see-also"></a>См. также

- [Заполнение набора данных с помощью адаптера данных DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
