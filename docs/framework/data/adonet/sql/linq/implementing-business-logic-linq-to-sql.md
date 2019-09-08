---
title: Реализация бизнес-логики (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c4577590-7b12-42e1-84a6-95aa2562727e
ms.openlocfilehash: 5261aab1ef6641651f856b8ebb024f64ad32ee59
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781439"
---
# <a name="implementing-business-logic-linq-to-sql"></a>Реализация бизнес-логики (LINQ to SQL)
Термин "бизнес-логика" в данном разделе относится к любым пользовательским правилам или проверкам, которые применяются к данным перед их вставкой, обновлением или удалением в базе данных. Бизнес-логику также иногда называют терминами "бизнес-правила" или "логика домена". В многоуровневых приложениях бизнес-логика реализуется в виде логического уровня, и ее можно изменять независимо от уровня представления данных или уровня доступа к данным. Бизнес-логика может вызываться уровнем доступа к данным перед обновлением, вставкой или удалением данных в базе данных или после выполнения этих операций.  
  
 Бизнес-логика может представлять собой простую схему проверки совместимости типа поля с типом столбца таблицы. Она также может состоять из набора объектов, взаимодействующих произвольным и довольно сложным образом. Правила могут реализовываться в виде хранимых процедур для базы данных или в качестве объектов, содержащихся в памяти. Однако реализация [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] бизнес-логики позволяет использовать разделяемые классы и разделяемые методы для отделения бизнес-логики от кода доступа к данным.  
  
## <a name="how-linq-to-sql-invokes-your-business-logic"></a>Способы вызова бизнес-логики технологией LINQ to SQL  
 При создании класса сущности во время разработки либо вручную, либо с помощью реляционный конструктор объектов или SQLMetal он определяется как разделяемый класс. Это означает, что в отдельном файле с исходным кодом можно определить другую часть этого класса сущностей, содержащего пользовательскую бизнес-логику. Во время компиляции обе части объединяются в один класс. Но если вы хотите повторно создать классы сущностей с помощью реляционный конструктор объектов или SQLMetal, это можно сделать, и ваша часть класса не будет изменена.  
  
 Разделяемые классы, которые определяют сущности, и класс <xref:System.Data.Linq.DataContext> содержат разделяемые методы. Эти методы являются точками расширения, которые можно использовать для применения бизнес-логики перед обновлением, вставкой или удалением сущности или свойства сущности, а также после выполнения этих операций. Разделяемые методы можно рассматривать как события времени компиляции. Генератор кода определяет сигнатуру метода и вызывает эти методы в методах доступа к свойствам "get" и "set", конструкторе `DataContext` и в некоторых случаях неявным образом при вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A>. Однако, если не реализовать определенный разделяемый метод, все ссылки на него и определение удаляются во время компиляции.  
  
 В определении реализации, созданном в отдельном файле с исходным кодом, можно выполнить любую требуемую пользовательскую логику. Можно использовать разделяемый класс в качестве уровня домена или вызывать его из определения реализации разделяемого метода в отдельном объекте или объектах. В любом случае бизнес-логика полностью отделена как от кода уровня доступа к данным, так и от кода уровня представления данных.  
  
## <a name="a-closer-look-at-the-extensibility-points"></a>Более подробное рассмотрение точек расширения  
 В следующем примере показана часть кода, созданного реляционный конструктор объектов для `DataContext` класса, который имеет две таблицы: `Customers` и `Orders`. Обратите внимание, что методы "Insert", "Update" и "Delete" определены для каждой таблицы в классе.  
  
```vb  
Partial Public Class Northwnd  
    Inherits System.Data.Linq.DataContext  
  
    Private Shared mappingSource As _  
        System.Data.Linq.Mapping.MappingSource = New _  
        AttributeMappingSource  
  
    #Region "Extensibility Method Definitions"  
    Partial Private Sub OnCreated()  
    End Sub  
    Partial Private Sub InsertCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub UpdateCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub DeleteCustomer(instance As Customer)  
    End Sub  
    Partial Private Sub InsertOrder(instance As [Order])  
    End Sub  
    Partial Private Sub UpdateOrder(instance As [Order])  
    End Sub  
    Partial Private Sub DeleteOrder(instance As [Order])  
    End Sub  
    #End Region  
```  
  
```csharp  
public partial class MyNorthWindDataContext : System.Data.Linq.DataContext  
    {  
        private static System.Data.Linq.Mapping.MappingSource mappingSource = new AttributeMappingSource();  
  
        #region Extensibility Method Definitions  
        partial void OnCreated();  
        partial void InsertCustomer(Customer instance);  
        partial void UpdateCustomer(Customer instance);  
        partial void DeleteCustomer(Customer instance);  
        partial void InsertOrder(Order instance);  
        partial void UpdateOrder(Order instance);  
        partial void DeleteOrder(Order instance);  
        #endregion  
```  
  
 Если реализовать методы "Insert", "Update" и "Delete" в разделяемом классе, то при вызове метода [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] среда выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A> вызовет их вместо собственных методов, используемых по умолчанию. Это позволяет переопределить поведение, реализуемое по умолчанию для операций создания, чтения, обновления и удаления. Дополнительные сведения см. в разделе [Пошаговое руководство: Настройка поведения операций вставки, обновления и удаления классов](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes)сущностей.  
  
 Метод `OnCreated` вызывается в классе конструктора.  
  
```vb  
Public Sub New(ByVal connection As String)  
    MyBase.New(connection, mappingSource)  
    OnCreated()  
End Sub  
```  
  
```csharp  
public MyNorthWindDataContext(string connection) :  
            base(connection, mappingSource)  
        {  
            OnCreated();  
        }  
```  
  
 Классы сущностей имеют три метода, вызываемые средой выполнения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] при создании, загрузке и проверки сущности (при вызове метода `SubmitChanges`). Классы сущностей также имеют два разделяемых метода для каждого свойства. Один метод вызывается перед заданием свойства, а другой — после. В следующем примере кода демонстрируются некоторые методы, созданные для класса `Customer`.  
  
