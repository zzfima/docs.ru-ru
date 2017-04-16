---
title: "Добавление заметок к типизированным объектам DataSet | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Добавление заметок к типизированным объектам DataSet
Заметки дают возможность изменять имена элементов в типизированных <xref:System.Data.DataSet> без изменения базовой схемы.  Если изменить имена элементов в базовой схеме, типизированные объекты **DataSet** будут ссылаться на объекты, не существующие в источнике данных, а также потеряют ссылки на объекты, которые имеются в источнике данных.  
  
 Используя заметки, можно изменить имена объектов в типизированных объектах **DataSet** на более понятные. Это упрощает чтение кода и облегчает клиентам использование типизированного объекта **DataSet**. При этом не затрагивается базовая схема.  Например, наличие следующего элемента схемы для таблицы **Customers** базы данных **Northwind** может привести к появлению имени **DataRow** объекта **CustomersRow** и <xref:System.Data.DataRowCollection> с именем **Customers**.  
  
```  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Для **DataRowCollection** имя **Заказчики** имеет значение в клиентском коде, но имя **DataRow** для **CustomersRow** может сбить с толку, т.к. это один объект.  Кроме того, в обычных сценариях ссылка на объект производится без идентификатора **Row**, и он просто указывается как объект **Customer**.  В качестве решения можно добавить заметки к схеме и определить новые имена для объектов **DataRow** и **DataRowCollection**.  Далее приводится версия предыдущей схемы с добавленными заметками.  
  
```  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Задание значения **typedName** для **Customer** приведет к появлению имени объекта **DataRow** для **Customer**.  Заданием **typedPlural** для **Customers** сохраняется имя **DataRowCollection** для **Customers**.  
  
 В следующей таблице показаны доступные для использования заметки.  
  
|Комментарий|Описание|  
|-----------------|--------------|  
|**typedName**|Имя объекта.|  
|**typedPlural**|Имя коллекции объектов.|  
|**typedParent**|Имя объекта при ссылке на родительскую связь.|  
|**typedChildren**|Имя метода, возвращающего объекты по дочерней связи.|  
|**nullValue**|Значение для того случая, если базовым значением является **DBNull**.  См. следующую таблицу для заметок **nullValue**.  По умолчанию используется **\_throw**.|  
  
 В следующей таблице представлены значения, которые могут быть заданы для заметки **nullValue**.  
  
|Значение nullValue|Описание|  
|------------------------|--------------|  
|*Заменяющее значение*|Задает возвращаемое значение.  Возвращаемое значение должно соответствовать типу элемента.  Например, чтобы для целочисленных полей вместо null возвращался 0, используйте `nullValue="0"`.|  
|**\_throw**|Создание исключения.  Это значение по умолчанию.|  
|**\_null**|Возвращает ссылку null или создает исключение, если встречается примитивный тип.|  
|**\_empty**|Для строк возвращает **String.Empty**, в противном случае возвращает объект, созданный из пустого конструктора.  Если встречается примитивный тип, вызывает исключение.|  
  
 В следующей таблице показаны значения по умолчанию для объектов в типизированном **DataSet** и доступные заметки.  
  
|Объект\/Метод\/Событие|По умолчанию|Комментарий|  
|----------------------------|------------------|-----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|Методы **DataTable**|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**DataRow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Свойство**|PropertyName|typedName|  
|Метод доступа **Child**|GetChildTableNameRows|typedChildren|  
|Метод доступа **Parent**|TableNameRow|typedParent|  
|События **DataSet**|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Чтобы использовать типизированные заметки **DataSet**, необходимо включить следующую ссылку **xmlns** в схему XSD.  \(Сведения о создании xsd из таблиц базы данных см. в разделе <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Работа с наборами данных в Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)\).  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Далее приводится образец схемы с добавленными заметками, которая предоставляет таблицу **Customers** базы данных **Northwind** с включенной ссылкой на таблицу **Orders**.  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet"   
      xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
      xmlns=""   
      xmlns:xs="http://www.w3.org/2001/XMLSchema"   
      xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers" codegen:typedName="Customer"  
codegen:typedPlural="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID" type="xs:string" minOccurs="0" />  
              <xs:element name="CompanyName"  
codegen:typedName="CompanyName" type="xs:string" minOccurs="0" />  
              <xs:element name="Phone" codegen:typedName="Phone"  
codegen:nullValue="" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
        <xs:element name="Orders" codegen:typedName="Order"  
codegen:typedPlural="Orders">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="OrderID" codegen:typedName="OrderID"  
type="xs:int" minOccurs="0" />  
              <xs:element name="CustomerID"  
codegen:typedName="CustomerID"  
                 codegen:nullValue="" type="xs:string" minOccurs="0" />  
              <xs:element name="EmployeeID"  
codegen:typedName="EmployeeID" codegen:nullValue="0"   
type="xs:int" minOccurs="0" />  
              <xs:element name="OrderAdapter"  
codegen:typedName="OrderAdapter"  
codegen:nullValue="1980-01-01T00:00:00"   
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
  
 В следующем примере кода используется **DataSet** со строгой типизацией, созданный из образца схемы.  Он использует один <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения таблицы **Customers** и другой <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения таблицы **Orders**.  Набор данных **DataSet** со строгой типизацией определяет **DataRelations**.  
  
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
    customers.Customers.NewCustomeromer()  
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
    customers.Customers.NewCustomeromer();  
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
  
## См. также  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataSet>   
 [Типизированные объекты DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)