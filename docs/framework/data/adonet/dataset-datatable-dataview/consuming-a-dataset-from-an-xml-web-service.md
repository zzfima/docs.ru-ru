---
title: Потребление набора данных из веб-службы XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: acf5af755d6322f75a616005cc904d464564bc81
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69915820"
---
# <a name="consuming-a-dataset-from-an-xml-web-service"></a><span data-ttu-id="b6be5-102">Потребление набора данных из веб-службы XML</span><span class="sxs-lookup"><span data-stu-id="b6be5-102">Consuming a DataSet from an XML Web Service</span></span>
<span data-ttu-id="b6be5-103">Объект <xref:System.Data.DataSet> не имеет привязки к каким-либо источникам, что позволяет частично упростить передачу данных через Интернет.</span><span class="sxs-lookup"><span data-stu-id="b6be5-103">The <xref:System.Data.DataSet> was architected with a disconnected design, in part to facilitate the convenient transport of data over the Internet.</span></span> <span data-ttu-id="b6be5-104">**Набор данных** является сериализуемым в том, что он может быть указан в качестве входных данных или выходных данных из веб-служб XML без дополнительного программирования, необходимого для потоковой передачи содержимого **набора данных** из веб-службы XML в клиент и обратно.</span><span class="sxs-lookup"><span data-stu-id="b6be5-104">The **DataSet** is "serializable" in that it can be specified as an input to or output from XML Web services without any additional coding required to stream the contents of the **DataSet** from an XML Web service to a client and back.</span></span> <span data-ttu-id="b6be5-105">**Набор данных** неявно преобразуется в XML-поток с помощью формата DiffGram, передается по сети, а затем перестраивается из потока XML в качестве **набора данных** на стороне получения.</span><span class="sxs-lookup"><span data-stu-id="b6be5-105">The **DataSet** is implicitly converted to an XML stream using the DiffGram format, sent over the network, and then reconstructed from the XML stream as a **DataSet** on the receiving end.</span></span> <span data-ttu-id="b6be5-106">Это обеспечивает очень простой и гибкий метод передачи и получения реляционных данных с помощью веб-служб XML.</span><span class="sxs-lookup"><span data-stu-id="b6be5-106">This gives you a very simple and flexible method for transmitting and returning relational data using XML Web services.</span></span> <span data-ttu-id="b6be5-107">Дополнительные сведения о формате DiffGram см. в разделе [дельтами](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span><span class="sxs-lookup"><span data-stu-id="b6be5-107">For more information about the DiffGram format, see [DiffGrams](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).</span></span>  
  
 <span data-ttu-id="b6be5-108">В следующем примере показано, как создать веб-службу XML и клиент, которые используют **набор данных** для передачи реляционных данных (включая измененные данные) и разрешения всех обновлений обратно в исходный источник данных.</span><span class="sxs-lookup"><span data-stu-id="b6be5-108">The following example shows how to create an XML Web service and client that use the **DataSet** to transport relational data (including modified data) and resolve any updates back to the original data source.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b6be5-109">При создании веб-службы XML следует всегда учитывать возможные вопросы безопасности.</span><span class="sxs-lookup"><span data-stu-id="b6be5-109">We recommend that you always consider security implications when creating an XML Web service.</span></span> <span data-ttu-id="b6be5-110">Сведения о защите веб-службы XML см. в разделе [Защита веб-служб XML, созданных с помощью ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="b6be5-110">For information on securing an XML Web service, see [Securing XML Web Services Created Using ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).</span></span>  
  
### <a name="to-create-an-xml-web-service-that-returns-and-consumes-a-dataset"></a><span data-ttu-id="b6be5-111">Создание веб-службы XML, которая возвращает и потребляет объект DataSet</span><span class="sxs-lookup"><span data-stu-id="b6be5-111">To create an XML Web service that returns and consumes a DataSet</span></span>  
  
1. <span data-ttu-id="b6be5-112">Создайте веб-службу XML.</span><span class="sxs-lookup"><span data-stu-id="b6be5-112">Create the XML Web service.</span></span>  
  
     <span data-ttu-id="b6be5-113">В этом примере создается веб-служба XML, которая возвращает данные, в данном случае список клиентов из базы данных **Northwind** и получает **набор данных** с обновлениями данных, которые веб-служба XML разрешается обратно в исходный источник данных.</span><span class="sxs-lookup"><span data-stu-id="b6be5-113">In the example, an XML Web service is created that returns data, in this case a list of customers from the **Northwind** database, and receives a **DataSet** with updates to the data, which the XML Web service resolves back to the original data source.</span></span>  
  
     <span data-ttu-id="b6be5-114">Веб-служба XML предоставляет два следующих метода: **Клиенты**, чтобы получить список клиентов и **коде**для разрешения обновлений обратно в источник данных.</span><span class="sxs-lookup"><span data-stu-id="b6be5-114">The XML Web service exposes two methods: **GetCustomers**, to return the list of customers, and **UpdateCustomers**, to resolve updates back to the data source.</span></span> <span data-ttu-id="b6be5-115">Веб-служба XML хранится в файле на веб-сервере DataSetSample.asmx.</span><span class="sxs-lookup"><span data-stu-id="b6be5-115">The XML Web service is stored in a file on the Web server called DataSetSample.asmx.</span></span> <span data-ttu-id="b6be5-116">В следующем коде описано содержимое файла DataSetSample.asmx.</span><span class="sxs-lookup"><span data-stu-id="b6be5-116">The following code outlines the contents of DataSetSample.asmx.</span></span>  
  
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
  
     <span data-ttu-id="b6be5-117">В типичном сценарии метод **коде** будет написан для перехвата нарушений оптимистической блокировки.</span><span class="sxs-lookup"><span data-stu-id="b6be5-117">In a typical scenario, the **UpdateCustomers** method would be written to catch optimistic concurrency violations.</span></span> <span data-ttu-id="b6be5-118">Для простоты в данном примере это опущено.</span><span class="sxs-lookup"><span data-stu-id="b6be5-118">For simplicity, the example does not include this.</span></span> <span data-ttu-id="b6be5-119">Дополнительные сведения о оптимистичном параллелизме см. в разделе [Оптимистическая блокировка](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).</span><span class="sxs-lookup"><span data-stu-id="b6be5-119">For more information about optimistic concurrency, see [Optimistic Concurrency](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).</span></span>  
  
2. <span data-ttu-id="b6be5-120">Создайте посредник веб-службы XML.</span><span class="sxs-lookup"><span data-stu-id="b6be5-120">Create an XML Web service proxy.</span></span>  
  
     <span data-ttu-id="b6be5-121">Клиентам веб-службы XML необходим посредник SOAP, чтобы использовать предоставленные методы.</span><span class="sxs-lookup"><span data-stu-id="b6be5-121">Clients of the XML Web service require a SOAP proxy in order to consume the exposed methods.</span></span> <span data-ttu-id="b6be5-122">Этот посредник может быть создан с помощью среды Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6be5-122">You can have Visual Studio generate this proxy for you.</span></span> <span data-ttu-id="b6be5-123">Если задать веб-ссылку на существующую веб-службу из Visual Studio, все действия, описанные в этом шаге, будут производиться незаметно.</span><span class="sxs-lookup"><span data-stu-id="b6be5-123">By setting a Web reference to an existing Web service from within Visual Studio, all the behavior described in this step occurs transparently.</span></span> <span data-ttu-id="b6be5-124">Если требуется создать класс посредника самостоятельно, читайте этот раздел далее.</span><span class="sxs-lookup"><span data-stu-id="b6be5-124">If you want to create the proxy class yourself, continue with this discussion.</span></span> <span data-ttu-id="b6be5-125">Однако в большинстве случаев достаточно создать класс посредника для клиентского приложения с помощью Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b6be5-125">In most circumstances, however, using Visual Studio to create the proxy class for the client application is sufficient.</span></span>  
  
     <span data-ttu-id="b6be5-126">Посредник можно создать с помощью средства WSDL.</span><span class="sxs-lookup"><span data-stu-id="b6be5-126">A proxy can be created using the Web Services Description Language Tool.</span></span> <span data-ttu-id="b6be5-127">Например, если веб-служба XML предоставляется по URL-адресу `http://myserver/data/DataSetSample.asmx`, выполните следующую команду, чтобы создать Visual Basic прокси .NET с пространством имен **дссампле** и сохранить его в файле Sample. vb.</span><span class="sxs-lookup"><span data-stu-id="b6be5-127">For example, if the XML Web service is exposed at the URL `http://myserver/data/DataSetSample.asmx`, issue a command such as the following to create a Visual Basic .NET proxy with a namespace of **WebData.DSSample** and store it in the file sample.vb.</span></span>  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="b6be5-128">Чтобы создать посредник C# в файле sample.cs, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b6be5-128">To create a C# proxy in the file sample.cs, issue the following command.</span></span>  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     <span data-ttu-id="b6be5-129">После создания посредник можно будет скомпилировать как библиотеку и импортировать в клиент веб-службы XML.</span><span class="sxs-lookup"><span data-stu-id="b6be5-129">The proxy can then be compiled as a library and imported into the XML Web service client.</span></span> <span data-ttu-id="b6be5-130">Чтобы скомпилировать код посредника Visual Basic .NET, хранящийся в файле sample.vb, в файл sample.dll, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b6be5-130">To compile the Visual Basic .NET proxy code stored in sample.vb as sample.dll, issue the following command.</span></span>  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     <span data-ttu-id="b6be5-131">Чтобы скомпилировать код посредника C#, хранящийся в файле sample.cs, в файл sample.dll, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b6be5-131">To compile the C# proxy code stored in sample.cs as sample.dll, issue the following command.</span></span>  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3. <span data-ttu-id="b6be5-132">Создайте клиент веб-службы XML.</span><span class="sxs-lookup"><span data-stu-id="b6be5-132">Create an XML Web service client.</span></span>  
  
     <span data-ttu-id="b6be5-133">Если вы хотите, чтобы Visual Studio автоматически создавала класс прокси веб-службы, просто создайте клиентский проект, а в окне обозреватель решений щелкните правой кнопкой мыши проект, выберите команду **Добавить веб-ссылку**и выберите веб-службу из списка доступных веб-служб. службы (для этого может потребоваться указать адрес конечной точки веб-службы, если веб-служба недоступна в текущем решении или на текущем компьютере). Если посредник веб-службы XML создается самостоятельно (как описано в предыдущем шаге), его можно импортировать в код клиента и воспользоваться методами веб-службы XML.</span><span class="sxs-lookup"><span data-stu-id="b6be5-133">If you want to have Visual Studio generate the Web service proxy class for you, simply create the client project, and, in the Solution Explorer window, right-click the project, click **Add Web Reference**, and select the Web service from the list of available Web services (this may require supplying the address of the Web service endpoint, if the Web service isn't available within the current solution, or on the current computer.) If you create the XML Web service proxy yourself (as described in the previous step), you can import it into your client code and consume the XML Web service methods.</span></span> <span data-ttu-id="b6be5-134">Следующий пример кода импортирует библиотеку прокси-сервера, вызывает **клиентов** для получения списка клиентов, добавляет нового клиента, а затем возвращает **набор данных** с обновлениями **коде**.</span><span class="sxs-lookup"><span data-stu-id="b6be5-134">The following sample code imports the proxy library, calls **GetCustomers** to get a list of customers, adds a new customer, and then returns a **DataSet** with the updates to **UpdateCustomers**.</span></span>  
  
     <span data-ttu-id="b6be5-135">Обратите внимание, что в примере передается **набор данных** , возвращаемый **DataSet. Changed** в **коде** , так как только измененные строки необходимо передать в **коде**.</span><span class="sxs-lookup"><span data-stu-id="b6be5-135">Notice that the example passes the **DataSet** returned by **DataSet.GetChanges** to **UpdateCustomers** because only modified rows need to be passed to **UpdateCustomers**.</span></span> <span data-ttu-id="b6be5-136">**Коде** возвращает разрешенный **набор данных**, который затем можно **объединить** в существующий **набор данных** , чтобы включить в него разрешенные изменения и любые сведения об ошибках строк из обновления.</span><span class="sxs-lookup"><span data-stu-id="b6be5-136">**UpdateCustomers** returns the resolved **DataSet**, which you can then **Merge** into the existing **DataSet** to incorporate the resolved changes and any row error information from the update.</span></span> <span data-ttu-id="b6be5-137">В следующем коде предполагается, что вы использовали Visual Studio для создания веб-ссылки и переименовали веб-ссылку на Дссампле в диалоговом окне " **Добавление веб-ссылки** ".</span><span class="sxs-lookup"><span data-stu-id="b6be5-137">The following code assumes that you have used Visual Studio to create the Web reference, and that you have renamed the Web reference to DsSample in the **Add Web Reference** dialog box.</span></span>  
  
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
  
     <span data-ttu-id="b6be5-138">Если класс посредника создается самостоятельно, следует выполнить следующие дополнительные шаги.</span><span class="sxs-lookup"><span data-stu-id="b6be5-138">If you decide to create the proxy class yourself, you must take the following extra steps.</span></span> <span data-ttu-id="b6be5-139">Чтобы скомпилировать образец, предоставьте созданную библиотеку посредника (sample.dll) и связанные с ней библиотеки .NET.</span><span class="sxs-lookup"><span data-stu-id="b6be5-139">To compile the sample, supply the proxy library that was created (sample.dll) and the related .NET libraries.</span></span> <span data-ttu-id="b6be5-140">Чтобы скомпилировать версию Visual Basic .NET образца, которая хранится в файле client.vb, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b6be5-140">To compile the Visual Basic .NET version of the sample, stored in the file client.vb, issue the following command.</span></span>  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     <span data-ttu-id="b6be5-141">Чтобы скомпилировать версию C# образца, которая хранится в файле client.cs, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="b6be5-141">To compile the C# version of the sample, stored in the file client.cs, issue the following command.</span></span>  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b6be5-142">См. также</span><span class="sxs-lookup"><span data-stu-id="b6be5-142">See also</span></span>

- [<span data-ttu-id="b6be5-143">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b6be5-143">ADO.NET</span></span>](../../../../../docs/framework/data/adonet/index.md)
- [<span data-ttu-id="b6be5-144">Наборы данных, таблицы данных и объекты DataView</span><span class="sxs-lookup"><span data-stu-id="b6be5-144">DataSets, DataTables, and DataViews</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [<span data-ttu-id="b6be5-145">DataTables</span><span class="sxs-lookup"><span data-stu-id="b6be5-145">DataTables</span></span>](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [<span data-ttu-id="b6be5-146">Заполнение набора данных с помощью адаптера данных DataAdapter</span><span class="sxs-lookup"><span data-stu-id="b6be5-146">Populating a DataSet from a DataAdapter</span></span>](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [<span data-ttu-id="b6be5-147">Обновление источников данных с объектами DataAdapter</span><span class="sxs-lookup"><span data-stu-id="b6be5-147">Updating Data Sources with DataAdapters</span></span>](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)
- [<span data-ttu-id="b6be5-148">Параметры DataAdapter</span><span class="sxs-lookup"><span data-stu-id="b6be5-148">DataAdapter Parameters</span></span>](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)
- <span data-ttu-id="b6be5-149">[Средство языка описания веб-служб (WSDL. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="b6be5-149">[Web Services Description Language Tool (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))</span></span>
- [<span data-ttu-id="b6be5-150">Центр разработчиков наборов данных и управляемых поставщиков ADO.NET</span><span class="sxs-lookup"><span data-stu-id="b6be5-150">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
