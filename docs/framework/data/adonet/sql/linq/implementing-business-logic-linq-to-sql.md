---
title: Реализация бизнес-логики (LINQ to SQL)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: c4577590-7b12-42e1-84a6-95aa2562727e
ms.openlocfilehash: 7e24bf24785538863738fe2c006834a77f47e1ca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496094"
---
# <a name="implementing-business-logic-linq-to-sql"></a><span data-ttu-id="267da-102">Реализация бизнес-логики (LINQ to SQL)</span><span class="sxs-lookup"><span data-stu-id="267da-102">Implementing Business Logic (LINQ to SQL)</span></span>
<span data-ttu-id="267da-103">Термин "бизнес-логика" в данном разделе относится к любым пользовательским правилам или проверкам, которые применяются к данным перед их вставкой, обновлением или удалением в базе данных.</span><span class="sxs-lookup"><span data-stu-id="267da-103">The term "business logic" in this topic refers to any custom rules or validation tests that you apply to data before it is inserted, updated or deleted from the database.</span></span> <span data-ttu-id="267da-104">Бизнес-логику также иногда называют терминами "бизнес-правила" или "логика домена".</span><span class="sxs-lookup"><span data-stu-id="267da-104">Business logic is also sometimes referred to as "business rules" or "domain logic."</span></span> <span data-ttu-id="267da-105">В многоуровневых приложениях бизнес-логика реализуется в виде логического уровня, и ее можно изменять независимо от уровня представления данных или уровня доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="267da-105">In n-tier applications it is typically designed as a logical layer so that it can be modified independently of the presentation layer or data access layer.</span></span> <span data-ttu-id="267da-106">Бизнес-логика может вызываться уровнем доступа к данным перед обновлением, вставкой или удалением данных в базе данных или после выполнения этих операций.</span><span class="sxs-lookup"><span data-stu-id="267da-106">The business logic can be invoked by the data access layer before or after any update, insertion, or deletion of data in the database.</span></span>  
  
 <span data-ttu-id="267da-107">Бизнес-логика может представлять собой простую схему проверки совместимости типа поля с типом столбца таблицы.</span><span class="sxs-lookup"><span data-stu-id="267da-107">The business logic can be as simple as a schema validation to make sure that the type of the field is compatible with the type of the table column.</span></span> <span data-ttu-id="267da-108">Она также может состоять из набора объектов, взаимодействующих произвольным и довольно сложным образом.</span><span class="sxs-lookup"><span data-stu-id="267da-108">Or it can consist of a set of objects that interact in arbitrarily complex ways.</span></span> <span data-ttu-id="267da-109">Правила могут реализовываться в виде хранимых процедур для базы данных или в качестве объектов, содержащихся в памяти.</span><span class="sxs-lookup"><span data-stu-id="267da-109">The rules may be implemented as stored procedures on the database or as in-memory objects.</span></span> <span data-ttu-id="267da-110">Тем не менее бизнес-логика реализуется, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] позволяет использовать разделяемые классы и методы для отделения бизнес-логики от кода доступа к данным.</span><span class="sxs-lookup"><span data-stu-id="267da-110">However the business logic is implemented, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] enables you use partial classes and partial methods to separate the business logic from the data access code.</span></span>  
  
