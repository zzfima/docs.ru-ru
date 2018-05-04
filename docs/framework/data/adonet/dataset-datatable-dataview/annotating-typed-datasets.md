---
title: Создание примечаний к типизированным наборам данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: 1974ac71e367203b8b94375e43d4fde13f2df51f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="annotating-typed-datasets"></a>Создание примечаний к типизированным наборам данных
Заметки дают возможность изменять имена элементов в типизированных <xref:System.Data.DataSet> без изменения базовой схемы. Изменить имена элементов в базовой схеме, типизированные **набора данных** для ссылки на объекты, которые не существуют в источнике данных, а также потеряют ссылки на объекты, которые существуют в источнике данных.  
  
 Используя заметки, можно изменить имена объектов в типизированных объектах **DataSet** с более понятные имена, что делает код более удобочитаемым и типизированного **DataSet** облегчает клиентам использовать, предоставляя Базовая схема без изменений. Например, следующий элемент схемы для **клиентов** таблицу **Northwind** базы данных приведет к появлению **DataRow** объект имени  **CustomersRow** и <xref:System.Data.DataRowCollection> с именем **клиентов**.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Объект **DataRowCollection** имя **клиентов** имеет смысл в клиентском коде, но **DataRow** имя **CustomersRow** может ввести в заблуждение так как один объект. Кроме того, общие сценарии, объект обычно указывается без **строки** идентификатор и вместо этого будет просто обращаться как к **клиента** объекта. Решение — добавить заметки к схеме и определить новые имена для **DataRow** и **DataRowCollection** объектов. Далее приводится версия предыдущей схемы с добавленными заметками.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 Указание **typedName** значение **клиента** приведет к **DataRow** объект имени **клиента**. Указание **typedPlural** значение **клиентов** сохраняет **DataRowCollection** имя **клиентов**.  
  
 В следующей таблице показаны доступные для использования заметки.  
  
|Комментарий|Описание|  
|----------------|-----------------|  
|**typedName**|Имя объекта.|  
|**typedPlural**|Имя коллекции объектов.|  
|**typedParent**|Имя объекта при ссылке на родительскую связь.|  
|**typedChildren**|Имя метода, возвращающего объекты по дочерней связи.|  
|**nullValue**|Значение, если базовое значение ― **DBNull**. См. следующую таблицу для **nullValue** заметок. Значение по умолчанию — **_throw**.|  
  
 В следующей таблице показаны значения, которые могут быть указаны для **nullValue** заметки.  
  
|Значение nullValue|Описание|  
|---------------------|-----------------|  
|*Заменяющее значение*|Задает возвращаемое значение. Возвращаемое значение должно соответствовать типу элемента. Например, чтобы для целочисленных полей вместо null возвращался 0, используйте `nullValue="0"`.|  
|**_throw**|Создание исключения. Это значение по умолчанию.|  
|**_null**|Возвращает ссылку null или создает исключение, если встречается примитивный тип.|  
|**_empty**|Для строк возвращает **String.Empty**, в противном случае возвращает объект, созданный из пустого конструктора. Если встречается примитивный тип, вызывает исключение.|  
  
 В следующей таблице показаны значения по умолчанию для объектов в типизированном **набора данных** и доступные заметки.  
  
|Объект/Метод/Событие|По умолчанию|Комментарий|  
|---------------------------|-------------|----------------|  
|**Таблицы данных**|TableNameDataTable|typedPlural|  
|**DataTable** методы|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**DataRowCollection**|TableName|typedPlural|  
|**dataRow**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Свойство**|PropertyName|typedName|  
|**Дочерние** метода доступа|GetChildTableNameRows|typedChildren|  
|**Родительский** метода доступа|TableNameRow|typedParent|  
|**Набор данных** события|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Чтобы использовать типизированные **DataSet** заметки, необходимо включить следующие **xmlns** ссылка в вашей языка определения схемы XML. (Чтобы сформировать xsd из таблиц базы данных, в разделе <xref:System.Data.DataSet.WriteXmlSchema%2A> или [работа с наборами данных в Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)).  
  
```  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Ниже приведен пример аннотированной схемы, которая предоставляет **клиентов** таблицу **Northwind** базы данных с отношением для **заказов** таблица, включенная.  
  
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
  
 В следующем примере кода используется строго типизированный **DataSet** созданный из образца схемы. Он использует один <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения **клиентов** таблицу, а другую <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения **заказов** таблицы. Строго типизированные **DataSet** определяет **отношений DataRelation**.  
  
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
  
## <a name="see-also"></a>См. также  
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [Типизированные наборы данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
