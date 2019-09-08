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
# <a name="handling-dataset-events"></a>Обработка событий наборов данных
Объект <xref:System.Data.DataSet> предоставляет три события: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized>и <xref:System.Data.DataSet.MergeFailed>.  
  
## <a name="the-mergefailed-event"></a>Событие MergeFailed  
 Наиболее часто используемым событием объекта `DataSet` является `MergeFailed`, которое вызывается, когда возникает конфликт в схеме объектов `DataSet` , подвергнутых слиянию. Это происходит, когда целевой и исходный объекты <xref:System.Data.DataRow> имеют одинаковое значение первичного ключа, и свойству <xref:System.Data.DataSet.EnforceConstraints%2A> присваивается значение `true`. Например, если столбцы первичного ключа таблицы, подвергнутые слиянию, совпадают в таблицах двух объектов `DataSet` , то возникает исключение и вызывается событие `MergeFailed` . Объект <xref:System.Data.MergeFailedEventArgs> , переданный событию `MergeFailed` , имеет свойство <xref:System.Data.MergeFailedEventArgs.Conflict%2A> , определяющее конфликт в схеме между двумя объектами `DataSet` , и свойство <xref:System.Data.MergeFailedEventArgs.Table%2A> , определяющее имя таблицы, участвующей в конфликте.  
  
 В следующем фрагменте кода показан способ добавления обработчика события `MergeFailed` .  
  
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
  
## <a name="the-initialized-event"></a>Инициализированное событие  
 Событие <xref:System.Data.DataSet.Initialized> происходит после инициализации нового экземпляра `DataSet` конструктором `DataSet`.  
  
 Свойство <xref:System.Data.DataSet.IsInitialized%2A> возвращает значение `true` , если `DataSet` выполнил инициализацию. В противном случае оно возвращает значение `false`. Метод <xref:System.Data.DataSet.BeginInit%2A> , который начинает инициализацию `DataSet`, присваивает свойству <xref:System.Data.DataSet.IsInitialized%2A> значение `false`. Метод <xref:System.Data.DataSet.EndInit%2A> , который заканчивает инициализацию `DataSet`, присваивает свойству значение `true`. Эти методы используются средой разработки Visual Studio для инициализации `DataSet` , которая используется другим компонентом. Они редко используются в коде.  
  
## <a name="the-disposed-event"></a>Удаленное событие  
 `DataSet` является производным от класса <xref:System.ComponentModel.MarshalByValueComponent> , который предоставляет и метод <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> , и событие <xref:System.ComponentModel.MarshalByValueComponent.Disposed> . <xref:System.ComponentModel.MarshalByValueComponent.Disposed> Событие добавляет обработчик событий для прослушивания ликвидированного события в компоненте. Если требуется выполнить код <xref:System.ComponentModel.MarshalByValueComponent.Disposed> при <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A> вызове метода, можно использовать событие. `DataSet` <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>Освобождает ресурсы, используемые <xref:System.ComponentModel.MarshalByValueComponent>.  
  
> [!NOTE]
> Объекты `DataSet` <xref:System.ComponentModel.MarshalByValueComponent> и `DataTable` наследуются от и поддерживают интерфейс<xref:System.Runtime.Serialization.ISerializable> для удаленного взаимодействия. Это единственные объекты ADO.NET, которые разрешают удаленное взаимодействие. Дополнительные сведения см. в разделе [удаленное взаимодействие .NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/72x4h507(v=vs.100)).  
  
 Сведения о других событиях `DataSet`, доступных при работе с, см. в разделе [Обработка событий DataTable](handling-datatable-events.md) и [Обработка событий DataAdapter](../handling-dataadapter-events.md).  
  
## <a name="see-also"></a>См. также

- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Проверка данных](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/t3b36awf(v=vs.120))
- [Извлечение и изменение данных в ADO.NET](../retrieving-and-modifying-data.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