## <a name="how-linq-to-sql-invokes-your-business-logic"></a><span data-ttu-id="267da-111">Способы вызова бизнес-логики технологией LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="267da-111">How LINQ to SQL Invokes Your Business Logic</span></span>  
 <span data-ttu-id="267da-112">Если во время разработки либо вручную, либо с помощью конструктора [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] или программы SQLMetal создается класс сущностей, он определяется как разделяемый класс.</span><span class="sxs-lookup"><span data-stu-id="267da-112">When you generate an entity class at design time, either manually or by using the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] or SQLMetal, it is defined as a partial class.</span></span> <span data-ttu-id="267da-113">Это означает, что в отдельном файле с исходным кодом можно определить другую часть этого класса сущностей, содержащего пользовательскую бизнес-логику.</span><span class="sxs-lookup"><span data-stu-id="267da-113">This means that, in a separate code file, you can define another part of the entity class that contains your custom business logic.</span></span> <span data-ttu-id="267da-114">Во время компиляции обе части объединяются в один класс.</span><span class="sxs-lookup"><span data-stu-id="267da-114">At compile time, the two parts are merged into a single class.</span></span> <span data-ttu-id="267da-115">Однако, если требуется повторное создание класса сущностей с помощью конструктора [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] или программы SQLMetal, это можно сделать без изменения той части, которая содержит бизнес-логику.</span><span class="sxs-lookup"><span data-stu-id="267da-115">But if you have to regenerate your entity classes by using the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] or SQLMetal, you can do so and your part of the class will not be modified.</span></span>  
  
 <span data-ttu-id="267da-116">Разделяемые классы, которые определяют сущности, и класс <xref:System.Data.Linq.DataContext> содержат разделяемые методы.</span><span class="sxs-lookup"><span data-stu-id="267da-116">The partial classes that define entities and the <xref:System.Data.Linq.DataContext> contain partial methods.</span></span> <span data-ttu-id="267da-117">Эти методы являются точками расширения, которые можно использовать для применения бизнес-логики перед обновлением, вставкой или удалением сущности или свойства сущности, а также после выполнения этих операций.</span><span class="sxs-lookup"><span data-stu-id="267da-117">These are the extensibility points that you can use to apply your business logic before and after any update, insert, or delete for an entity or entity property.</span></span> <span data-ttu-id="267da-118">Разделяемые методы можно рассматривать как события времени компиляции.</span><span class="sxs-lookup"><span data-stu-id="267da-118">Partial methods can be thought of as compile-time events.</span></span> <span data-ttu-id="267da-119">Генератор кода определяет сигнатуру метода и вызывает эти методы в методах доступа к свойствам "get" и "set", конструкторе `DataContext` и в некоторых случаях неявным образом при вызове метода <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.</span><span class="sxs-lookup"><span data-stu-id="267da-119">The code-generator defines a method signature and calls the methods in the get and set property accessors, the `DataContext` constructor, and in some cases behind the scenes when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="267da-120">Однако, если не реализовать определенный разделяемый метод, все ссылки на него и определение удаляются во время компиляции.</span><span class="sxs-lookup"><span data-stu-id="267da-120">However, if you do not implement a particular partial method, then all the references to it and the definition are removed at compile time.</span></span>  
  
 <span data-ttu-id="267da-121">В определении реализации, созданном в отдельном файле с исходным кодом, можно выполнить любую требуемую пользовательскую логику.</span><span class="sxs-lookup"><span data-stu-id="267da-121">In the implementing definition that you write in your separate code file, you can perform whatever custom logic is required.</span></span> <span data-ttu-id="267da-122">Можно использовать разделяемый класс в качестве уровня домена или вызывать его из определения реализации разделяемого метода в отдельном объекте или объектах.</span><span class="sxs-lookup"><span data-stu-id="267da-122">You can use your partial class itself as your domain layer, or you can call from your implementing definition of the partial method into a separate object or objects.</span></span> <span data-ttu-id="267da-123">В любом случае бизнес-логика полностью отделена как от кода уровня доступа к данным, так и от кода уровня представления данных.</span><span class="sxs-lookup"><span data-stu-id="267da-123">Either way, your business logic is cleanly separated from both your data access code and your presentation layer code.</span></span>  
  
