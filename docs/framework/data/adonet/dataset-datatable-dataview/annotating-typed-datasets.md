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
# <a name="annotating-typed-datasets"></a>Создание примечаний к типизированным наборам данных
Заметки дают возможность изменять имена элементов в типизированных <xref:System.Data.DataSet> без изменения базовой схемы. Изменение имен элементов в базовой схеме приведет к тому, что набранный **DataSet** отсылает к объектам, не существующих в источнике данных, а также потеряет ссылку на объекты, которые существуют в источнике данных.  
  
 Используя аннотации, можно настроить имена объектов в набранном **DataSet** с более значимыми именами, что упрощает использование кода DataSet и упрощает использование **DataSet,** оставляя базовую схему нетронутой. Например, следующий элемент схемы для таблицы **клиентов** базы данных **Northwind** приведет к <xref:System.Data.DataRowCollection> названию объекта **DataRow** **CustomersRow** и названному **Заказчику.**  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Имя **клиентов** **DataRowCollection** имеет значение в клиентском коде, но имя **DataRow** **CustomersRow** вводит в заблуждение, потому что это один объект. Кроме того, в обычных сценариях объект будет называться без идентификатора **строки** и вместо этого будет просто называться объектом **клиента.** Решение состоит в том, чтобы аннотировать схему и определить новые имена для объектов **DataRow** и **DataRowCollection.** Далее приводится версия предыдущей схемы с добавленными заметками.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Указать **значение typedName** **клиента** приведет к названию объекта **DataRow** **Клиента.** Указание **набраннойВоялезначение** **клиентов** сохраняет имя **Клиентов** **DataRowCollection.**  
  
 В следующей таблице показаны доступные для использования заметки.  
  
|Заметка|Описание|  
|----------------|-----------------|  
|**typedName**|Имя объекта.|  
|**typedPlural**|Имя коллекции объектов.|  
|**typedParent**|Имя объекта при ссылке на родительскую связь.|  
|**typedChildren**|Имя метода, возвращающего объекты по дочерней связи.|  
|**Nullvalue**|Значение, если базовое значение **DBNull**. Смотрите следующую таблицу для аннотаций **nullValue.** По умолчанию **_throw**.|  
  
 В следующей таблице показаны значения, которые могут быть указаны для аннотации **nullValue.**  
  
|Значение nullValue|Описание|  
|---------------------|-----------------|  
|*Значение замены*|Задает возвращаемое значение. Возвращаемое значение должно соответствовать типу элемента. Например, чтобы для целочисленных полей вместо null возвращался 0, используйте `nullValue="0"`.|  
|**_throw**|Создание исключения. Это значение по умолчанию.|  
|**_null**|Возвращает ссылку null или создает исключение, если встречается примитивный тип.|  
|**_empty**|Для строк верните **String.Empty,** в противном случае верните объект, созданный из пустого конструктора. Если встречается примитивный тип, вызывает исключение.|  
  
 В следующей таблице отображались значения по умолчанию для объектов в набранном **DataSet** и доступные аннотации.  
  
|Объект/Метод/Событие|По умолчанию|Заметка|  
|---------------------------|-------------|----------------|  
|**Datatable**|TableNameDataTable|typedPlural|  
|**DataTable** Методы|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**Datarow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Свойство**|PropertyName|typedName|  
|**Детский дом** Доступа|GetChildTableNameRows|typedChildren|  
|**Родительская** Доступа|TableNameRow|typedParent|  
|**DataSet** События|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Для использования набранных аннотаций **DataSet** необходимо включить в схему определения XML Schema (XSD) следующую ссылку **xmlns.** Чтобы создать xsd из таблиц <xref:System.Data.DataSet.WriteXmlSchema%2A> баз данных, смотрите или [работайте с наборами данных в Visual Studio.](/visualstudio/data-tools/dataset-tools-in-visual-studio)  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Ниже приводится пример аннотированной схемы, которая предоставляет таблицу **клиентов** базы данных **Northwind** со отсылкой к таблице **заказов** включены.  
  
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
  
 В следующем примере кода используется сильно набранный **DataSet,** созданный из схемы образца. Он использует <xref:System.Data.SqlClient.SqlDataAdapter> один для заполнения таблицы **Заказчиков,** а другой <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения таблицы **Заказов.** Сильно набранный **DataSet** определяет **DataRelations.**  
  
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
  
## <a name="see-also"></a>См. также раздел

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Типизированные наборы данных](typed-datasets.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
