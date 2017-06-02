---
title: "Обработка событий наборов данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54edefe0-bc38-419b-b486-3d8a0c356f13
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Обработка событий наборов данных
Объект <xref:System.Data.DataSet> предоставляет три события: <xref:System.ComponentModel.MarshalByValueComponent.Disposed>, <xref:System.Data.DataSet.Initialized> и <xref:System.Data.DataSet.MergeFailed>.  
  
## Событие MergeFailed  
 Наиболее часто используемым событием объекта `DataSet` является `MergeFailed`, которое вызывается, когда возникает конфликт в схеме объектов `DataSet`, подвергнутых слиянию. Это происходит, когда целевой и исходный объекты <xref:System.Data.DataRow> имеют одинаковое значение первичного ключа, и свойству <xref:System.Data.DataSet.EnforceConstraints%2A> присваивается значение `true`. Например, если столбцы первичного ключа таблицы, подвергнутые слиянию, совпадают в таблицах двух объектов `DataSet`, то возникает исключение и вызывается событие `MergeFailed`. Объект <xref:System.Data.MergeFailedEventArgs>, переданный событию `MergeFailed`, имеет свойство <xref:System.Data.MergeFailedEventArgs.Conflict%2A>, определяющее конфликт в схеме между двумя объектами `DataSet`, и свойство <xref:System.Data.MergeFailedEventArgs.Table%2A>, определяющее имя таблицы, участвующей в конфликте.  
  
 В следующем фрагменте кода показан способ добавления обработчика события `MergeFailed`.  
  
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
  
## Инициализированное событие  
 Событие <xref:System.Data.DataSet.Initialized> происходит после инициализации нового экземпляра `DataSet` конструктором `DataSet`.  
  
 Свойство <xref:System.Data.DataSet.IsInitialized%2A> возвращает значение `true`, если `DataSet` выполнил инициализацию. В противном случае оно возвращает значение `false`. Метод <xref:System.Data.DataSet.BeginInit%2A>, который начинает инициализацию `DataSet`, присваивает свойству <xref:System.Data.DataSet.IsInitialized%2A> значение `false`. Метод <xref:System.Data.DataSet.EndInit%2A>, который заканчивает инициализацию `DataSet`, присваивает свойству значение `true`. Эти методы используются средой разработки [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] для инициализации объекта `DataSet`, который используется другим компонентом. Они редко используются в коде.  
  
## Удаленное событие  
 `DataSet` является производным от класса <xref:System.ComponentModel.MarshalByValueComponent>, который предоставляет и метод <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>, и событие <xref:System.ComponentModel.MarshalByValueComponent.Disposed>. Событие <xref:System.ComponentModel.MarshalByValueComponent.Disposed>добавляет обработчик события для прослушивания удаленного события компонента. Событие <xref:System.ComponentModel.MarshalByValueComponent.Disposed>объекта `DataSet` может быть использовано в том случае, если необходимо выполнять какой\-либо код при вызове метода <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>. Метод <xref:System.ComponentModel.MarshalByValueComponent.Dispose%2A>освобождает все ресурсы, занятые объектом <xref:System.ComponentModel.MarshalByValueComponent>.  
  
> [!NOTE]
>  Объекты `DataSet` и `DataTable` наследуются от <xref:System.ComponentModel.MarshalByValueComponent>и поддерживают интерфейс <xref:System.Runtime.Serialization.ISerializable> для удаленного взаимодействия. Это единственные объекты ADO.NET, которые разрешают удаленное взаимодействие. Для получения дополнительной информации см. [Remote Objects](http://msdn.microsoft.com/ru-ru/515686e6-0a8d-42f7-8188-73abede57c58).  
  
 Сведения об остальных событиях, доступных при работе с `DataSet`, см. в разделах [Обработка событий DataTable](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/handling-datatable-events.md) и [Обработка событий DataAdapter](../../../../../docs/framework/data/adonet/handling-dataadapter-events.md).  
  
## См. также  
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Проверка данных](../Topic/Validating%20Data.md)   
 [Получение и изменение данных в ADO.NET](../../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)   
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)