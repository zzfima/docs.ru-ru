---
title: Создание строго типизированных наборов данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 25419f8a810b52103e6b862cfe2fe6ab5a1fd981
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040093"
---
# <a name="generating-strongly-typed-datasets"></a>Создание строго типизированных наборов данных
Учитывая схему XML, которая соответствует стандарту языка определения схемы XML (XSD), можно создать строго типизированную <xref:System.Data.DataSet> с помощью средства XSD. exe, поставляемого с пакетом средств разработки программного обеспечения (SDK) для Windows.  
  
 (Чтобы создать XSD из таблиц базы данных, см. статью <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with DataSets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).  
  
 В следующем коде показан синтаксис для создания **набора данных** с помощью этого средства.  
  
```console  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 В этом синтаксисе директива `/d` указывает средству создать **набор данных**, а `/l:` указывает инструменту, какой язык следует использовать (например, C# или Visual Basic .NET). Необязательная директива `/eld` указывает, что можно использовать LINQ to DataSet для запроса к созданному **набору данных.** Данный параметр используется при указании параметра `/d`. Дополнительные сведения см. в разделе [запросы к типизированным наборам данных](../querying-typed-datasets.md). Необязательная директива `/n:` указывает, что средство также создает пространство имен для **набора данных** с именем **кссдсчема. Namespace**. Выходом команды является файл XSDSchemaFileName.cs, который можно скомпилировать и использовать в приложении ADO.NET. Созданный код можно скомпилировать в виде библиотеки или модуля.  
  
 В следующем коде показан синтаксис для компиляции созданного кода в виде библиотеки с помощью компилятора C# (csc.exe).  
  
```console  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 Директива `/t:` служит для этого инструмента указанием по компиляции библиотеки, а директива `/r:` указывает зависимые библиотеки, которые необходимо скомпилировать. Выходом команды является файл XSDSchemaFileName.dll, который можно передать компилятору при компилировании приложения ADO.NET с помощью директивы `/r:`.  
  
 В следующем коде показан синтаксис обеспечения доступа к пространству имен, переданному инструменту XSD.exe в приложении ADO.NET.  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 В следующем примере кода используется типизированный **набор данных** с именем **кустомердатасет** для загрузки списка клиентов из базы данных **Northwind** . После загрузки данных с помощью метода **Fill** в примере выполняется циклический перебор каждого клиента в таблице **Customers** с помощью объекта типизированной **кустомерсров** (**DataRow**). Это обеспечивает прямой доступ к столбцу **CustomerID** , в отличие от **датаколумнколлектион**.  
  
```vb  
Dim customers As CustomerDataSet= New CustomerDataSet()  
Dim adapter As SqlDataAdapter New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers;", _  
  "Data Source=(local);Integrated " & _  
  "Security=SSPI;Initial Catalog=Northwind")  
  
adapter.Fill(customers, "Customers")  
  
Dim customerRow As CustomerDataSet.CustomersRow  
For Each customerRow In customers.Customers  
  Console.WriteLine(customerRow.CustomerID)  
Next  
```  
  
```csharp  
CustomerDataSet customers = new CustomerDataSet();  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers;",  
  "Data Source=(local);Integrated " +  
  "Security=SSPI;Initial Catalog=Northwind");  
  
adapter.Fill(customers, "Customers");  
  
foreach(CustomerDataSet.CustomersRow customerRow in customers.Customers)  
  Console.WriteLine(customerRow.CustomerID);  
```  
  
 Ниже приведена схема XML, используемая для примера.
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<xs:schema id="CustomerDataSet" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">  
  <xs:element name="CustomerDataSet" msdata:IsDataSet="true">  
    <xs:complexType>  
      <xs:choice maxOccurs="unbounded">  
        <xs:element name="Customers">  
          <xs:complexType>  
            <xs:sequence>  
              <xs:element name="CustomerID" type="xs:string" minOccurs="0" />  
            </xs:sequence>  
          </xs:complexType>  
        </xs:element>  
      </xs:choice>  
    </xs:complexType>  
  </xs:element>  
</xs:schema>  
```  
  
## <a name="see-also"></a>См. также

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [Типизированные наборы данных](typed-datasets.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [Общие сведения об ADO.NET](../ado-net-overview.md)
