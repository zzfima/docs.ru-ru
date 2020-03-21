---
title: Получение класса DbProviderFactory
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a16e4a4d-6a5b-45db-8635-19570e4572ae
ms.openlocfilehash: 0e2efd593019199ff641610b8602825cc60d4661
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149470"
---
# <a name="obtaining-a-dbproviderfactory"></a>Получение класса DbProviderFactory
Процесс получения <xref:System.Data.Common.DbProviderFactory> состоит из передачи сведений о поставщике данных классу <xref:System.Data.Common.DbProviderFactories>. На основе этих сведений метод <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> создает строго типизированную фабрику поставщика. Например, чтобы создать фабрику <xref:System.Data.SqlClient.SqlClientFactory>, можно передать методу `GetFactory` строку с именем поставщика, указанным в формате «System.Data.SqlClient». Другая перегрузка метода `GetFactory` принимает <xref:System.Data.DataRow>. После создания фабрики поставщика можно использовать ее методы для создания дополнительных объектов. К методам фабрики `SqlClientFactory` относятся <xref:System.Data.SqlClient.SqlClientFactory.CreateConnection%2A>, <xref:System.Data.SqlClient.SqlClientFactory.CreateCommand%2A> и <xref:System.Data.SqlClient.SqlClientFactory.CreateDataAdapter%2A>.  
  
> [!NOTE]
> Классы .NET Framework <xref:System.Data.OracleClient.OracleClientFactory>, <xref:System.Data.Odbc.OdbcFactory> и <xref:System.Data.OleDb.OleDbFactory> также предоставляют похожие возможности.  
  
## <a name="registering-dbproviderfactories"></a>Регистрация фабрик DbProviderFactory  
 Каждый поставщик данных .NET Framework, поддерживающий заводской класс, регистрирует информацию о конфигурации в разделе **DbProviderFactories** файла **machine.config** на локальном компьютере. В следующем фрагменте файла конфигурации показан синтаксис и формат для <xref:System.Data.SqlClient>.  
  
```xml  
<system.data>  
  <DbProviderFactories>  
    <add name="SqlClient Data Provider"  
     invariant="System.Data.SqlClient"
     description=".Net Framework Data Provider for SqlServer"
     type="System.Data.SqlClient.SqlClientFactory, System.Data,
     Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089"  
    />  
  </DbProviderFactories>  
</system.data>  
```  
  
 **Инвариантный** атрибут определяет основного поставщика данных. Этот трехкомпонентный синтаксис имени также применяется при создании новой фабрики и для определения поставщика в файле конфигурации, чтобы имя поставщика вместе со связанной с ним строкой соединения можно было получать во время выполнения.  
  
## <a name="retrieving-provider-information"></a>Извлечения сведений поставщика  
 Сведения обо всех поставщиках, установленных на локальном компьютере, можно получить с помощью метода <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A>. Он возвращает <xref:System.Data.DataTable> имя **DbProviderFactories,** содержащее столбцы, описанные в следующей таблице.  
  
|Порядковый номер столбца|Имя столбца|Пример выходных данных|Описание|  
|--------------------|-----------------|--------------------|-----------------|  
|0|**Название**|Поставщик данных SqlClient|Понятное имя поставщика данных.|  
|1|**Описание**|Поставщик данных .NET Framework для SqlServer|Понятное описание поставщика данных.|  
|2|**InvariantName**|System.Data.SqlClient|Имя, которое можно использовать программно, чтобы ссылаться на поставщик данных.|  
|3|**AssemblyQualifiedName**|System.Data.SqlClient.SqlClientFactory, System.Data, Version=2.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089|Полное имя фабричного класса, которое содержит достаточно данных для создания экземпляров объектов.|  
  
 Эту таблицу `DataTable` можно применять, чтобы дать пользователям возможность выбирать <xref:System.Data.DataRow> во время выполнения. Выбранная строка `DataRow` затем может передаваться методу <xref:System.Data.Common.DbProviderFactories.GetFactory%2A> для создания строго типизированной фабрики <xref:System.Data.Common.DbProviderFactory>. Выбранная строка <xref:System.Data.DataRow> затем может передаваться методу `GetFactory` для создания нужного объекта `DbProviderFactory`.  
  
