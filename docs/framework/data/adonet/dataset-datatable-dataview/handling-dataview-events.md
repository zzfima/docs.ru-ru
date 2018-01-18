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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: bf3b02227de5068a031cedb73269148c7d5262a0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2018
---
# <a name="handling-dataview-events"></a>Обработка событий DataView
Событие <xref:System.Data.DataView.ListChanged> объекта <xref:System.Data.DataView> используется для определения того, было ли обновлено представление. К обновлениям, которые вызывают это событие, относятся добавление, удаление или изменение строки в базовой таблице, добавление или удаление столбца из схемы базовой таблицы, изменение в родительской или дочерней связи. **ListChanged** событий также уведомляет пользователя, если список строк существенно изменился из-за применения нового порядка сортировки или фильтра.  
  
 **ListChanged** реализует событие **ListChangedEventHandler** делегат типа <xref:System.ComponentModel> пространства имен и принимает в качестве ввода <xref:System.ComponentModel.ListChangedEventArgs> объекта. Чтобы выяснить, какие изменения фиксируется с помощью <xref:System.ComponentModel.ListChangedType> значения перечисления в **ListChangedType** свойство **ListChangedEventArgs** объекта. Для внесения изменений, которые включают добавление, удаление или перемещение строк, новому индексу добавленной или перемещенной строки и к прежнему индексу удаленной строки можно осуществлять с помощью **NewIndex** свойство **ListChangedEventArgs** объекта. В случае перемещение строки, к прежнему индексу перемещенной строки можно осуществлять с помощью **OldIndex** свойство **ListChangedEventArgs** объекта.  
  
 **DataViewManager** также предоставляет **ListChanged** событий для уведомления о том, если при добавлении или удалении таблицы или изменений и **отношений** коллекцию базовый **набора данных**.  
  
 В следующем примере кода показано, как добавить **ListChanged** обработчика событий.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataView>  
 <xref:System.ComponentModel.ListChangedEventHandler>  
 [Объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/dataviews.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
