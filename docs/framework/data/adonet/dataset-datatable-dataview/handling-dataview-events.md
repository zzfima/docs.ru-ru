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
# <a name="handling-dataview-events"></a>Обработка событий DataView
Событие <xref:System.Data.DataView.ListChanged> объекта <xref:System.Data.DataView> используется для определения того, было ли обновлено представление. К обновлениям, которые вызывают это событие, относятся добавление, удаление или изменение строки в базовой таблице, добавление или удаление столбца из схемы базовой таблицы, изменение в родительской или дочерней связи. Событие **ListChanged** также уведомляет вас, если список строк, которые вы просматриваете, значительно изменился из-за применения нового порядка сортировки или фильтра.  
  
 Событие **ListChanged** реализует делегирование **ListChangedEventHandler** пространства <xref:System.ComponentModel> имен и <xref:System.ComponentModel.ListChangedEventArgs> принимает в качестве ввода объекта. Определить, какой тип изменений <xref:System.ComponentModel.ListChangedType> произошел, используя значение перечисления в свойстве **ListChangedType** объекта **ListChangedEventArgs.** Для изменений, связанных с добавлением, удалением или перемещением строк, новый индекс добавленной или перемещенной строки и предыдущий индекс удаленной строки можно получить с помощью свойства **NewIndex** объекта **ListChangedEventArgs.** В случае перемещенной строки предыдущий индекс перемещенной строки может быть доступен с помощью свойства **OldIndex** объекта **ListChangedEventArgs.**  
  
 **DataViewManager** также предоставляет событие **ListChanged,** чтобы уведомить вас, если таблица была добавлена или удалена, или если было внесено изменение в сбор **отношений** базового **DataSet.**  
  
 В следующем примере кода показано, как добавить обработчик событий **ListChanged.**  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataView>
- <xref:System.ComponentModel.ListChangedEventHandler>
- [Объекты DataView](dataviews.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