## <a name="listing-the-installed-provider-factory-classes"></a>Перечисление классов установленной фабрики поставщика  
 В этом примере демонстрируется, как использовать метод <xref:System.Data.Common.DbProviderFactories.GetFactoryClasses%2A> для возвращения таблицы <xref:System.Data.DataTable> со сведениями об установленных поставщиках. В коде выполняется просмотр каждой строки в таблице `DataTable` с выводом сведений по каждому поставщику в консольном окне.  
  
 [!code-csharp[DataWorks DbProviderFactories#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories/VB/source.vb#1)]  
  
## <a name="using-application-configuration-files-to-store-factory-information"></a>Использование файлов конфигурации приложений для хранения сведений о фабрике  
 Шаблон проектирования, используемый для работы с фабриками, предполагает хранение информации о поставщике и строках соединения в файле конфигурации приложения, таких как **app.config** для приложения Windows и **web.config** для ASP.NET приложения.  
  
 В следующем фрагменте файла конфигурации демонстрируется, как сохранять две именованные строки соединения «NorthwindSQL» для соединения с базой данных Northwind в SQL Server и «NorthwindAccess» для соединения с базой данных Northwind в Access/Jet. Имя **инварианта** используется для атрибута **providerName.**  
  
```xml  
<configuration>  
  <connectionStrings>  
    <clear/>  
    <add name="NorthwindSQL"
     providerName="System.Data.SqlClient"
     connectionString=  
     "Data Source=MSSQL1;Initial Catalog=Northwind;Integrated Security=true"  
    />  
  
    <add name="NorthwindAccess"
     providerName="System.Data.OleDb"
     connectionString=  
     "Provider=Microsoft.Jet.OLEDB.4.0;Data Source=C:\Data\Northwind.mdb;"  
    />  
  </connectionStrings>  
</configuration>  
```  
  
### <a name="retrieving-a-connection-string-by-provider-name"></a>Извлечение строки соединения по имени поставщика  
 Чтобы создать фабрику поставщика, необходимо предоставить строку соединения, а также имя поставщика. Этот пример показывает, как извлечь строку соединения из файла конфигурации приложения, передавая имя поставщика в инвариантном формате "*System.Data.ProviderName*". В коде выполняется просмотр элементов коллекции <xref:System.Configuration.ConnectionStringSettingsCollection>. В случае успеха возвращается <xref:System.Configuration.ConnectionStringSettings.ProviderName%2A>; в противном случае - `null` (`Nothing` в Visual Basic). При наличии нескольких записей для поставщика возвращается первая найденная. Для получения дополнительной информации и примеров извлечения строк соединения из файлов конфигурации [см.](connection-strings-and-configuration-files.md)  
  
> [!NOTE]
> Для выполнения этого кода необходима ссылка на файл `System.Configuration.dll`.  
  
 [!code-csharp[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/CS/source.cs#1)]
 [!code-vb[DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks ConnectionStringSettings.RetrieveFromConfigByProvider/VB/source.vb#1)]  
  
## <a name="creating-the-dbproviderfactory-and-dbconnection"></a>Создание DbProviderFactory и DbConnection  
 Этот пример демонстрирует, как <xref:System.Data.Common.DbProviderFactory> <xref:System.Data.Common.DbConnection> создать объект, передавая ему имя поставщика в формате "*System.Data.ProviderName*" и строку соединения. В случае успеха возвращается объект `DbConnection`; в случае любой ошибки - `null` (`Nothing` в Visual Basic).  
  
 Этот код получает `DbProviderFactory` путем вызова <xref:System.Data.Common.DbProviderFactories.GetFactory%2A>. Затем метод <xref:System.Data.Common.DbProviderFactory.CreateConnection%2A> создает объект <xref:System.Data.Common.DbConnection>, а свойству <xref:System.Data.Common.DbConnection.ConnectionString%2A> присваивается значение строки соединения.  
  
 [!code-csharp[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/CS/source.cs#1)]
 [!code-vb[DataWorks DbProviderFactories.GetFactory#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DbProviderFactories.GetFactory/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также раздел

- [DbProviderFactories](dbproviderfactories.md)
- [Строки подключения](connection-strings.md)
- [Использование классов конфигурации](https://docs.microsoft.com/previous-versions/aspnet/ms228063(v=vs.100))
- [Общие сведения об ADO.NET](ado-net-overview.md)
