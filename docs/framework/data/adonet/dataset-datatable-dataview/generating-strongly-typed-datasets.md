---
title: Создание строго типизированных наборов данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 9accfb68c57384e12a59bae40ebe30a2d3e22877
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43526492"
---
# <a name="generating-strongly-typed-datasets"></a>Создание строго типизированных наборов данных
При наличии схемы XML, соответствующей стандарту языка XSD, можно создать объект <xref:System.Data.DataSet> со строгой типизацией с помощью инструмента XSD.exe, предоставляемого [!INCLUDE[winsdklong](../../../../../includes/winsdklong-md.md)].  
  
 (Чтобы сформировать xsd из таблиц базы данных, см. в разделе <xref:System.Data.DataSet.WriteXmlSchema%2A> или [работа с наборами данных в Visual Studio](https://msdn.microsoft.com/library/8bw9ksd6.aspx)).  
  
 Ниже показан синтаксис для создания **набора данных** с помощью этого средства.  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 В этом синтаксисе `/d` директива указывает, что для создания **набора данных**и `/l:` предписывает используемый язык (например, C# или Visual Basic .NET). Необязательный `/eld` директива указывает, что можно использовать [!INCLUDE[linq_dataset](../../../../../includes/linq-dataset-md.md)] для запроса к созданному **набора данных.** Данный параметр используется при указании параметра `/d`. Дополнительные сведения см. в разделе [запросе типизированных наборов DataSet](../../../../../docs/framework/data/adonet/querying-typed-datasets.md). Необязательный `/n:` директива указывает, что для пространства имен для **набора данных** вызывается **XSDSchema.Namespace**. Выходом команды является файл XSDSchemaFileName.cs, который можно скомпилировать и использовать в приложении ADO.NET. Созданный код можно скомпилировать в виде библиотеки или модуля.  
  
 В следующем коде показан синтаксис для компиляции созданного кода в виде библиотеки с помощью компилятора C# (csc.exe).  
  
```  
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
  
 В следующем примере кода используется типизированный **набора данных** с именем **CustomerDataSet** загрузить список клиентов из **Northwind** базы данных. После загрузки данных с помощью **заполнения** метод, пример выполняет цикл по каждому клиенту в **клиентов** таблицы с помощью типизированного **CustomersRow** ( **DataRow**) объекта. Это обеспечивает прямой доступ к **CustomerID** столбец, в отличие от до **DataColumnCollection**.  
  
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
 <xref:System.Data.DataColumnCollection>  
 <xref:System.Data.DataSet>  
 [Типизированные наборы данных](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/typed-datasets.md)  
 [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
