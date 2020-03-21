---
title: Создание примечаний к типизированным наборам данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 757a87f92d8dc6049de1844fed892d95dc57c990
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151524"
---
# <a name="annotating-typed-datasets"></a><span data-ttu-id="e53e3-102">Создание примечаний к типизированным наборам данных</span><span class="sxs-lookup"><span data-stu-id="e53e3-102">Annotating Typed DataSets</span></span>
<span data-ttu-id="e53e3-103">Заметки дают возможность изменять имена элементов в типизированных <xref:System.Data.DataSet> без изменения базовой схемы.</span><span class="sxs-lookup"><span data-stu-id="e53e3-103">Annotations enable you to modify the names of the elements in your typed <xref:System.Data.DataSet> without modifying the underlying schema.</span></span> <span data-ttu-id="e53e3-104">Изменение имен элементов в базовой схеме приведет к тому, что набранный **DataSet** отсылает к объектам, не существующих в источнике данных, а также потеряет ссылку на объекты, которые существуют в источнике данных.</span><span class="sxs-lookup"><span data-stu-id="e53e3-104">Modifying the names of the elements in your underlying schema would cause the typed **DataSet** to refer to objects that do not exist in the data source, as well as lose a reference to the objects that do exist in the data source.</span></span>  
  
 <span data-ttu-id="e53e3-105">Используя аннотации, можно настроить имена объектов в набранном **DataSet** с более значимыми именами, что упрощает использование кода DataSet и упрощает использование **DataSet,** оставляя базовую схему нетронутой.</span><span class="sxs-lookup"><span data-stu-id="e53e3-105">Using annotations, you can customize the names of objects in your typed **DataSet** with more meaningful names, making code more readable and your typed **DataSet** easier for clients to use, while leaving underlying schema intact.</span></span> <span data-ttu-id="e53e3-106">Например, следующий элемент схемы для таблицы **клиентов** базы данных **Northwind** приведет к <xref:System.Data.DataRowCollection> названию объекта **DataRow** **CustomersRow** и названному **Заказчику.**</span><span class="sxs-lookup"><span data-stu-id="e53e3-106">For example, the following schema element for the **Customers** table of the **Northwind** database would result in a **DataRow** object name of **CustomersRow** and a <xref:System.Data.DataRowCollection> named **Customers**.</span></span>  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="e53e3-107">Имя **клиентов** **DataRowCollection** имеет значение в клиентском коде, но имя **DataRow** **CustomersRow** вводит в заблуждение, потому что это один объект.</span><span class="sxs-lookup"><span data-stu-id="e53e3-107">A **DataRowCollection** name of **Customers** is meaningful in client code, but a **DataRow** name of **CustomersRow** is misleading because it is a single object.</span></span> <span data-ttu-id="e53e3-108">Кроме того, в обычных сценариях объект будет называться без идентификатора **строки** и вместо этого будет просто называться объектом **клиента.**</span><span class="sxs-lookup"><span data-stu-id="e53e3-108">Also, in common scenarios, the object would be referred to without the **Row** identifier and instead would be simply referred to as a **Customer** object.</span></span> <span data-ttu-id="e53e3-109">Решение состоит в том, чтобы аннотировать схему и определить новые имена для объектов **DataRow** и **DataRowCollection.**</span><span class="sxs-lookup"><span data-stu-id="e53e3-109">The solution is to annotate the schema and identify new names for the **DataRow** and **DataRowCollection** objects.</span></span> <span data-ttu-id="e53e3-110">Далее приводится версия предыдущей схемы с добавленными заметками.</span><span class="sxs-lookup"><span data-stu-id="e53e3-110">Following is the annotated version of the previous schema.</span></span>  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 <span data-ttu-id="e53e3-111">Указать **значение typedName** **клиента** приведет к названию объекта **DataRow** **Клиента.**</span><span class="sxs-lookup"><span data-stu-id="e53e3-111">Specifying a **typedName** value of **Customer** will result in a **DataRow** object name of **Customer**.</span></span> <span data-ttu-id="e53e3-112">Указание **набраннойВоялезначение** **клиентов** сохраняет имя **Клиентов** **DataRowCollection.**</span><span class="sxs-lookup"><span data-stu-id="e53e3-112">Specifying a **typedPlural** value of **Customers** preserves the **DataRowCollection** name of **Customers**.</span></span>  
  
 <span data-ttu-id="e53e3-113">В следующей таблице показаны доступные для использования заметки.</span><span class="sxs-lookup"><span data-stu-id="e53e3-113">The following table shows the annotations available for use.</span></span>  
  
