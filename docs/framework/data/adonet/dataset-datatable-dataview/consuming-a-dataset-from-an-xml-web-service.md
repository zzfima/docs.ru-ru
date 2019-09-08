---
title: Потребление набора данных из веб-службы XML
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
ms.openlocfilehash: 5f28179b43cb0af2d75e9e5b13783bc7287c8886
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784773"
---
# <a name="consuming-a-dataset-from-an-xml-web-service"></a>Потребление набора данных из веб-службы XML
Объект <xref:System.Data.DataSet> не имеет привязки к каким-либо источникам, что позволяет частично упростить передачу данных через Интернет. **Набор данных** является сериализуемым в том, что он может быть указан в качестве входных данных или выходных данных из веб-служб XML без дополнительного программирования, необходимого для потоковой передачи содержимого **набора данных** из веб-службы XML в клиент и обратно. **Набор данных** неявно преобразуется в XML-поток с помощью формата DiffGram, передается по сети, а затем перестраивается из потока XML в качестве **набора данных** на стороне получения. Это обеспечивает очень простой и гибкий метод передачи и получения реляционных данных с помощью веб-служб XML. Дополнительные сведения о формате DiffGram см. в разделе [дельтами](diffgrams.md).  
  
 В следующем примере показано, как создать веб-службу XML и клиент, которые используют **набор данных** для передачи реляционных данных (включая измененные данные) и разрешения всех обновлений обратно в исходный источник данных.  
  
> [!NOTE]
> При создании веб-службы XML следует всегда учитывать возможные вопросы безопасности. Сведения о защите веб-службы XML см. в разделе [Защита веб-служб XML, созданных с помощью ASP.NET](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/w67h0dw7(v=vs.100)).  
  
### <a name="to-create-an-xml-web-service-that-returns-and-consumes-a-dataset"></a>Создание веб-службы XML, которая возвращает и потребляет объект DataSet  
  
1. Создайте веб-службу XML.  
  
     В этом примере создается веб-служба XML, которая возвращает данные, в данном случае список клиентов из базы данных **Northwind** и получает **набор данных** с обновлениями данных, которые веб-служба XML разрешается обратно в исходный источник данных.  
  
     Веб-служба XML предоставляет два следующих метода: **Клиенты**, чтобы получить список клиентов и **коде**для разрешения обновлений обратно в источник данных. Веб-служба XML хранится в файле на веб-сервере DataSetSample.asmx. В следующем коде описано содержимое файла DataSetSample.asmx.  
  
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
  
     В типичном сценарии метод **коде** будет написан для перехвата нарушений оптимистической блокировки. Для простоты в данном примере это опущено. Дополнительные сведения о оптимистичном параллелизме см. в разделе [Оптимистическая блокировка](../optimistic-concurrency.md).  
  
2. Создайте посредник веб-службы XML.  
  
     Клиентам веб-службы XML необходим посредник SOAP, чтобы использовать предоставленные методы. Этот посредник может быть создан с помощью среды Visual Studio. Если задать веб-ссылку на существующую веб-службу из Visual Studio, все действия, описанные в этом шаге, будут производиться незаметно. Если требуется создать класс посредника самостоятельно, читайте этот раздел далее. Однако в большинстве случаев достаточно создать класс посредника для клиентского приложения с помощью Visual Studio.  
  
     Посредник можно создать с помощью средства WSDL. Например, если веб-служба XML предоставляется по URL-адресу `http://myserver/data/DataSetSample.asmx`, выполните следующую команду, чтобы создать Visual Basic прокси .NET с пространством имен **дссампле** и сохранить его в файле Sample. vb.  
  
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
  
     Если вы хотите, чтобы Visual Studio автоматически создавала класс прокси веб-службы, просто создайте клиентский проект, а в окне обозреватель решений щелкните правой кнопкой мыши проект, выберите команду **Добавить веб-ссылку**и выберите веб-службу из списка доступных веб-служб. службы (для этого может потребоваться указать адрес конечной точки веб-службы, если веб-служба недоступна в текущем решении или на текущем компьютере). Если посредник веб-службы XML создается самостоятельно (как описано в предыдущем шаге), его можно импортировать в код клиента и воспользоваться методами веб-службы XML. Следующий пример кода импортирует библиотеку прокси-сервера, вызывает **клиентов** для получения списка клиентов, добавляет нового клиента, а затем возвращает **набор данных** с обновлениями **коде**.  
  
     Обратите внимание, что в примере передается **набор данных** , возвращаемый **DataSet. Changed** в **коде** , так как только измененные строки необходимо передать в **коде**. **Коде** возвращает разрешенный **набор данных**, который затем можно **объединить** в существующий **набор данных** , чтобы включить в него разрешенные изменения и любые сведения об ошибках строк из обновления. В следующем коде предполагается, что вы использовали Visual Studio для создания веб-ссылки и переименовали веб-ссылку на Дссампле в диалоговом окне " **Добавление веб-ссылки** ".  
  
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

- [ADO.NET](../index.md)
- [Наборы данных, таблицы данных и объекты DataView](index.md)
- [DataTables](datatables.md)
- [Заполнение набора данных с помощью адаптера данных DataAdapter](../populating-a-dataset-from-a-dataadapter.md)
- [Обновление источников данных с объектами DataAdapter](../updating-data-sources-with-dataadapters.md)
- [Параметры DataAdapter](../dataadapter-parameters.md)
- [Средство языка описания веб-служб (WSDL. exe)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7h3ystb6(v=vs.100))
- [Общие сведения об ADO.NET](../ado-net-overview.md)
