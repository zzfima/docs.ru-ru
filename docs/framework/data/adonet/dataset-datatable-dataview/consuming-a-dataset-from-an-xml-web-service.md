---
title: Потребление набора данных из веб-службы XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: d835ffe7a10492ee731de8e5301e6d34545f9c32
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151394"
---
# <a name="consuming-a-dataset-from-an-xml-web-service"></a><span data-ttu-id="b2936-102">Потребление набора данных из веб-службы XML</span><span class="sxs-lookup"><span data-stu-id="b2936-102">Consuming a DataSet from an XML Web Service</span></span>
<span data-ttu-id="b2936-103">Объект <xref:System.Data.DataSet> не имеет привязки к каким-либо источникам, что позволяет частично упростить передачу данных через Интернет.</span><span class="sxs-lookup"><span data-stu-id="b2936-103">The <xref:System.Data.DataSet> was architected with a disconnected design, in part to facilitate the convenient transport of data over the Internet.</span></span> <span data-ttu-id="b2936-104">**DataSet** является "серийным", поскольку он может быть указан в качестве ввода или вывода из веб-служб XML без какого-либо дополнительного кодирования, необходимого для потоковой передачи содержимого **DataSet** из веб-службы XML клиенту и обратно.</span><span class="sxs-lookup"><span data-stu-id="b2936-104">The **DataSet** is "serializable" in that it can be specified as an input to or output from XML Web services without any additional coding required to stream the contents of the **DataSet** from an XML Web service to a client and back.</span></span> <span data-ttu-id="b2936-105">**DataSet** неявно преобразуется в поток XML с помощью формата DiffGram, переосланный по сети, а затем реконструированный из потока XML в качестве **DataSet** на принимающем конце.</span><span class="sxs-lookup"><span data-stu-id="b2936-105">The **DataSet** is implicitly converted to an XML stream using the DiffGram format, sent over the network, and then reconstructed from the XML stream as a **DataSet** on the receiving end.</span></span> <span data-ttu-id="b2936-106">Это обеспечивает очень простой и гибкий метод передачи и получения реляционных данных с помощью веб-служб XML.</span><span class="sxs-lookup"><span data-stu-id="b2936-106">This gives you a very simple and flexible method for transmitting and returning relational data using XML Web services.</span></span> <span data-ttu-id="b2936-107">Для получения дополнительной информации о [DiffGrams](diffgrams.md)формате DiffGram см.</span><span class="sxs-lookup"><span data-stu-id="b2936-107">For more information about the DiffGram format, see [DiffGrams](diffgrams.md).</span></span>  
  
 <span data-ttu-id="b2936-108">В следующем примере показано, как создать веб-службу XML и клиента, которые используют **DataSet** для транспортировки реляционных данных (включая измененные данные) и разрешать любые обновления обратно в исходный источник данных.</span><span class="sxs-lookup"><span data-stu-id="b2936-108">The following example shows how to create an XML Web service and client that use the **DataSet** to transport relational data (including modified data) and resolve any updates back to the original data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b2936-109">При создании веб-службы XML следует всегда учитывать возможные вопросы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b2936-109">We recommend that you always consider security implications when creating an XML Web service.</span></span> <span data-ttu-id="b2936-110">Для получения информации о защите веб-службы XML см [ASP.NET.](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b2936-110">For information on securing an XML Web service, see [Securing XML Web Services Created Using ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).</span></span>  
  
### <a name="to-create-an-xml-web-service-that-returns-and-consumes-a-dataset"></a><span data-ttu-id="b2936-111">Создание веб-службы XML, которая возвращает и потребляет объект DataSet</span><span class="sxs-lookup"><span data-stu-id="b2936-111">To create an XML Web service that returns and consumes a DataSet</span></span>  
  
1. <span data-ttu-id="b2936-112">Создайте веб-службу XML.</span><span class="sxs-lookup"><span data-stu-id="b2936-112">Create the XML Web service.</span></span>  
  
     <span data-ttu-id="b2936-113">В этом примере создается веб-служба XML, которая возвращает данные, в данном случае список клиентов из базы данных **Northwind,** и получает **DataSet** с обновлениями данных, которые служба XML Web разрешает обратно в исходный источник данных.</span><span class="sxs-lookup"><span data-stu-id="b2936-113">In the example, an XML Web service is created that returns data, in this case a list of customers from the **Northwind** database, and receives a **DataSet** with updates to the data, which the XML Web service resolves back to the original data source.</span></span>  
  
     <span data-ttu-id="b2936-114">Веб-сервис XML предоставляет два способа: **GetCustomers,** чтобы вернуть список клиентов, и **UpdateCustomers**, чтобы решить обновления обратно в источник данных.</span><span class="sxs-lookup"><span data-stu-id="b2936-114">The XML Web service exposes two methods: **GetCustomers**, to return the list of customers, and **UpdateCustomers**, to resolve updates back to the data source.</span></span> <span data-ttu-id="b2936-115">Веб-служба XML хранится в файле на веб-сервере DataSetSample.asmx.</span><span class="sxs-lookup"><span data-stu-id="b2936-115">The XML Web service is stored in a file on the Web server called DataSetSample.asmx.</span></span> <span data-ttu-id="b2936-116">В следующем коде описано содержимое файла DataSetSample.asmx.</span><span class="sxs-lookup"><span data-stu-id="b2936-116">The following code outlines the contents of DataSetSample.asmx.</span></span>  
  
    ```vb  
    <% @ WebService Language = "vb" Class = "Sample" %>  
    Imports System  
    Imports System.Data  
    Imports System.Data.SqlClient  
    Imports System.Web.Services  
  
    <WebService(Namespace:="http://microsoft.com/webservices/")> _  
    Public Class Sample  
  
    Public connection As SqlConnection = New SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind")  
  
      <WebMethod( Description := "Returns Northwind Customers", EnableSession := False )> _  
      Public Function GetCustomers() As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
          "SELECT CustomerID, CompanyName FROM Customers", connection)  
  
        Dim custDS As DataSet = New DataSet()  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey  
        adapter.Fill(custDS, "Customers")  
  
        Return custDS  
      End Function  
  
      <WebMethod( Description := "Updates Northwind Customers", EnableSession := False )> _  
      Public Function UpdateCustomers(custDS As DataSet) As DataSet  
        Dim adapter As SqlDataAdapter = New SqlDataAdapter()  
  
        adapter.InsertCommand = New SqlCommand( _  
          "INSERT INTO Customers (CustomerID, CompanyName) " & _  
          "Values(@CustomerID, @CompanyName)", connection)  
        adapter.InsertCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.InsertCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        adapter.UpdateCommand = New SqlCommand( _  
          "UPDATE Customers Set CustomerID = @CustomerID, " & _  
          "CompanyName = @CompanyName WHERE CustomerID = " & _  
          @OldCustomerID", connection)  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        adapter.UpdateCommand.Parameters.Add( _  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName")  
  
        Dim parameter As SqlParameter = _  
          adapter.UpdateCommand.Parameters.Add( _  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.DeleteCommand = New SqlCommand( _  
          "DELETE FROM Customers WHERE CustomerID = @CustomerID", _  
          connection)  
        parameter = adapter.DeleteCommand.Parameters.Add( _  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID")  
        parameter.SourceVersion = DataRowVersion.Original  
  
        adapter.Update(custDS, "Customers")  
  
        Return custDS  
      End Function  
    End Class  
    ```  
  
    ```csharp  
    <% @ WebService Language = "C#" Class = "Sample" %>  
    using System;  
    using System.Data;  
    using System.Data.SqlClient;  
    using System.Web.Services;  
  
    [WebService(Namespace="http://microsoft.com/webservices/")]  
    public class Sample  
    {  
      public SqlConnection connection = new SqlConnection("Data Source=(local);Integrated Security=SSPI;Initial Catalog=Northwind");  
  
      [WebMethod( Description = "Returns Northwind Customers", EnableSession = false )]  
      public DataSet GetCustomers()  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter(  
          "SELECT CustomerID, CompanyName FROM Customers", connection);  
  
        DataSet custDS = new DataSet();  
        adapter.MissingSchemaAction = MissingSchemaAction.AddWithKey;  
        adapter.Fill(custDS, "Customers");  
  
        return custDS;  
      }  
  
      [WebMethod( Description = "Updates Northwind Customers",  
        EnableSession = false )]  
      public DataSet UpdateCustomers(DataSet custDS)  
      {  
        SqlDataAdapter adapter = new SqlDataAdapter();  
  
        adapter.InsertCommand = new SqlCommand(  
          "INSERT INTO Customers (CustomerID, CompanyName) " +  
          "Values(@CustomerID, @CompanyName)", connection);  
        adapter.InsertCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.InsertCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
  
        adapter.UpdateCommand = new SqlCommand(  
          "UPDATE Customers Set CustomerID = @CustomerID, " +  
          "CompanyName = @CompanyName WHERE CustomerID = " +  
          "@OldCustomerID", connection);  
        adapter.UpdateCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        adapter.UpdateCommand.Parameters.Add(  
          "@CompanyName", SqlDbType.NChar, 15, "CompanyName");  
        SqlParameter parameter = adapter.UpdateCommand.Parameters.Add(  
          "@OldCustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.DeleteCommand = new SqlCommand(  
        "DELETE FROM Customers WHERE CustomerID = @CustomerID",  
         connection);  
        parameter = adapter.DeleteCommand.Parameters.Add(  
          "@CustomerID", SqlDbType.NChar, 5, "CustomerID");  
        parameter.SourceVersion = DataRowVersion.Original;  
  
        adapter.Update(custDS, "Customers");  
  
        return custDS;  
      }  
    }  
    ```  
  
     <span data-ttu-id="b2936-117">В типичном сценарии метод **UpdateCustomers** будет написан для выявления оптимистических нарушений параллелизма.</span><span class="sxs-lookup"><span data-stu-id="b2936-117">In a typical scenario, the **UpdateCustomers** method would be written to catch optimistic concurrency violations.</span></span> <span data-ttu-id="b2936-118">Для простоты в данном примере это опущено.</span><span class="sxs-lookup"><span data-stu-id="b2936-118">For simplicity, the example does not include this.</span></span> <span data-ttu-id="b2936-119">Для получения дополнительной информации об оптимистичной параллелизм, [см.](../optimistic-concurrency.md)</span><span class="sxs-lookup"><span data-stu-id="b2936-119">For more information about optimistic concurrency, see [Optimistic Concurrency](../optimistic-concurrency.md).</span></span>  
  
2. <span data-ttu-id="b2936-120">Создайте посредник веб-службы XML.</span><span class="sxs-lookup"><span data-stu-id="b2936-120">Create an XML Web service proxy.</span></span>  
  
     <span data-ttu-id="b2936-121">Клиентам веб-службы XML необходим посредник SOAP, чтобы использовать предоставленные методы.</span><span class="sxs-lookup"><span data-stu-id="b2936-121">Clients of the XML Web service require a SOAP proxy in order to consume the exposed methods.</span></span> <span data-ttu-id="b2936-122">Этот посредник может быть создан с помощью среды Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b2936-122">You can have Visual Studio generate this proxy for you.</span></span> <span data-ttu-id="b2936-123">Если задать веб-ссылку на существующую веб-службу из Visual Studio, все действия, описанные в этом шаге, будут производиться незаметно.</span><span class="sxs-lookup"><span data-stu-id="b2936-123">By setting a Web reference to an existing Web service from within Visual Studio, all the behavior described in this step occurs transparently.</span></span> <span data-ttu-id="b2936-124">Если требуется создать класс посредника самостоятельно, читайте этот раздел далее.</span><span class="sxs-lookup"><span data-stu-id="b2936-124">If you want to create the proxy class yourself, continue with this discussion.</span></span> <span data-ttu-id="b2936-125">Однако в большинстве случаев достаточно создать класс посредника для клиентского приложения с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b2936-125">In most circumstances, however, using Visual Studio to create the proxy class for the client application is sufficient.</span></span>  
  
     <span data-ttu-id="b2936-126">Посредник можно создать с помощью средства WSDL.</span><span class="sxs-lookup"><span data-stu-id="b2936-126">A proxy can be created using the Web Services Description Language Tool.</span></span> <span data-ttu-id="b2936-127">Например, если веб-служба XML выставлена на URL, `http://myserver/data/DataSetSample.asmx`выдайте команду, такую как следующая, чтобы создать прокси Visual Basic .NET с пространством имен **WebData.DSSample** и хранить его в файле sample.vb.</span><span class="sxs-lookup"><span data-stu-id="b2936-127">For example, if the XML Web service is exposed at the URL `http://myserver/data/DataSetSample.asmx`, issue a command such as the following to create a Visual Basic .NET proxy with a namespace of **WebData.DSSample** and store it in the file sample.vb.</span></span>  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="b2936-128">Чтобы создать посредник C# в файле sample.cs, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b2936-128">To create a C# proxy in the file sample.cs, issue the following command.</span></span>  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="b2936-129">После создания посредник можно будет скомпилировать как библиотеку и импортировать в клиент веб-службы XML.</span><span class="sxs-lookup"><span data-stu-id="b2936-129">The proxy can then be compiled as a library and imported into the XML Web service client.</span></span> <span data-ttu-id="b2936-130">Чтобы скомпилировать код посредника Visual Basic .NET, хранящийся в файле sample.vb, в файл sample.dll, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b2936-130">To compile the Visual Basic .NET proxy code stored in sample.vb as sample.dll, issue the following command.</span></span>  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     <span data-ttu-id="b2936-131">Чтобы скомпилировать код посредника C#, хранящийся в файле sample.cs, в файл sample.dll, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b2936-131">To compile the C# proxy code stored in sample.cs as sample.dll, issue the following command.</span></span>  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3. <span data-ttu-id="b2936-132">Создайте клиент веб-службы XML.</span><span class="sxs-lookup"><span data-stu-id="b2936-132">Create an XML Web service client.</span></span>  
  
     <span data-ttu-id="b2936-133">Если вы хотите, чтобы Visual Studio создала для вас прокси-класс Web service, просто создайте клиентский проект, а в окне Solution Explorer щелкните по проекту, нажмите **«Добавить веб-справку»** и выберите Web-службу из списка доступных Web-сервисов (для этого может потребоваться предоставление адреса конечной точки Web service, если веб-служба недоступна в текущем решении или на текущем компьютере). При создании прокси-сервера XML Web (как описано на предыдущем этапе), можно импортировать его в свой клиентский код и использовать методы веб-службы XML.</span><span class="sxs-lookup"><span data-stu-id="b2936-133">If you want to have Visual Studio generate the Web service proxy class for you, simply create the client project, and, in the Solution Explorer window, right-click the project, click **Add Web Reference**, and select the Web service from the list of available Web services (this may require supplying the address of the Web service endpoint, if the Web service isn't available within the current solution, or on the current computer.) If you create the XML Web service proxy yourself (as described in the previous step), you can import it into your client code and consume the XML Web service methods.</span></span> <span data-ttu-id="b2936-134">Следующий пример кода импортирует библиотеку прокси, звонит **GetCustomers,** чтобы получить список клиентов, добавляет нового клиента, а затем возвращает **DataSet** с обновлениями **для UpdateCustomers**.</span><span class="sxs-lookup"><span data-stu-id="b2936-134">The following sample code imports the proxy library, calls **GetCustomers** to get a list of customers, adds a new customer, and then returns a **DataSet** with the updates to **UpdateCustomers**.</span></span>  
  
     <span data-ttu-id="b2936-135">Обратите внимание, что пример передает **DataSet,** возвращенный **DataSet.GetChanges** для **обновленияКлиентов,** потому что только измененные строки должны быть переданы **UpdateCustomers.**</span><span class="sxs-lookup"><span data-stu-id="b2936-135">Notice that the example passes the **DataSet** returned by **DataSet.GetChanges** to **UpdateCustomers** because only modified rows need to be passed to **UpdateCustomers**.</span></span> <span data-ttu-id="b2936-136">**UpdateCustomers** возвращает разрешенный **DataSet,** который затем можно **слить** в существующий **DataSet,** чтобы включить разрешенные изменения и любую информацию об ошибке строки из обновления.</span><span class="sxs-lookup"><span data-stu-id="b2936-136">**UpdateCustomers** returns the resolved **DataSet**, which you can then **Merge** into the existing **DataSet** to incorporate the resolved changes and any row error information from the update.</span></span> <span data-ttu-id="b2936-137">Следующий код предполагает, что вы использовали Visual Studio для создания веб-ссылки, и что вы переименовали веб-ссылку на DsSample в диалоговом окне **Добавления Web Reference.**</span><span class="sxs-lookup"><span data-stu-id="b2936-137">The following code assumes that you have used Visual Studio to create the Web reference, and that you have renamed the Web reference to DsSample in the **Add Web Reference** dialog box.</span></span>  
  
    ```vb  
    Imports System  
    Imports System.Data  
  
    Public Class Client  
  
      Public Shared Sub Main()  
        Dim proxySample As New DsSample.Sample ()  ' Proxy object.  
        Dim customersDataSet As DataSet = proxySample.GetCustomers()  
        Dim customersTable As DataTable = _  
          customersDataSet.Tables("Customers")  
  
        Dim rowAs DataRow = customersTable.NewRow()  
        row("CustomerID") = "ABCDE"  
        row("CompanyName") = "New Company Name"  
        customersTable.Rows.Add(row)  
  
        Dim updateDataSet As DataSet = _  
          proxySample.UpdateCustomers(customersDataSet.GetChanges())  
  
        customersDataSet.Merge(updateDataSet)  
        customersDataSet.AcceptChanges()  
      End Sub  
    End Class  
    ```  
  
    ```csharp  
    using System;  
    using System.Data;  
  
    public class Client  
    {  
      public static void Main()  
      {  
        Sample proxySample = new DsSample.Sample();  // Proxy object.  
        DataSet customersDataSet = proxySample.GetCustomers();  
        DataTable customersTable = customersDataSet.Tables["Customers"];  
  
        DataRow row = customersTable.NewRow();  
        row["CustomerID"] = "ABCDE";  
        row["CompanyName"] = "New Company Name";  
        customersTable.Rows.Add(row);  
  
        DataSet updateDataSet = new DataSet();  
  
        updateDataSet =
          proxySample.UpdateCustomers(customersDataSet.GetChanges());  
  
        customersDataSet.Merge(updateDataSet);  
        customersDataSet.AcceptChanges();  
      }  
    }  
    ```  
  
     <span data-ttu-id="b2936-138">Если класс посредника создается самостоятельно, следует выполнить следующие дополнительные шаги.</span><span class="sxs-lookup"><span data-stu-id="b2936-138">If you decide to create the proxy class yourself, you must take the following extra steps.</span></span> <span data-ttu-id="b2936-139">Чтобы скомпилировать образец, предоставьте созданную библиотеку посредника (sample.dll) и связанные с ней библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="b2936-139">To compile the sample, supply the proxy library that was created (sample.dll) and the related .NET libraries.</span></span> <span data-ttu-id="b2936-140">Чтобы скомпилировать версию Visual Basic .NET образца, которая хранится в файле client.vb, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b2936-140">To compile the Visual Basic .NET version of the sample, stored in the file client.vb, issue the following command.</span></span>  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     <span data-ttu-id="b2936-141">Чтобы скомпилировать версию C# образца, которая хранится в файле client.cs, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b2936-141">To compile the C# version of the sample, stored in the file client.cs, issue the following command.</span></span>  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b2936-142">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="b2936-142">See also</span></span>

- [<span data-ttu-id="b2936-143">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b2936-143">ADO.NET</span></span>](../index.md)
- [<span data-ttu-id="b2936-144">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="b2936-144">DataSets, DataTables, and DataViews</span></span>](index.md)
- [<span data-ttu-id="b2936-145">DataTables</span><span class="sxs-lookup"><span data-stu-id="b2936-145">DataTables</span></span>](datatables.md)
- [<span data-ttu-id="b2936-146">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="b2936-146">Populating a DataSet from a DataAdapter</span></span>](../populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="b2936-147">Обновление источников данных с объектами DataAdapter</span><span class="sxs-lookup"><span data-stu-id="b2936-147">Updating Data Sources with DataAdapters</span></span>](../updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="b2936-148">Параметры DataAdapter</span><span class="sxs-lookup"><span data-stu-id="b2936-148">DataAdapter Parameters</span></span>](../dataadapter-parameters.md)
- <span data-ttu-id="b2936-149">[Инструмент языка описания веб-служб (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b2936-149">[Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span></span>
- [<span data-ttu-id="b2936-150">Общие сведения об ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b2936-150">ADO.NET Overview</span></span>](../ado-net-overview.md)
