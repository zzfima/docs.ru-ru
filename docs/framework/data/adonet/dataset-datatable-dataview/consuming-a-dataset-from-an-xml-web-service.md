---
title: "Использование данных из DataSet в веб-службе XML | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9edd6b71-0fa5-4649-ae1d-ac1c12541019
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 4
---
# Использование данных из DataSet в веб-службе XML
Объект <xref:System.Data.DataSet> не имеет привязки к каким\-либо источникам, что позволяет частично упростить передачу данных через Интернет.  Объект **DataSet** является сериализуемым, то есть его можно задать в качестве ввода или вывода для веб\-служб XML, при этом для передачи содержимого объекта **DataSet** из веб\-службы XML клиенту и обратно не требуется дополнительное программирование.  Объект **DataSet** неявно преобразуется в поток XML с помощью формата DiffGram, отправляется по сети, а затем восстанавливается из потока XML в объект **DataSet** на принимающей стороне.  Это обеспечивает очень простой и гибкий метод передачи и получения реляционных данных с помощью веб\-служб XML.  Дополнительные сведения о формате DiffGram см. в разделе [Объекты DiffGram](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/diffgrams.md).  
  
 В следующем примере показывается, как создать веб\-службу XML и клиент, в которых для передачи реляционных данных \(в том числе измененных данных\) и внесения всех обновлений в источник данных используется объект **DataSet**.  
  
