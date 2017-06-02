---
title: "Создание объектов DataSet со строгой типизацией | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
caps.latest.revision: 5
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 5
---
# Создание объектов DataSet со строгой типизацией
При наличии схемы XML, соответствующей стандарту языка XSD, можно создать объект <xref:System.Data.DataSet> со строгой типизацией с помощью инструмента XSD.exe, предоставляемого [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].  
  
 \(Сведения о создании xsd из таблиц базы данных см. в разделе <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Работа с наборами данных в Visual Studio](http://msdn.microsoft.com/library/8bw9ksd6.aspx)\).  
  
 В следующем коде показан синтаксис создания **DataSet** с помощью данного инструмента.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 В этом синтаксисе директива `/d` служит для указанного инструмента указанием по созданию объекта **DataSet**, а директива `/l:` предписывает используемый язык \(например, C\# или Visual Basic .NET\).  Дополнительная директива `/eld` указывает на возможность использования [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] для создания запроса к созданному **DataSet**. Данный параметр используется при указании параметра `/d`.  Для получения дополнительной информации см. [Запрос к типизированным объектам DataSet](../../../../../docs/framework/data/adonet/querying-typed-datasets.md).  Дополнительная директива `/n:` служит для этого инструмента указанием по созданию пространства имен для **DataSet** с именем **XSDSchema.Namespace**.  Выходом команды является файл XSDSchemaFileName.cs, который можно скомпилировать и использовать в приложении ADO.NET.  Созданный код можно скомпилировать в виде библиотеки или модуля.  
  
 В следующем коде показан синтаксис для компиляции созданного кода в виде библиотеки с помощью компилятора C\# \(csc.exe\).  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 Директива `/t:` служит для этого инструмента указанием по компиляции библиотеки, а директива `/r:` указывает зависимые библиотеки, которые необходимо скомпилировать.  Выходом команды является файл XSDSchemaFileName.dll, который можно передать компилятору при компилировании приложения ADO.NET с помощью директивы `/r:`.  
  
 В следующем коде показан синтаксис обеспечения доступа к пространству имен, переданному инструменту XSD.exe в приложении ADO.NET.  
  
```vb  
Imports XSDSchema.Namespace  
  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 В следующем примере кода используется типизированный объект **DataSet** с именем **CustomerDataSet** для загрузки списка клиентов из базы данных **Northwind**.  После загрузки данных с помощью метода **Fill** в этом примере кода происходит обработка в цикле данных о каждом заказчике из таблицы **Customers** с помощью типизированного объекта **CustomersRow** \(**DataRow**\).  Благодаря этому обеспечивается прямой доступ к столбцу **CustomerID**, в отличие от получения доступа через объект **DataColumnCollection**.  
  
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
  
 Далее приводится схема XML, используемая для примера.  
  
```  
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
  
## См. также  
 <xref:System.Data.DataColumnCollection>   
 <xref:System.Data.DataSet>   
 [Типизированные объекты DataSets](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)