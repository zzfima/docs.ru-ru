---
title: "Обработка событий DataView | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e5675663-fc91-4e0d-87a9-481b25b64c0f
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Обработка событий DataView
Событие <xref:System.Data.DataView.ListChanged> объекта <xref:System.Data.DataView> используется для определения того, было ли обновлено представление.  К обновлениям, которые вызывают это событие, относятся добавление, удаление или изменение строки в базовой таблице, добавление или удаление столбца из схемы базовой таблицы, изменение в родительской или дочерней связи.  Событие **ListChanged** также уведомляет о том, что рассматриваемый список строк существенно изменился в результате применения нового порядка сортировки или фильтра.  
  
 В событии **ListChanged** реализуется делегат **ListChangedEventHandler** пространства имен <xref:System.ComponentModel> и в качестве входа принимается объект <xref:System.ComponentModel.ListChangedEventArgs>.  Определить тип произошедшего изменения можно с помощью значения перечисления <xref:System.ComponentModel.ListChangedType> в свойстве **ListChangedType** объекта **ListChangedEventArgs**.  Что касается изменений, которые включают добавление, удаление или перемещение строк, то доступ к новому индексу добавленной или перемещенной строки и к прежнему индексу удаленной строки можно получить с помощью свойства **NewIndex** объекта **ListChangedEventArgs**.  В том случае, если произошло перемещение строки, доступ к прежнему индексу перемещенной строки можно получить с помощью свойства **OldIndex** объекта **ListChangedEventArgs**.  
  
 Объект **DataViewManager** предоставляет событие **ListChanged**, которое позволяет передавать уведомление о добавлении или удалении таблицы либо о внесении изменения в коллекцию **Relations** базового объекта **DataSet**.  
  
 В следующем примере кода показано добавление обработчика событий **ListChanged**.  
  
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
  
## См. также  
 <xref:System.Data.DataView>   
 <xref:System.ComponentModel.ListChangedEventHandler>   
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)