```vb  
#Region "Extensibility Method Definitions"  
    Partial Private Sub OnLoaded()  
    End Sub  
    Partial Private Sub OnValidate(action As _  
        System.Data.Linq.ChangeAction)  
    End Sub  
    Partial Private Sub OnCreated()  
    End Sub  
    Partial Private Sub OnCustomerIDChanging(value As String)  
    End Sub  
    Partial Private Sub OnCustomerIDChanged()  
    End Sub  
    Partial Private Sub OnCompanyNameChanging(value As String)  
    End Sub  
    Partial Private Sub OnCompanyNameChanged()  
    End Sub  
' ...Additional Changing/Changed methods for each property.  
```  
  
```csharp  
#region Extensibility Method Definitions  
    partial void OnLoaded();  
    partial void OnValidate();  
    partial void OnCreated();  
    partial void OnCustomerIDChanging(string value);  
    partial void OnCustomerIDChanged();  
    partial void OnCompanyNameChanging(string value);  
    partial void OnCompanyNameChanged();  
// ...additional Changing/Changed methods for each property  
```  
  
 Эти методы вызывается в методе доступа "set" для свойства, как показано в следующем примере для свойства `CustomerID`:  
  
```vb  
Public Property CustomerID() As String  
    Set  
        If (String.Equals(Me._CustomerID, value) = False) Then  
            Me.OnCustomerIDChanging(value)  
            Me.SendPropertyChanging()  
            Me._CustomerID = value  
            Me.SendPropertyChanged("CustomerID")  
            Me.OnCustomerIDChanged()  
        End If  
    End Set  
End Property  
```  
  
```csharp  
public string CustomerID  
{  
    set  
    {  
        if ((this._CustomerID != value))  
        {  
            this.OnCustomerIDChanging(value);  
            this.SendPropertyChanging();  
            this._CustomerID = value;  
            this.SendPropertyChanged("CustomerID");  
            this.OnCustomerIDChanged();  
        }  
     }  
}  
```  
  
 В пользовательской части класса создается определение реализации метода. В Visual Studio после ввода `partial` вы увидите IntelliSense для определений методов в другой части класса.  
  
```vb  
Partial Public Class Customer  
    Private Sub OnCustomerIDChanging(value As String)  
        ' Perform custom validation logic here.  
    End Sub  
End Class  
```  
  
```csharp  
partial class Customer   
    {  
        partial void OnCustomerIDChanging(string value)  
        {  
            //Perform custom validation logic here.  
        }  
    }  
```  
  
 Дополнительные сведения о добавлении бизнес-логики в приложение с помощью разделяемых методов см. в следующих разделах.  
  
 [Практическое руководство. Добавление проверки в классы сущностей](/visualstudio/data-tools/how-to-add-validation-to-entity-classes)  
  
 [Пошаговое руководство: Настройка операций вставки, обновления и удаления в классах сущностей](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes)  
  
 [Пошаговое руководство: Добавление проверки в классы сущностей](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb629301(v=vs.120))  
  
## <a name="see-also"></a>См. также

- [Разделяемые классы и методы](../../../../../csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)
- [Разделяемые методы](../../../../../visual-basic/programming-guide/language-features/procedures/partial-methods.md)
- [Средства LINQ to SQL в Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [SqlMetal.exe (средство создания кода)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
