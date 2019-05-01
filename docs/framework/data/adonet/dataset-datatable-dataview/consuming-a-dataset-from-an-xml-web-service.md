---
title: Потребление набора данных из веб-службы XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: 7b284a8f085ab7e93651c829ac16e47fb63a8b51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62034480"
---
# <a name="consuming-a-dataset-from-an-xml-web-service"></a>Потребление набора данных из веб-службы XML
Объект <xref:System.Data.DataSet> не имеет привязки к каким-либо источникам, что позволяет частично упростить передачу данных через Интернет. **Набора данных** является «сериализуемые», в том, что он может быть указан в качестве входных данных или выходные данные из XML-веб-служб без дополнительного кода, необходимых для потоковой передачи содержимого **набора данных** из XML-веб-службы к клиенту и обратно. **Набора данных** неявно преобразуется в поток XML с использованием формата DiffGram, отправляемых по сети и затем восстанавливается из потока XML в виде **набора данных** на принимающей стороне. Это обеспечивает очень простой и гибкий метод передачи и получения реляционных данных с помощью веб-служб XML. Дополнительные сведения о формате DiffGram см. в разделе [дельт](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).  
  
 Приведенный ниже показано, как создать XML-веб-службы и клиента, который использовать **набора данных** для передачи реляционных данных (в том числе измененных данных) и внесения всех обновлений к исходному источнику данных.  
  
> [!NOTE]
>  При создании веб-службы XML следует всегда учитывать возможные вопросы безопасности. Сведения о защите веб-службы XML, см. в разделе [защита XML-веб-службы создан с помощью ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).  
  
### <a name="to-create-an-xml-web-service-that-returns-and-consumes-a-dataset"></a>Создание веб-службы XML, которая возвращает и потребляет объект DataSet  
  
1. Создайте веб-службу XML.  
  
     В примере создается XML-веб-службы, возвращающий данные, в нашем примере список клиентов из **Northwind** базы данных, а также получает **набора данных** с обновления данных, который веб-службу XML Разрешает обратно к исходному источнику данных.  
  
     Веб-служба XML предоставляет два следующих метода: **GetCustomers**, который возвращает список клиентов, и **UpdateCustomers**, чтобы разрешить обновления в источнике данных. Веб-служба XML хранится в файле на веб-сервере DataSetSample.asmx. В следующем коде описано содержимое файла DataSetSample.asmx.  
  
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
  
     В типичном сценарии **UpdateCustomers** создается метод для обнаружения нарушений оптимистичного параллелизма. Для простоты в данном примере это опущено. Дополнительные сведения об оптимистическом параллелизме см. в разделе [оптимистичного параллелизма](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).  
  
2. Создайте посредник веб-службы XML.  
  
     Клиентам веб-службы XML необходим посредник SOAP, чтобы использовать предоставленные методы. Этот посредник может быть создан с помощью среды Visual Studio. Если задать веб-ссылку на существующую веб-службу из Visual Studio, все действия, описанные в этом шаге, будут производиться незаметно. Если требуется создать класс посредника самостоятельно, читайте этот раздел далее. Однако в большинстве случаев достаточно создать класс посредника для клиентского приложения с помощью Visual Studio.  
  
     Посредник можно создать с помощью средства WSDL. Например, если XML-веб-служба доступна по URL-адрес `http://myserver/data/DataSetSample.asmx`, выполните команду, подобную следующей, чтобы создать посредник Visual Basic .NET с пространством имен **WebData.DSSample** и сохранить ее в файле sample.vb.  
  
    ```console
    wsdl /l:VB -out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     Чтобы создать посредник C# в файле sample.cs, выполните следующую команду.  
  
    ```console
    wsdl -l:CS -out:sample.cs http://myserver/data/DataSetSample.asmx -n:WebData.DSSample  
    ```  
  
     После создания посредник можно будет скомпилировать как библиотеку и импортировать в клиент веб-службы XML. Чтобы скомпилировать код посредника Visual Basic .NET, хранящийся в файле sample.vb, в файл sample.dll, выполните следующую команду.  
  
    ```console  
    vbc -t:library -out:sample.dll sample.vb -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
     Чтобы скомпилировать код посредника C#, хранящийся в файле sample.cs, в файл sample.dll, выполните следующую команду.  
  
    ```console
    csc -t:library -out:sample.dll sample.cs -r:System.dll -r:System.Web.Services.dll -r:System.Data.dll -r:System.Xml.dll  
    ```  
  
3. Создайте клиент веб-службы XML.  
  
     Если вы хотите создать класс прокси веб-службы для вас среда Visual Studio, просто создать клиентский проект и, в окне обозревателя решений щелкните правой кнопкой мыши проект, нажмите кнопку **Add Web Reference**и выберите веб-службу из Список доступных веб-служб (может потребоваться предоставляет адрес конечной точки веб-службы, если веб-служба недоступна в текущем решении или на текущем компьютере.) Если посредник веб-службы XML создается самостоятельно (как описано в предыдущем шаге), его можно импортировать в код клиента и воспользоваться методами веб-службы XML. В следующем образце кода импортируется библиотека посредника, вызовы **GetCustomers** для получения списка заказчиков, добавляется новый клиент, а затем возвращает **набора данных** с обновлениями для **UpdateCustomers** .  
  
     Обратите внимание, что в примере передается **набора данных** возвращаемые **DataSet.GetChanges** для **UpdateCustomers** так, как только измененные строки должны быть переданы  **UpdateCustomers**. **UpdateCustomers** возвращает обновленный **набора данных**, которую можно затем **слияния** в существующую **набора данных** включать внесенные изменения и любой сведения об ошибках строк из обновления. В следующем коде предполагается, что вы использовали Visual Studio для создания веб-ссылки и переименовании веб-ссылки было изменено на DsSample в **Add Web Reference** диалоговое окно.  
  
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
  
     Если класс посредника создается самостоятельно, следует выполнить следующие дополнительные шаги. Чтобы скомпилировать образец, предоставьте созданную библиотеку посредника (sample.dll) и связанные с ней библиотеки .NET. Чтобы скомпилировать версию Visual Basic .NET образца, которая хранится в файле client.vb, выполните следующую команду.  
  
    ```console
    vbc client.vb -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
     Чтобы скомпилировать версию C# образца, которая хранится в файле client.cs, выполните следующую команду.  
  
    ```console
    csc client.cs -r:sample.dll -r:System.dll -r:System.Data.dll -r:System.Xml.dll -r:System.Web.Services.dll  
    ```  
  
## <a name="see-also"></a>См. также

- [ADO.NET](../../../../../docs/framework/data/adonet/index.md)
- [Наборы данных, таблицы данных и объекты DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)
- [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)
- [Заполнение набора данных с помощью адаптера данных DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)
- [Обновление источников данных с объектами DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)
- [Параметры DataAdapter](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)
- [Инструмент языка описания веб-служб (Wsdl.exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))
- [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](https://go.microsoft.com/fwlink/?LinkId=217917)
