---
title: Практическое руководство. Создание и привязка ObservableCollection
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], ObservableCollection class
- notifications [WPF]
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
ms.openlocfilehash: 8db9f2051a0401e01f233f9c959e015eb657bdac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69965468"
---
# <a name="how-to-create-and-bind-to-an-observablecollection"></a>Практическое руководство. Создание и привязка ObservableCollection
В этом примере показано, как создать и привязать коллекцию, производную от <xref:System.Collections.ObjectModel.ObservableCollection%601> класса, который представляет собой класс коллекции, который предоставляет уведомления при добавлении или удалении элементов.  
  
## <a name="example"></a>Пример  
 В следующем примере показана реализация коллекции `NameList`.  
  
```csharp  
public class NameList : ObservableCollection<PersonName>  
{  
    public NameList() : base()  
    {  
        Add(new PersonName("Willa", "Cather"));  
        Add(new PersonName("Isak", "Dinesen"));  
        Add(new PersonName("Victor", "Hugo"));  
        Add(new PersonName("Jules", "Verne"));  
    }  
  }  
  
  public class PersonName  
  {  
      private string firstName;  
      private string lastName;  
  
      public PersonName(string first, string last)  
      {  
          this.firstName = first;  
          this.lastName = last;  
      }  
  
      public string FirstName  
      {  
          get { return firstName; }  
          set { firstName = value; }  
      }  
  
      public string LastName  
      {  
          get { return lastName; }  
          set { lastName = value; }  
      }  
  }  
```  
  
```vb  
Public Class NameList  
    Inherits ObservableCollection(Of PersonName)  
  
    ' Methods  
    Public Sub New()  
        MyBase.Add(New PersonName("Willa", "Cather"))  
        MyBase.Add(New PersonName("Isak", "Dinesen"))  
        MyBase.Add(New PersonName("Victor", "Hugo"))  
        MyBase.Add(New PersonName("Jules", "Verne"))  
    End Sub  
  
End Class  
  
Public Class PersonName  
    ' Methods  
    Public Sub New(ByVal first As String, ByVal last As String)  
        Me._firstName = first  
        Me._lastName = last  
    End Sub  
  
    ' Properties  
    Public Property FirstName() As String  
        Get  
            Return Me._firstName  
        End Get  
        Set(ByVal value As String)  
            Me._firstName = value  
        End Set  
    End Property  
  
    Public Property LastName() As String  
        Get  
            Return Me._lastName  
        End Get  
        Set(ByVal value As String)  
            Me._lastName = value  
        End Set  
    End Property  
  
    ' Fields  
    Private _firstName As String  
    Private _lastName As String  
End Class  
```  
  
 Коллекцию можно сделать доступной для привязки так же, как и с другими объектами среды CLR, как описано в разделе [обеспечение доступности данных для привязки в XAML](how-to-make-data-available-for-binding-in-xaml.md). Например, можно создать экземпляр коллекции в [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] и указать коллекцию в качестве ресурса, как показано ниже.  
  
```xaml  
<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  xmlns:c="clr-namespace:SDKSample"  
  x:Class="SDKSample.Window1"  
  Width="400"  
  Height="280"  
  Title="MultiBinding Sample">  
  
  <Window.Resources>  
    <c:NameList x:Key="NameListData"/>  
  
...  
  
</Window.Resources>  
```  
  
 Затем можно выполнить привязку к коллекции:  
  
```xaml  
<ListBox Width="200"  
         ItemsSource="{Binding Source={StaticResource NameListData}}"  
         ItemTemplate="{StaticResource NameItemTemplate}"  
         IsSynchronizedWithCurrentItem="True"/>  
```  
  
 Определение `NameItemTemplate` здесь не показано.  
  
> [!NOTE]
> Объекты в коллекции должны удовлетворять требованиям, описанным в разделе [Общие сведения об источниках привязки](binding-sources-overview.md). В частности, если вы используете <xref:System.Windows.Data.BindingMode.OneWay> или <xref:System.Windows.Data.BindingMode.TwoWay> ( [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] например, хотите обновлять, когда исходные свойства изменяются динамически), необходимо реализовать подходящий механизм уведомления об изменении свойств, например <xref:System.ComponentModel.INotifyPropertyChanged>интерфейс.  
  
 Дополнительные сведения см. в разделе "Привязка к коллекциям" в разделе [Общие сведения о привязке данных](data-binding-overview.md).  
  
## <a name="see-also"></a>См. также

- [Сортировка данных в представлении](how-to-sort-data-in-a-view.md)
- [Фильтрация данных в представлении](how-to-filter-data-in-a-view.md)
- [Сортировка и группировка данных с помощью представления в XAML](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [Общие сведения о привязке данных](data-binding-overview.md)
- [Разделы практического руководства](data-binding-how-to-topics.md)