|<span data-ttu-id="e53e3-114">Заметка</span><span class="sxs-lookup"><span data-stu-id="e53e3-114">Annotation</span></span>|<span data-ttu-id="e53e3-115">Описание</span><span class="sxs-lookup"><span data-stu-id="e53e3-115">Description</span></span>|  
|----------------|-----------------|  
|<span data-ttu-id="e53e3-116">**typedName**</span><span class="sxs-lookup"><span data-stu-id="e53e3-116">**typedName**</span></span>|<span data-ttu-id="e53e3-117">Имя объекта.</span><span class="sxs-lookup"><span data-stu-id="e53e3-117">Name of the object.</span></span>|  
|<span data-ttu-id="e53e3-118">**typedPlural**</span><span class="sxs-lookup"><span data-stu-id="e53e3-118">**typedPlural**</span></span>|<span data-ttu-id="e53e3-119">Имя коллекции объектов.</span><span class="sxs-lookup"><span data-stu-id="e53e3-119">Name of a collection of objects.</span></span>|  
|<span data-ttu-id="e53e3-120">**typedParent**</span><span class="sxs-lookup"><span data-stu-id="e53e3-120">**typedParent**</span></span>|<span data-ttu-id="e53e3-121">Имя объекта при ссылке на родительскую связь.</span><span class="sxs-lookup"><span data-stu-id="e53e3-121">Name of the object when referred to in a parent relationship.</span></span>|  
|<span data-ttu-id="e53e3-122">**typedChildren**</span><span class="sxs-lookup"><span data-stu-id="e53e3-122">**typedChildren**</span></span>|<span data-ttu-id="e53e3-123">Имя метода, возвращающего объекты по дочерней связи.</span><span class="sxs-lookup"><span data-stu-id="e53e3-123">Name of the method to return objects from a child relationship.</span></span>|  
|<span data-ttu-id="e53e3-124">**Nullvalue**</span><span class="sxs-lookup"><span data-stu-id="e53e3-124">**nullValue**</span></span>|<span data-ttu-id="e53e3-125">Значение, если базовое значение **DBNull**.</span><span class="sxs-lookup"><span data-stu-id="e53e3-125">Value if the underlying value is **DBNull**.</span></span> <span data-ttu-id="e53e3-126">Смотрите следующую таблицу для аннотаций **nullValue.**</span><span class="sxs-lookup"><span data-stu-id="e53e3-126">See the following table for **nullValue** annotations.</span></span> <span data-ttu-id="e53e3-127">По умолчанию **_throw**.</span><span class="sxs-lookup"><span data-stu-id="e53e3-127">The default is **_throw**.</span></span>|  
  
 <span data-ttu-id="e53e3-128">В следующей таблице показаны значения, которые могут быть указаны для аннотации **nullValue.**</span><span class="sxs-lookup"><span data-stu-id="e53e3-128">The following table shows the values that can be specified for the **nullValue** annotation.</span></span>  
  