## <a name="a-closer-look-at-the-extensibility-points"></a><span data-ttu-id="267da-124">Более подробное рассмотрение точек расширения</span><span class="sxs-lookup"><span data-stu-id="267da-124">A Closer Look at the Extensibility Points</span></span>  
 <span data-ttu-id="267da-125">В следующем примере показано часть кода, созданного [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] для `DataContext` класс, который содержит две таблицы: `Customers` и `Orders`.</span><span class="sxs-lookup"><span data-stu-id="267da-125">The following example shows part of the code generated by the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] for the `DataContext` class that has two tables: `Customers` and `Orders`.</span></span> <span data-ttu-id="267da-126">Обратите внимание, что методы "Insert", "Update" и "Delete" определены для каждой таблицы в классе.</span><span class="sxs-lookup"><span data-stu-id="267da-126">Note that Insert, Update, and Delete methods are defined for each table in the class.</span></span>  
  
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
  
 <span data-ttu-id="267da-127">Если реализовать методы "Insert", "Update" и "Delete" в разделяемом классе, то при вызове метода [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] среда выполнения <xref:System.Data.Linq.DataContext.SubmitChanges%2A> вызовет их вместо собственных методов, используемых по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="267da-127">If you implement the Insert, Update and Delete methods in your partial class, the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime will call them instead of its own default methods when <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called.</span></span> <span data-ttu-id="267da-128">Это позволяет переопределить поведение, реализуемое по умолчанию для операций создания, чтения, обновления и удаления.</span><span class="sxs-lookup"><span data-stu-id="267da-128">This enables you to override the default behavior for create / read / update / delete operations.</span></span> <span data-ttu-id="267da-129">Дополнительные сведения см. в разделе [Пошаговое руководство: Настройка вставки, обновления и удаления в классах сущностей](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes).</span><span class="sxs-lookup"><span data-stu-id="267da-129">For more information, see [Walkthrough: Customizing the insert, update, and delete behavior of entity classes](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes).</span></span>  
  
 <span data-ttu-id="267da-130">Метод `OnCreated` вызывается в классе конструктора.</span><span class="sxs-lookup"><span data-stu-id="267da-130">The `OnCreated` method is called in the class constructor.</span></span>  
  
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
  
 <span data-ttu-id="267da-131">Классы сущностей имеют три метода, вызываемые средой выполнения [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] при создании, загрузке и проверки сущности (при вызове метода `SubmitChanges`).</span><span class="sxs-lookup"><span data-stu-id="267da-131">The entity classes have three methods that are called by the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] runtime when the entity is created, loaded, and validated (when `SubmitChanges` is called).</span></span> <span data-ttu-id="267da-132">Классы сущностей также имеют два разделяемых метода для каждого свойства. Один метод вызывается перед заданием свойства, а другой — после.</span><span class="sxs-lookup"><span data-stu-id="267da-132">The entity classes also have two partial methods for each property, one that is called before the property is set, and one that is called after.</span></span> <span data-ttu-id="267da-133">В следующем примере кода демонстрируются некоторые методы, созданные для класса `Customer`.</span><span class="sxs-lookup"><span data-stu-id="267da-133">The following code example shows some of the methods generated for the `Customer` class:</span></span>  
  
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
  
 <span data-ttu-id="267da-134">Эти методы вызывается в методе доступа "set" для свойства, как показано в следующем примере для свойства `CustomerID`:</span><span class="sxs-lookup"><span data-stu-id="267da-134">The methods are called in the property set accessor as shown in the following example for the `CustomerID` property:</span></span>  
  
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
  
 <span data-ttu-id="267da-135">В пользовательской части класса создается определение реализации метода.</span><span class="sxs-lookup"><span data-stu-id="267da-135">In your part of the class, you write an implementing definition of the method.</span></span> <span data-ttu-id="267da-136">В Visual Studio, после ввода `partial` технология IntelliSense отобразит определения метода в другой части класса.</span><span class="sxs-lookup"><span data-stu-id="267da-136">In Visual Studio, after you type `partial` you will see IntelliSense for the method definitions in the other part of the class.</span></span>  
  
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
  
 <span data-ttu-id="267da-137">Дополнительные сведения о добавлении бизнес-логики в приложение с помощью разделяемых методов см. в следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="267da-137">For more information about how to add business logic to your application by using partial methods, see the following topics:</span></span>  
  
 [<span data-ttu-id="267da-138">Практическое руководство. Добавление проверки в классы сущностей</span><span class="sxs-lookup"><span data-stu-id="267da-138">How to: Add validation to entity classes</span></span>](/visualstudio/data-tools/how-to-add-validation-to-entity-classes)  
  
 [<span data-ttu-id="267da-139">Пошаговое руководство: Настройка операций вставки, обновления и удаления в классах сущностей</span><span class="sxs-lookup"><span data-stu-id="267da-139">Walkthrough: Customizing the insert, update, and delete behavior of entity classes</span></span>](/visualstudio/data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes)  
  
 [<span data-ttu-id="267da-140">Пошаговое руководство: Добавление проверки в классы сущностей</span><span class="sxs-lookup"><span data-stu-id="267da-140">Walkthrough: Adding Validation to Entity Classes</span></span>](https://msdn.microsoft.com/library/85b06a02-b2e3-4534-95b8-d077c8d4c1d7)  
  
## <a name="see-also"></a><span data-ttu-id="267da-141">См. также</span><span class="sxs-lookup"><span data-stu-id="267da-141">See also</span></span>
- [<span data-ttu-id="267da-142">Разделяемые классы и методы</span><span class="sxs-lookup"><span data-stu-id="267da-142">Partial Classes and Methods</span></span>](~/docs/csharp/programming-guide/classes-and-structs/partial-classes-and-methods.md)
- [<span data-ttu-id="267da-143">Разделяемые методы</span><span class="sxs-lookup"><span data-stu-id="267da-143">Partial Methods</span></span>](~/docs/visual-basic/programming-guide/language-features/procedures/partial-methods.md)
- [<span data-ttu-id="267da-144">Средства LINQ to SQL в Visual Studio</span><span class="sxs-lookup"><span data-stu-id="267da-144">LINQ to SQL Tools in Visual Studio</span></span>](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [<span data-ttu-id="267da-145">SqlMetal.exe (средство создания кода)</span><span class="sxs-lookup"><span data-stu-id="267da-145">SqlMetal.exe (Code Generation Tool)</span></span>](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
