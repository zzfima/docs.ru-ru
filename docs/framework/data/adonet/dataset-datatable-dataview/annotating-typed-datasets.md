---
title: Создание примечаний к типизированным наборам данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f82aaa62-321e-4c8a-b51b-9d1114700170
ms.openlocfilehash: df6da84dfc120e3f6c3cb0e46729ca2cecc9fe3a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040397"
---
# <a name="annotating-typed-datasets"></a>Создание примечаний к типизированным наборам данных
Заметки дают возможность изменять имена элементов в типизированных <xref:System.Data.DataSet> без изменения базовой схемы. Изменение имен элементов в базовой схеме приведет к тому, что типизированный **набор данных** будет ссылаться на объекты, не существующие в источнике данных, а также будет потеряна ссылка на объекты, существующие в источнике данных.  
  
 С помощью заметок можно настроить имена объектов в типизированном **наборе данных** с более информативными именами, сделать код более удобочитаемым, а типизированный **набор данных** проще использовать для использования клиентами, при этом не изменяя базовую схему. Например, следующий элемент схемы для таблицы **Customers** базы данных **Northwind** приведет к появлению имени объекта **DataRow** **кустомерсров** и <xref:System.Data.DataRowCollection> с именем **Customers**.  
  
```xml  
<xs:element name="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 **Датаровколлектион** имя **клиентов** имеет смысл в клиентском коде, но имя **DataRow** **кустомерсров** является ошибочным, поскольку является одним объектом. Кроме того, в обычных сценариях объект будет называться без идентификатора **строки** , а вместо этого будет просто называться объектом **Customer** . Решение заключается в создании заметка схемы и определении новых имен для объектов **DataRow** и **датаровколлектион** . Далее приводится версия предыдущей схемы с добавленными заметками.  
  
```xml  
<xs:element name="Customers" codegen:typedName="Customer" codegen:typedPlural="Customers">  
  <xs:complexType>  
    <xs:sequence>  
      <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
    </xs:sequence>  
  </xs:complexType>  
</xs:element>  
```  
  
 При указании значения **типеднаме** для **Customer** будет выдаваться имя объекта **DataRow** **Customer**. Указание значения **типедплурал** для **клиентов** сохраняет имя **датаровколлектион** **клиентов**.  
  
 В следующей таблице показаны доступные для использования заметки.  
  
|Комментарий|Описание|  
|----------------|-----------------|  
|**типеднаме**|Имя объекта.|  
|**типедплурал**|Имя коллекции объектов.|  
|**типедпарент**|Имя объекта при ссылке на родительскую связь.|  
|**типедчилдрен**|Имя метода, возвращающего объекты по дочерней связи.|  
|**nullValue**|Значение, если базовое значение равно **DBNull**. См. следующую таблицу для **NullValue** Annotations. Значение по умолчанию — **_throw**.|  
  
 В следующей таблице приведены значения, которые можно указать для аннотации **NullValue** .  
  
|Значение nullValue|Описание|  
|---------------------|-----------------|  
|*Заменяющее значение*|Задает возвращаемое значение. Возвращаемое значение должно соответствовать типу элемента. Например, чтобы для целочисленных полей вместо null возвращался 0, используйте `nullValue="0"`.|  
|**_throw**|Создание исключения. Это значение по умолчанию.|  
|**_null**|Возвращает ссылку null или создает исключение, если встречается примитивный тип.|  
|**_empty**|Для строк возвращает **String. Empty**, в противном случае возвращает объект, созданный из пустого конструктора. Если встречается примитивный тип, вызывает исключение.|  
  
 В следующей таблице показаны значения по умолчанию для объектов в типизированном **наборе данных** и доступных аннотациях.  
  
|Объект/Метод/Событие|Значение по умолчанию|Комментарий|  
|---------------------------|-------------|----------------|  
|**DataTable**|TableNameDataTable|typedPlural|  
|**DataTable** Метод|NewTableNameRow<br /><br /> AddTableNameRow<br /><br /> DeleteTableNameRow|typedName|  
|**датаровколлектион**|TableName|typedPlural|  
|**Строку**|TableNameRow|typedName|  
|**DataColumn**|DataTable.ColumnNameColumn<br /><br /> DataRow.ColumnName|typedName|  
|**Property**|PropertyName|typedName|  
|**Дочерний элемент** Возмож|GetChildTableNameRows|typedChildren|  
|**Родительский элемент** Возмож|TableNameRow|typedParent|  
|**Набор данных** Событиях|TableNameRowChangeEvent<br /><br /> TableNameRowChangeEventHandler|typedName|  
  
 Чтобы использовать зааннотации типизированного **набора данных** , необходимо включить следующую ссылку **xmlns** в схему языка определения схемы XML (XSD). Сведения о создании XSD из таблиц базы данных см. в разделе <xref:System.Data.DataSet.WriteXmlSchema%2A> или [Работа с наборами DataSet в Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio).  
  
```xml  
xmlns:codegen="urn:schemas-microsoft-com:xml-msprop"  
```  
  
 Ниже приведен пример схемы с заметками, которая предоставляет таблицу **Customers** базы данных **Northwind** с отношением к включенной таблице **Orders** .  
  
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
  
 В следующем примере кода используется строго типизированный **набор данных** , созданный из образца схемы. Он использует один <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения таблицы **Customers** и другой <xref:System.Data.SqlClient.SqlDataAdapter> для заполнения таблицы **Orders** . Строго типизированный **набор данных** определяет **DataRelation**.  
  
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
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Типизированные наборы данных](typed-datasets.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