|<span data-ttu-id="e53e3-129">Значение nullValue</span><span class="sxs-lookup"><span data-stu-id="e53e3-129">nullValue Value</span></span>|<span data-ttu-id="e53e3-130">Описание</span><span class="sxs-lookup"><span data-stu-id="e53e3-130">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="e53e3-131">*Значение замены*</span><span class="sxs-lookup"><span data-stu-id="e53e3-131">*Replacement Value*</span></span>|<span data-ttu-id="e53e3-132">Задает возвращаемое значение.</span><span class="sxs-lookup"><span data-stu-id="e53e3-132">Specify a value to be returned.</span></span> <span data-ttu-id="e53e3-133">Возвращаемое значение должно соответствовать типу элемента.</span><span class="sxs-lookup"><span data-stu-id="e53e3-133">The returned value must match the type of the element.</span></span> <span data-ttu-id="e53e3-134">Например, чтобы для целочисленных полей вместо null возвращался 0, используйте `nullValue="0"`.</span><span class="sxs-lookup"><span data-stu-id="e53e3-134">For example, use `nullValue="0"` to return 0 for null integer fields.</span></span>|  
|<span data-ttu-id="e53e3-135">**_throw**</span><span class="sxs-lookup"><span data-stu-id="e53e3-135">**_throw**</span></span>|<span data-ttu-id="e53e3-136">Создание исключения.</span><span class="sxs-lookup"><span data-stu-id="e53e3-136">Throw an exception.</span></span> <span data-ttu-id="e53e3-137">Это значение по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e53e3-137">This is the default.</span></span>|  
|<span data-ttu-id="e53e3-138">**_null**</span><span class="sxs-lookup"><span data-stu-id="e53e3-138">**_null**</span></span>|<span data-ttu-id="e53e3-139">Возвращает ссылку null или создает исключение, если встречается примитивный тип.</span><span class="sxs-lookup"><span data-stu-id="e53e3-139">Return a null reference or throw an exception if a primitive type is encountered.</span></span>|  
|<span data-ttu-id="e53e3-140">**_empty**</span><span class="sxs-lookup"><span data-stu-id="e53e3-140">**_empty**</span></span>|<span data-ttu-id="e53e3-141">Для строк верните **String.Empty,** в противном случае верните объект, созданный из пустого конструктора.</span><span class="sxs-lookup"><span data-stu-id="e53e3-141">For strings, return **String.Empty**, otherwise return an object created from an empty constructor.</span></span> <span data-ttu-id="e53e3-142">Если встречается примитивный тип, вызывает исключение.</span><span class="sxs-lookup"><span data-stu-id="e53e3-142">If a primitive type is encountered, throw an exception.</span></span>|  
  
 <span data-ttu-id="e53e3-143">В следующей таблице отображались значения по умолчанию для объектов в набранном **DataSet** и доступные аннотации.</span><span class="sxs-lookup"><span data-stu-id="e53e3-143">The following table shows default values for objects in a typed **DataSet** and the available annotations.</span></span>  
  
