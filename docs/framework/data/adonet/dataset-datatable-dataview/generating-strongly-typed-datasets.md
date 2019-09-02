---
title: Создание строго типизированных наборов данных
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 54333cbf-bb43-4314-a7d4-6dc1dd1c44b3
ms.openlocfilehash: 9bff69e28aa17da87da7e94d4e110c0375f043ae
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/31/2019
ms.locfileid: "70203707"
---
# <a name="generating-strongly-typed-datasets"></a><span data-ttu-id="97c14-102">Создание строго типизированных наборов данных</span><span class="sxs-lookup"><span data-stu-id="97c14-102">Generating Strongly Typed DataSets</span></span>
<span data-ttu-id="97c14-103">Учитывая схему XML, которая соответствует стандарту языка определения схемы XML (XSD), можно создать строго типизированную <xref:System.Data.DataSet> программу с помощью средства XSD. exe, поставляемого с пакетом средств разработки программного обеспечения (SDK) для Windows.</span><span class="sxs-lookup"><span data-stu-id="97c14-103">Given an XML Schema that complies with the XML Schema definition language (XSD) standard, you can generate a strongly typed <xref:System.Data.DataSet> using the XSD.exe tool provided with the Windows Software Development Kit (SDK).</span></span>  
  
 <span data-ttu-id="97c14-104">(Чтобы создать схему XSD из таблиц базы данных, <xref:System.Data.DataSet.WriteXmlSchema%2A> см. статью или [Работа с DataSets в Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span><span class="sxs-lookup"><span data-stu-id="97c14-104">(To create an xsd from database tables, see <xref:System.Data.DataSet.WriteXmlSchema%2A> or [Working with Datasets in Visual Studio](/visualstudio/data-tools/dataset-tools-in-visual-studio)).</span></span>  
  
 <span data-ttu-id="97c14-105">В следующем коде показан синтаксис для создания **набора данных** с помощью этого средства.</span><span class="sxs-lookup"><span data-stu-id="97c14-105">The following code shows the syntax for generating a **DataSet** using this tool.</span></span>  
  
```  
xsd.exe /d /l:CS XSDSchemaFileName.xsd /eld /n:XSDSchema.Namespace  
```  
  
 <span data-ttu-id="97c14-106">В этом синтаксисе `/d` директива указывает средству создать **набор данных**, а `/l:` указывает, какой язык следует использовать (например, C# или Visual Basic .NET).</span><span class="sxs-lookup"><span data-stu-id="97c14-106">In this syntax, the `/d` directive tells the tool to generate a **DataSet**, and the `/l:` tells the tool what language to use (for example, C# or Visual Basic .NET).</span></span> <span data-ttu-id="97c14-107">Необязательная `/eld` директива указывает, что можно использовать LINQ to DataSet для запроса к созданному **набору данных.**</span><span class="sxs-lookup"><span data-stu-id="97c14-107">The optional `/eld` directive specifies that you can use LINQ to DataSet to query against the generated **DataSet.**</span></span> <span data-ttu-id="97c14-108">Данный параметр используется при указании параметра `/d`.</span><span class="sxs-lookup"><span data-stu-id="97c14-108">This option is used when the `/d` option is also specified.</span></span> <span data-ttu-id="97c14-109">Дополнительные сведения см. в разделе [запросы к типизированным наборам данных](../querying-typed-datasets.md).</span><span class="sxs-lookup"><span data-stu-id="97c14-109">For more information, see [Querying Typed DataSets](../querying-typed-datasets.md).</span></span> <span data-ttu-id="97c14-110">Необязательная `/n:` директива указывает средству создавать пространство имен для **набора данных** с именем **кссдсчема. Namespace**.</span><span class="sxs-lookup"><span data-stu-id="97c14-110">The optional `/n:` directive tells the tool to also generate a namespace for the **DataSet** called **XSDSchema.Namespace**.</span></span> <span data-ttu-id="97c14-111">Выходом команды является файл XSDSchemaFileName.cs, который можно скомпилировать и использовать в приложении ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="97c14-111">The output of the command is XSDSchemaFileName.cs, which can be compiled and used in an ADO.NET application.</span></span> <span data-ttu-id="97c14-112">Созданный код можно скомпилировать в виде библиотеки или модуля.</span><span class="sxs-lookup"><span data-stu-id="97c14-112">The generated code can be compiled as a library or a module.</span></span>  
  
 <span data-ttu-id="97c14-113">В следующем коде показан синтаксис для компиляции созданного кода в виде библиотеки с помощью компилятора C# (csc.exe).</span><span class="sxs-lookup"><span data-stu-id="97c14-113">The following code shows the syntax for compiling the generated code as a library using the C# compiler (csc.exe).</span></span>  
  
```  
csc.exe /t:library XSDSchemaFileName.cs /r:System.dll /r:System.Data.dll  
```  
  
 <span data-ttu-id="97c14-114">Директива `/t:` служит для этого инструмента указанием по компиляции библиотеки, а директива `/r:` указывает зависимые библиотеки, которые необходимо скомпилировать.</span><span class="sxs-lookup"><span data-stu-id="97c14-114">The `/t:` directive tells the tool to compile to a library, and the `/r:` directives specify dependent libraries required to compile.</span></span> <span data-ttu-id="97c14-115">Выходом команды является файл XSDSchemaFileName.dll, который можно передать компилятору при компилировании приложения ADO.NET с помощью директивы `/r:`.</span><span class="sxs-lookup"><span data-stu-id="97c14-115">The output of the command is XSDSchemaFileName.dll, which can be passed to the compiler when compiling an ADO.NET application with the `/r:` directive.</span></span>  
  
 <span data-ttu-id="97c14-116">В следующем коде показан синтаксис обеспечения доступа к пространству имен, переданному инструменту XSD.exe в приложении ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="97c14-116">The following code shows the syntax for accessing the namespace passed to XSD.exe in an ADO.NET application.</span></span>  
  
```vb  
Imports XSDSchema.Namespace  
```  
  
```csharp  
using XSDSchema.Namespace;  
```  
  
 <span data-ttu-id="97c14-117">В следующем примере кода используется типизированный **набор данных** с именем **кустомердатасет** для загрузки списка клиентов из базы данных **Northwind** .</span><span class="sxs-lookup"><span data-stu-id="97c14-117">The following code example uses a typed **DataSet** named **CustomerDataSet** to load a list of customers from the **Northwind** database.</span></span> <span data-ttu-id="97c14-118">После загрузки данных с помощью метода **Fill** в примере выполняется циклический перебор каждого клиента в таблице **Customers** с помощью объекта типизированной **кустомерсров** (**DataRow**).</span><span class="sxs-lookup"><span data-stu-id="97c14-118">Once the data is loaded using the **Fill** method, the example loops through each customer in the **Customers** table using the typed **CustomersRow** (**DataRow**) object.</span></span> <span data-ttu-id="97c14-119">Это обеспечивает прямой доступ к столбцу **CustomerID** , в отличие от **датаколумнколлектион**.</span><span class="sxs-lookup"><span data-stu-id="97c14-119">This provides direct access to the **CustomerID** column, as opposed to through the **DataColumnCollection**.</span></span>  
  
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
  
 <span data-ttu-id="97c14-120">Далее приводится схема XML, используемая для примера.</span><span class="sxs-lookup"><span data-stu-id="97c14-120">Following is the XML Schema used for the example.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="97c14-121">См. также</span><span class="sxs-lookup"><span data-stu-id="97c14-121">See also</span></span>

- <xref:System.Data.DataColumnCollection>
- <xref:System.Data.DataSet>
- [<span data-ttu-id="97c14-122">Типизированные наборы данных</span><span class="sxs-lookup"><span data-stu-id="97c14-122">Typed DataSets</span></span>](typed-datasets.md)
- [<span data-ttu-id="97c14-123">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="97c14-123">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="97c14-124">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="97c14-124">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