> [!NOTE]
>  При создании веб\-службы XML следует всегда учитывать возможные вопросы безопасности.  Дополнительные сведения об обеспечении безопасности веб\-служб XML см. в разделе [Securing XML Web Services Created Using ASP.NET](http://msdn.microsoft.com/ru-ru/354b2ab1-2782-4542-b32a-dc560178b90c).  
  
### Создание веб\-службы XML, которая возвращает и потребляет объект DataSet  
  
1.  Создайте веб\-службу XML.  
  
     В этом примере создается веб\-служба XML, возвращающая данные \(здесь это список клиентов из базы данных **Northwind**\), и получает объект **DataSet** с обновлениями данных, которые веб\-служба XML передает назад в исходный источник данных.  
  
     Веб\-служба XML обеспечивает доступ к двум следующим методам: **GetCustomers** для возврата списка клиентов и **UpdateCustomers** для передачи обновлений обратно источнику данных.  Веб\-служба XML хранится в файле на веб\-сервере DataSetSample.asmx.  В следующем коде описано содержимое файла DataSetSample.asmx.  
  
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
  
     Обычно метод **UpdateCustomers** создается для обнаружения нарушений оптимистичного параллелизма.  Для простоты в данном примере это опущено.  Дополнительные сведения об оптимистическом параллелизме см. в разделе [Оптимистическая блокировка](../../../../../docs/framework/data/adonet/optimistic-concurrency.md).  
  
2.  Создайте посредник веб\-службы XML.  
  
     Клиентам веб\-службы XML необходим посредник SOAP, чтобы использовать предоставленные методы.  Этот посредник может быть создан с помощью среды Visual Studio.  Если задать веб\-ссылку на существующую веб\-службу из Visual Studio, все действия, описанные в этом шаге, будут производиться незаметно.  Если требуется создать класс посредника самостоятельно, читайте этот раздел далее.  Однако в большинстве случаев достаточно создать класс посредника для клиентского приложения с помощью Visual Studio.  
  
     Посредник можно создать с помощью средства WSDL.  Например, если URL\-адрес веб\-службы XML \- «http:\/\/myserver\/data\/DataSetSample.asmx», выполните команду, как в следующем примере, чтобы создать посредник Visual Basic .NET с пространством имен **WebData.DSSample** и сохранить его в файле sample.vb.  
  
    ```  
    wsdl /l:VB /out:sample.vb http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     Чтобы создать посредник C\# в файле sample.cs, выполните следующую команду.  
  
    ```  
    wsdl /l:CS /out:sample.cs http://myserver/data/DataSetSample.asmx /n:WebData.DSSample  
    ```  
  
     После создания посредник можно будет скомпилировать как библиотеку и импортировать в клиент веб\-службы XML.  Чтобы скомпилировать код посредника Visual Basic .NET, хранящийся в файле sample.vb, в файл sample.dll, выполните следующую команду.  
  
    ```  
    vbc /t:library /out:sample.dll sample.vb /r:System.dll /r:System.Web.Services.dll /r:System.Data.dll /r:System.Xml.dll  
    ```  
  
     Чтобы скомпилировать код посредника C\#, хранящийся в файле sample.cs, в файл sample.dll, выполните следующую команду.  
  
    ```  
    csc /t:library /out:sample.dll sample.cs /r:System.dll /r:System.Web.Services.dll /r:System.Data.dll /r:System.Xml.dll  
    ```  
  
3.  Создайте клиент веб\-службы XML.  
  
     Если требуется сформировать класс посредника веб\-службы с помощью Visual Studio, просто создайте проект клиента и в окне обозревателя решений щелкните проект правой кнопкой мыши, нажмите кнопку **Добавить веб\-ссылку** и выберите веб\-службу из списка имеющихся веб\-служб \(при этом может потребоваться указать адрес конечной точки веб\-службы, если данной веб\-службы нет в текущем решении или на используемом компьютере\). Если посредник веб\-службы XML создается самостоятельно \(как описано в предыдущем шаге\), его можно импортировать в код клиента и воспользоваться методами веб\-службы XML.  В следующем образце кода импортируется библиотека посредника, вызывается метод **GetCustomers** для возврата списка клиентов, добавляется новый клиент и возвращается объект **DataSet** с обновлениями для метода **UpdateCustomers**.  
  
     Обратите внимание, что в коде этого примера объект **DataSet**, возвращенный методом **DataSet.GetChanges**, передается методу **UpdateCustomers**, так как в метод **UpdateCustomers** необходимо передавать только измененные строки.  Метод **UpdateCustomers** возвращает обновленный объект **DataSet**, который затем можно будет **слить** с существующим объектом **DataSet**, чтобы вставить внесенные изменения, а также все сведения об ошибках строк из обновления.  В следующем коде предполагается, что для создания веб\-ссылки использовалась среда Visual Studio, а также что в диалоговом окне **Добавить веб\-ссылку** имя веб\-ссылки было изменено на DsSample.  
  
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
  
     Если класс посредника создается самостоятельно, следует выполнить следующие дополнительные шаги.  Чтобы скомпилировать образец, предоставьте созданную библиотеку посредника \(sample.dll\) и связанные с ней библиотеки .NET.  Чтобы скомпилировать версию Visual Basic .NET образца, которая хранится в файле client.vb, выполните следующую команду.  
  
    ```  
    vbc client.vb /r:sample.dll /r:System.dll /r:System.Data.dll /r:System.Xml.dll /r:System.Web.Services.dll  
    ```  
  
     Чтобы скомпилировать версию C\# образца, которая хранится в файле client.cs, выполните следующую команду.  
  
    ```  
    csc client.cs /r:sample.dll /r:System.dll /r:System.Data.dll /r:System.Xml.dll /r:System.Web.Services.dll  
    ```  
  
## См. также  
 [ADO.NET](../../../../../docs/framework/data/adonet/index.md)   
 [Объекты DataSet, DataTable и DataView](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/index.md)   
 [DataTables](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatables.md)   
 [Заполнение набора данных с помощью адаптера данных DataAdapter](../../../../../docs/framework/data/adonet/populating-a-dataset-from-a-dataadapter.md)   
 [Обновление источников данных с помощью объектов DataAdapter](../../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md)   
 [Параметры DataAdapter](../../../../../docs/framework/data/adonet/dataadapter-parameters.md)   
 [Web Services Description Language Tool \(Wsdl.exe\)](http://msdn.microsoft.com/ru-ru/b9210348-8bc2-4367-8c91-d1a04b403e88)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)