|<span data-ttu-id="e53e3-144">Объект/Метод/Событие</span><span class="sxs-lookup"><span data-stu-id="e53e3-144">Object/Method/Event</span></span>|<span data-ttu-id="e53e3-145">По умолчанию</span><span class="sxs-lookup"><span data-stu-id="e53e3-145">Default</span></span>|<span data-ttu-id="e53e3-146">Заметка</span><span class="sxs-lookup"><span data-stu-id="e53e3-146">Annotation</span></span>|  
|---------------------------|-------------|----------------|  
|<span data-ttu-id="e53e3-147">**Datatable**</span><span class="sxs-lookup"><span data-stu-id="e53e3-147">**DataTable**</span></span>|<span data-ttu-id="e53e3-148">TableNameDataTable</span><span class="sxs-lookup"><span data-stu-id="e53e3-148">TableNameDataTable</span></span>|<span data-ttu-id="e53e3-149">typedPlural</span><span class="sxs-lookup"><span data-stu-id="e53e3-149">typedPlural</span></span>|  
|<span data-ttu-id="e53e3-150">**DataTable** Методы</span><span class="sxs-lookup"><span data-stu-id="e53e3-150">**DataTable** Methods</span></span>|<span data-ttu-id="e53e3-151">NewTableNameRow</span><span class="sxs-lookup"><span data-stu-id="e53e3-151">NewTableNameRow</span></span><br /><br /> <span data-ttu-id="e53e3-152">AddTableNameRow</span><span class="sxs-lookup"><span data-stu-id="e53e3-152">AddTableNameRow</span></span><br /><br /> <span data-ttu-id="e53e3-153">DeleteTableNameRow</span><span class="sxs-lookup"><span data-stu-id="e53e3-153">DeleteTableNameRow</span></span>|<span data-ttu-id="e53e3-154">typedName</span><span class="sxs-lookup"><span data-stu-id="e53e3-154">typedName</span></span>|  
|<span data-ttu-id="e53e3-155">**DataRowCollection**</span><span class="sxs-lookup"><span data-stu-id="e53e3-155">**DataRowCollection**</span></span>|<span data-ttu-id="e53e3-156">TableName</span><span class="sxs-lookup"><span data-stu-id="e53e3-156">TableName</span></span>|<span data-ttu-id="e53e3-157">typedPlural</span><span class="sxs-lookup"><span data-stu-id="e53e3-157">typedPlural</span></span>|  
|<span data-ttu-id="e53e3-158">**Datarow**</span><span class="sxs-lookup"><span data-stu-id="e53e3-158">**DataRow**</span></span>|<span data-ttu-id="e53e3-159">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="e53e3-159">TableNameRow</span></span>|<span data-ttu-id="e53e3-160">typedName</span><span class="sxs-lookup"><span data-stu-id="e53e3-160">typedName</span></span>|  
|<span data-ttu-id="e53e3-161">**DataColumn**</span><span class="sxs-lookup"><span data-stu-id="e53e3-161">**DataColumn**</span></span>|<span data-ttu-id="e53e3-162">DataTable.ColumnNameColumn</span><span class="sxs-lookup"><span data-stu-id="e53e3-162">DataTable.ColumnNameColumn</span></span><br /><br /> <span data-ttu-id="e53e3-163">DataRow.ColumnName</span><span class="sxs-lookup"><span data-stu-id="e53e3-163">DataRow.ColumnName</span></span>|<span data-ttu-id="e53e3-164">typedName</span><span class="sxs-lookup"><span data-stu-id="e53e3-164">typedName</span></span>|  
|<span data-ttu-id="e53e3-165">**Свойство**</span><span class="sxs-lookup"><span data-stu-id="e53e3-165">**Property**</span></span>|<span data-ttu-id="e53e3-166">PropertyName</span><span class="sxs-lookup"><span data-stu-id="e53e3-166">PropertyName</span></span>|<span data-ttu-id="e53e3-167">typedName</span><span class="sxs-lookup"><span data-stu-id="e53e3-167">typedName</span></span>|  
|<span data-ttu-id="e53e3-168">**Детский дом** Доступа</span><span class="sxs-lookup"><span data-stu-id="e53e3-168">**Child** Accessor</span></span>|<span data-ttu-id="e53e3-169">GetChildTableNameRows</span><span class="sxs-lookup"><span data-stu-id="e53e3-169">GetChildTableNameRows</span></span>|<span data-ttu-id="e53e3-170">typedChildren</span><span class="sxs-lookup"><span data-stu-id="e53e3-170">typedChildren</span></span>|  
|<span data-ttu-id="e53e3-171">**Родительская** Доступа</span><span class="sxs-lookup"><span data-stu-id="e53e3-171">**Parent** Accessor</span></span>|<span data-ttu-id="e53e3-172">TableNameRow</span><span class="sxs-lookup"><span data-stu-id="e53e3-172">TableNameRow</span></span>|<span data-ttu-id="e53e3-173">typedParent</span><span class="sxs-lookup"><span data-stu-id="e53e3-173">typedParent</span></span>|  
|<span data-ttu-id="e53e3-174">**DataSet** События</span><span class="sxs-lookup"><span data-stu-id="e53e3-174">**DataSet** Events</span></span>|<span data-ttu-id="e53e3-175">TableNameRowChangeEvent</span><span class="sxs-lookup"><span data-stu-id="e53e3-175">TableNameRowChangeEvent</span></span><br /><br /> <span data-ttu-id="e53e3-176">TableNameRowChangeEventHandler</span><span class="sxs-lookup"><span data-stu-id="e53e3-176">TableNameRowChangeEventHandler</span></span>|<span data-ttu-id="e53e3-177">typedName</span><span class="sxs-lookup"><span data-stu-id="e53e3-177">typedName</span></span>|  
  
 <span data-ttu-id="e53e3-178">Для использования набранных аннотаций **DataSet** необходимо включить в схему определения XML Schema (XSD) следующую ссылку **xmlns.**</span><span class="sxs-lookup"><span data-stu-id="e53e3-178">To use typed **DataSet** annotations, you must include the following **xmlns** reference in your XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="e53e3-179">Чтобы создать xsd из таблиц <xref:System.Data.DataSet.WriteXmlSchema%2A> баз данных, смотрите или [работайте с наборами данных в Visual Studio.](/visualstudio/data-tools/dataset-tools-in-visual-studio)</span><span class="sxs-lookup"><span data-stu-id="e53e3-179">To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).</span></span>  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 <span data-ttu-id="e53e3-180">Ниже приводится пример аннотированной схемы, которая предоставляет таблицу **клиентов** базы данных **Northwind** со отсылкой к таблице **заказов** включены.</span><span class="sxs-lookup"><span data-stu-id="e53e3-180">The following is a sample annotated schema that exposes the **Customers** table of the **Northwind** database with a relation to the **Orders** table included.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""
      xmlns:xs="http://www.w3.org/2001/XMLSchema"
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone" codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order" codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"                  codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter" codegen:nullValue="1980-01-01T00:00:00"
type="xs:dateTime" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
    <xs:unique name="Constraint1">  
      <xs:selector xpath=".//Customers" />  
      <xs:field xpath="CustomerID" />  
    </xs:unique>  
    <xs:keyref name="CustOrders" refer="Constraint1"  
codegen:typedParent="Customer" codegen:typedChildren="GetOrders">  
      <xs:selector xpath=".//Orders" />  
      <xs:field xpath="CustomerID" />  
    </xs:keyref>  
  </xs:element>  
</xs:schema>  
```  
  
 <span data-ttu-id="e53e3-181">В следующем примере кода используется сильно набранный **DataSet,** созданный из схемы образца.</span><span class="sxs-lookup"><span data-stu-id="e53e3-181">The following code example uses a strongly typed **DataSet** created from the sample schema.</span></span> <span data-ttu-id="e53e3-182">Он использует <xref:System.Data.SqlClient.SqlDataAdapter> один для заполнения таблицы **Заказчиков,** а другой <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения таблицы **Заказов.**</span><span class="sxs-lookup"><span data-stu-id="e53e3-182">It uses one <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Customers** table and another <xref:System.Data.SqlClient.SqlDataAdapter> to populate the **Orders** table.</span></span> <span data-ttu-id="e53e3-183">Сильно набранный **DataSet** определяет **DataRelations.**</span><span class="sxs-lookup"><span data-stu-id="e53e3-183">The strongly typed **DataSet** defines the **DataRelations**.</span></span>  
  
```vb  
' Assumes a valid SqlConnection object named connection.  
Dim customerAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT CustomerID, CompanyName, Phone FROM Customers", &  
    connection)  
Dim orderAdapter As SqlDataAdapter = New SqlDataAdapter( _  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders", &  
    connection)  
  
' Populate a strongly typed DataSet.  
connection.Open()  
Dim customers As CustomerDataSet = New CustomerDataSet()  
customerAdapter.Fill(customers, "Customers")  
orderAdapter.Fill(customers, "Orders")  
connection.Close()  
  
' Add a strongly typed event.  
AddHandler customers.Customers.CustomerChanged, &  
    New CustomerDataSet.CustomerChangeEventHandler( _  
    AddressOf OnCustomerChanged)  
  
' Add a strongly typed DataRow.  
Dim newCustomer As CustomerDataSet.Customer = _  
    customers.Customers.NewCustomer()  
newCustomer.CustomerID = "NEW01"  
newCustomer.CompanyName = "My New Company"  
customers.Customers.AddCustomer(newCustomer)  
  
' Navigate the child relation.  
Dim customer As CustomerDataSet.Customer  
Dim order As CustomerDataSet.Order  
  
For Each customer In customers.Customers  
  Console.WriteLine(customer.CustomerID)  
  For Each order In customer.GetOrders()  
    Console.WriteLine(vbTab & order.OrderID)  
  Next  
Next  
  
Private Shared Sub OnCustomerChanged( _  
    sender As Object, e As CustomerDataSet.CustomerChangeEvent)  
  
End Sub  
```  
  
```csharp  
// Assumes a valid SqlConnection object named connection.  
SqlDataAdapter customerAdapter = new SqlDataAdapter(  
    "SELECT CustomerID, CompanyName, Phone FROM Customers",  
    connection);  
SqlDataAdapter orderAdapter = new SqlDataAdapter(  
    "SELECT OrderID, CustomerID, EmployeeID, OrderAdapter FROM Orders",
    connection);  
  
// Populate a strongly typed DataSet.  
connection.Open();  
CustomerDataSet customers = new CustomerDataSet();  
customerAdapter.Fill(customers, "Customers");  
orderAdapter.Fill(customers, "Orders");  
connection.Close();  
  
// Add a strongly typed event.  
customers.Customers.CustomerChanged += new
  CustomerDataSet.CustomerChangeEventHandler(OnCustomerChanged);  
  
// Add a strongly typed DataRow.  
CustomerDataSet.Customer newCustomer =
    customers.Customers.NewCustomer();  
newCustomer.CustomerID = "NEW01";  
newCustomer.CompanyName = "My New Company";  
customers.Customers.AddCustomer(newCustomer);  
  
// Navigate the child relation.  
foreach(CustomerDataSet.Customer customer in customers.Customers)  
{  
  Console.WriteLine(customer.CustomerID);  
  foreach(CustomerDataSet.Order order in customer.GetOrders())  
    Console.WriteLine("\t" + order.OrderID);  
}  
  
protected static void OnCustomerChanged(object sender, CustomerDataSet.CustomerChangeEvent e)  
    {  
  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="e53e3-184">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="e53e3-184">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="e53e3-185">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="e53e3-185">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="e53e3-186">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="e53e3-186">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="e53e3-187">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="e53e3-187">ADO.NET Overview</span></span>](../ado-net-overview.md)
