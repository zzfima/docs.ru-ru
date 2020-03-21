---
title: Синтаксис строки подключения
ms.date: 05/22/2018
ms.assetid: 0977aeee-04d1-4cce-bbed-750c77fce06e
ms.openlocfilehash: 3df97419391fe17ef77a3b8f24c4f0689a04602f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79151654"
---
# <a name="connection-string-syntax"></a>Синтаксис строки подключения
Каждый поставщик данных платформы .NET Framework имеет объект `Connection`, наследующий из <xref:System.Data.Common.DbConnection>, а также из свойства <xref:System.Data.Common.DbConnection.ConnectionString%2A>, зависящего от поставщика. Конкретный синтаксис строки подключения для каждого поставщика приведен в его свойстве `ConnectionString`. В следующей таблице представлен список четырех поставщиков данных, поставляемых в составе платформы .NET Framework.  
  
|Поставщик данных .NET Framework|Описание|  
|----------------------------------|-----------------|  
|<xref:System.Data.SqlClient>|Предоставляет доступ к данным для Microsoft SQL Server. Дополнительные сведения о синтаксисе строки подключения см. в разделе <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.|  
|<xref:System.Data.OleDb>|Предоставляет доступ к данным источников данных OLE DB. Дополнительные сведения о синтаксисе строки подключения см. в разделе <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A>.|  
|<xref:System.Data.Odbc>|Предоставляет доступ к данным источников данных ODBC. Дополнительные сведения о синтаксисе строки подключения см. в разделе <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A>.|  
|<xref:System.Data.OracleClient>|Предоставляет доступ к данным Oracle версии 8.1.7 или старше. Дополнительные сведения о синтаксисе строки подключения см. в разделе <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.|  
  
## <a name="connection-string-builders"></a>Построители строк подключения  
 В ADO.NET 2.0 появились указанные ниже построители строк соединения для поставщиков данных .NET Framework.  
  
- <xref:System.Data.SqlClient.SqlConnectionStringBuilder>  
  
- <xref:System.Data.OleDb.OleDbConnectionStringBuilder>  
  
- <xref:System.Data.Odbc.OdbcConnectionStringBuilder>  
  
- <xref:System.Data.OracleClient.OracleConnectionStringBuilder>  
  
 Построители строк соединения позволяют создавать во время выполнения синтаксически правильные строки соединения, и поэтому в коде не требуется вручную объединять значения строк соединения. Дополнительные сведения см. в статье [Connection String Builders](connection-string-builders.md) (Построители строк подключения).  

## <a name="windows-authentication"></a>Проверка подлинности Windows  
 Мы рекомендуем использовать Windows Authentication (иногда называемую *интегрированной безопасностью)* для подключения к источникам данных, которые ее поддерживают. Синтаксис строки подключения зависит от поставщика. В следующей таблице показан синтаксис проверки подлинности Windows, который используется с поставщиками данных платформы .NET Framework.  
  
|Поставщик|Синтаксис|  
|--------------|------------|  
|`SqlClient`|`Integrated Security=true;`<br /><br /> `-- or --`<br /><br /> `Integrated Security=SSPI;`|  
|`OleDb`|`Integrated Security=SSPI;`|  
|`Odbc`|`Trusted_Connection=yes;`|  
|`OracleClient`|`Integrated Security=yes;`|  
  
> [!NOTE]
> Значение `Integrated Security=true` вызывает исключение при работе с поставщиком `OleDb`.  
  
## <a name="sqlclient-connection-strings"></a>Строки подключения SqlClient  
Синтаксис для строки подключения <xref:System.Data.SqlClient.SqlConnection> документирован в свойстве <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType>. Свойство <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> используется для возврата или задания строки подключения для базы данных SQL Server. Если необходимо подключиться к более ранней версии SQL Server, следует использовать поставщик данных .NET Framework для OleDb (<xref:System.Data.OleDb>). Наиболее распространенные ключевые слова строк соединения также соответствуют свойствам <xref:System.Data.SqlClient.SqlConnectionStringBuilder>.  

> [!IMPORTANT]
> Настройка по `Persist Security Info` умолчанию `false`для ключевого слова. Значение `true` или `yes` позволяет получить из строки соединения конфиденциальные данные (в том числе идентификатор пользователя и пароль) после открытия соединения. Следите `Persist Security Info` `false` за тем, чтобы недоверчивый источник не был доступом к конфиденциальной информации строки соединения.  

### <a name="windows-authentication-with-sqlclient"></a>Аутентификация Windows с помощью SqlClient
 Каждая из следующих форм синтаксиса использует windows Authentication для подключения к базе данных **AdventureWorks** на локальном сервере.  
  
```csharp  
"Persist Security Info=False;Integrated Security=true;  
    Initial Catalog=AdventureWorks;Server=MSSQL1"  
"Persist Security Info=False;Integrated Security=SSPI;  
    database=AdventureWorks;server=(local)"  
"Persist Security Info=False;Trusted_Connection=True;  
    database=AdventureWorks;server=(local)"  
```  
  
### <a name="sql-server-authentication-with-sqlclient"></a>Проверка подлинности сервера СЗЛ с помощью SqlClient
 Для соединения с SQL Server предпочтительно использовать проверку подлинности Windows. Однако если требуется проверка подлинности SQL Server, то имя пользователя и пароль указываются с помощью приведенного ниже синтаксиса. В этом примере символы звездочки представляют допустимое имя пользователя и пароль.  
  
```csharp  
"Persist Security Info=False;User ID=*****;Password=*****;Initial Catalog=AdventureWorks;Server=MySqlServer"  
```  

При подключении к базе данных Azure S'L или к хранилище `user@servername`данных Azure S'L и обеспечить логин в формате убедитесь, что `servername` значение входа соответствует предоставленному `Server=`значению.

> [!NOTE]
> Проверка подлинности Windows имеет приоритет над именами входа SQL Server. Если указать значение Integrated Security=true, а также ввести имя пользователя и пароль, то имя пользователя и пароль не будут учитываться и будет применяться проверка подлинности Windows.  

### <a name="connect-to-a-named-instance-of-sql-server"></a>Подключение к названному экземпляру сервера S'L
Для подключения к названному экземпляру сервера S'L, используйте синтаксис *имени имени сервера.*  
  
```csharp  
"Data Source=MySqlServer\MSSQL1;"  
```  

Кроме того, в свойстве <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A> объекта `SqlConnectionStringBuilder` можно задать имя экземпляра при построении строки подключения. Свойство <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> объекта <xref:System.Data.SqlClient.SqlConnection> доступно только для чтения.  
  
### <a name="type-system-version-changes"></a>Изменения версий системы типов  
 Ключевое `Type System Version` слово <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> в представлении клиентской стороны типов серверов S'L. Дополнительные сведения о ключевом слове <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A?displayProperty=nameWithType> см. в разделе `Type System Version`.  
  
## <a name="connecting-and-attaching-to-sql-server-express-user-instances"></a>Подключение и присоединение к пользовательским экземплярам SQL Server Express  
 Пользовательские экземпляры являются одной из возможностей SQL Server Express. Они дают пользователям под учетной записью с минимальными правами возможность присоединить и запустить базу данных SQL Server без прав администратора. Пользовательский экземпляр выполняется с учетными данными пользователя Windows, а не службы.  
  
 Для получения более подробной информации [SQL Server Express User Instances](./sql/sql-server-express-user-instances.md)о работе с пользовательскими экземплярами, см.  
  
## <a name="using-trustservercertificate"></a>Использование ключевого слова TrustServerCertificate  
 Ключевое `TrustServerCertificate` слово действителен только при подключении к экземпляру сервера СЗЛ с действительным сертификатом. Если ключевому слову `TrustServerCertificate` присвоено значение `true`, то транспортный уровень будет использовать протокол SSL для шифрования канала и не пойдет по цепочке сертификатов для проверки доверия.  
  
```csharp  
"TrustServerCertificate=true;"
```  
  
> [!NOTE]
> Если ключевому слову `TrustServerCertificate` присвоено значение `true` и включено шифрование, то будет использоваться уровень шифрования, заданный на сервере, даже если в строке подключения `Encrypt` задано значение `false`. В противном случае соединение не будет установлено.  
  
### <a name="enabling-encryption"></a>Включение шифрования  
 Для включения шифрования, если сертификат не был представлен на сервере, в настройке сервера должен быть установлен **опорный комплекс Протокола Сил** и параметры **сертификата Trust Server.** В этом случае шифрование будет использовать самозаверяющий сертификат сервера, не проверяя наличия подтверждаемого сертификата сервера.  
  
 Настройки приложения не могут снизить установленный на SQL Server уровень безопасности, но при необходимости могут повысить его. Приложение может запросить шифрование, установив `TrustServerCertificate` `Encrypt` и ключевые слова, `true`гарантируя, что шифрование происходит даже тогда, когда сертификат сервера не был подготовлен и **шифрование протокола Force** не было настроено для клиента. Но если на клиенте не установлен параметр `TrustServerCertificate`, то сертификат сервера, тем не менее, потребуется.  
  
 В следующей таблице перечислены все случаи.  
  
|Параметр «Принудительное шифрование протокола» на клиенте|Параметр «Доверять сертификату сервера» на клиенте|Строка или атрибут «Шифровать/Использовать шифрование для подключения к данным»|Строка подключения или атрибут «Доверять сертификату сервера»|Результат|  
|----------------------------------------------|---------------------------------------------|-------------------------------------------------------------------|-----------------------------------------------------------|------------|  
|нет|Недоступно|Нет (по умолчанию)|Не учитывается|Шифрование отсутствует.|  
|нет|Недоступно|Да|Нет (по умолчанию)|Шифрование применяется только при наличии подтверждаемого сертификата сервера, в противном случае попытка соединения завершается неудачно.|  
|нет|Недоступно|Да|Да|Шифрование производится всегда, однако при этом может использоваться самозаверяющий сертификат сервера.|  
|Да|нет|Не учитывается|Не учитывается|Шифрование происходит только при наличии проверяемого серверного сертификата; в противном случае попытка подключения завершается неудачей.|  
|Да|Да|Нет (по умолчанию)|Не учитывается|Шифрование производится всегда, однако при этом может использоваться самозаверяющий сертификат сервера.|  
|Да|Да|Да|Нет (по умолчанию)|Шифрование происходит только при наличии проверяемого серверного сертификата; в противном случае попытка подключения завершается неудачей.|  
|Да|Да|Да|Да|Шифрование производится всегда, однако при этом может использоваться самозаверяющий сертификат сервера.|  
  
 Дополнительные сведения см. в статье [Использование шифрования без проверки](/sql/relational-databases/native-client/features/using-encryption-without-validation).
  
## <a name="oledb-connection-strings"></a>Строки соединения OleDb  
 Свойство <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> класса <xref:System.Data.OleDb.OleDbConnection> позволяет получить или задать строку подключения для источника данных OLE DB (например, Microsoft Access). Строку подключения `OleDb` также можно создать во время выполнения с помощью класса <xref:System.Data.OleDb.OleDbConnectionStringBuilder>.  
  
### <a name="oledb-connection-string-syntax"></a>Синтаксис строки соединения OleDb  
 В строке соединения <xref:System.Data.OleDb.OleDbConnection> необходимо указать имя поставщика. Следующие строки подключения подключают к базе данных Microsoft Access, использующей поставщик Jet. Обратите внимание, что ключевые слова `User ID` и `Password` необязательны, если база данных не защищена (по умолчанию).  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0; Data Source=d:\Northwind.mdb;User ID=Admin;Password=;
```  
  
 Если база данных Jet защищена на уровне пользователя, необходимо указать местоположение файла сведений рабочей группы (MDW-файла). Файл сведений рабочей группы используется для проверки учетных данных, указанных в строке подключения.  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=d:\Northwind.mdb;Jet OLEDB:System Database=d:\NorthwindSystem.mdw;User ID=*****;Password=*****;  
```  
  
> [!IMPORTANT]
> Можно предоставить информацию о подключении к **OleDbConnection** в файле Универсальной ссылки данных (UDL); однако вы должны избегать этого. UDL-файлы не подвергаются шифрованию, и строки соединения хранятся в них в виде простого текста. Так как UDL-файл представляет собой внешний файловый ресурс для приложения, его нельзя защитить средствами .NET Framework. Файлы UDL не поддерживаются для **SqlClient**.  
  
### <a name="using-datadirectory-to-connect-to-accessjet"></a>Соединение с Access/Jet с помощью строки замены DataDirectory  
 Строка замены `DataDirectory` поддерживается не только клиентом `SqlClient`. Ее можно также использовать с поставщиками данных .NET для <xref:System.Data.OleDb> и <xref:System.Data.Odbc>. В следующем образце строки <xref:System.Data.OleDb.OleDbConnection> приведен синтаксис для подключения к базе данных Northwind.mdb, расположенной в папке приложения app_data. В этой папке также хранится системная база данных (System.mdw).  
  
```csharp  
"Provider=Microsoft.Jet.OLEDB.4.0;  
Data Source=|DataDirectory|\Northwind.mdb;  
Jet OLEDB:System Database=|DataDirectory|\System.mdw;"  
```  
  
> [!IMPORTANT]
> Указывать расположение системной базы данных в строке подключения не требуется, если база данных Access/Jet не защищена. Защита снята по умолчанию, все пользователи соединяются как встроенный пользователь Admin с пустым паролем. База данных Jet остается уязвимой для атаки, даже если правильно реализована безопасность на уровне пользователя. Поэтому в базе данных Access/Jet не рекомендуется хранить конфиденциальные данные, поскольку схема безопасности на основе файловой системы неизбежно обладает определенной уязвимостью.  
  
### <a name="connecting-to-excel"></a>Соединение с Excel  
 Поставщик Microsoft Jet используется для подключения с книгой Excel. В следующей строке подключения ключевое слово `Extended Properties` задает специфические свойства Excel. «HDR=Yes;» показывает, что первая строка содержит имена столбцов, а не данные, а «IMEX=1;» дает указания драйверу всегда считывать «смешанные» столбцы данных как текст.  
  
```csharp
Provider=Microsoft.Jet.OLEDB.4.0;Data Source=D:\MyExcel.xls;Extended Properties=""Excel 8.0;HDR=Yes;IMEX=1""  
```  
  
 Обратите внимание, что двойные кавычки, необходимые для ключевого слова `Extended Properties`, также должны заключаться в двойные кавычки.  
  
### <a name="data-shape-provider-connection-string-syntax"></a>Синтаксис строки подключения с поставщиком Data Shape  
 При соединении с поставщиком Microsoft Data Shape используются оба ключевых слова: `Provider` и `Data Provider`. В следующем примере поставщик Data Shape используется для подключения к экземпляру SQL Server.  
  
```csharp  
"Provider=MSDataShape;Data Provider=SQLOLEDB;Data Source=(local);Initial Catalog=pubs;Integrated Security=SSPI;"
```  
  
## <a name="odbc-connection-strings"></a>Строки подключения ODBC  
 Свойство <xref:System.Data.Odbc.OdbcConnection.ConnectionString%2A> класса <xref:System.Data.Odbc.OdbcConnection> позволяет получить или задать строку подключения для источника данных OLE DB. Строки подключения ODBC также поддерживаются построителем <xref:System.Data.Odbc.OdbcConnectionStringBuilder>.  
  
 Следующая строка подключения использует текстовый драйвер Microsoft.  
  
```csharp  
Driver={Microsoft Text Driver (*.txt; *.csv)};DBQ=d:\bin  
```  
  
### <a name="using-datadirectory-to-connect-to-visual-foxpro"></a>Использование строки замены DataDirectory для соединения с Visual FoxPro  
 Следующий образец строки подключения <xref:System.Data.Odbc.OdbcConnection> демонстрирует использование `DataDirectory` для соединения с файлом Microsoft Visual FoxPro.  
  
```csharp  
"Driver={Microsoft Visual FoxPro Driver};  
SourceDB=|DataDirectory|\MyData.DBC;SourceType=DBC;"  
```  
  
## <a name="oracle-connection-strings"></a>Строки подключения Oracle  
 Свойство <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A> класса <xref:System.Data.OracleClient.OracleConnection> позволяет получить или задать строку подключения для источника данных OLE DB. Строки подключения Oracle также поддерживаются построителем <xref:System.Data.OracleClient.OracleConnectionStringBuilder>.  
  
```csharp
Data Source=Oracle9i;User ID=*****;Password=*****;  
```  
  
 Дополнительные сведения о синтаксисе строки подключения ODBC см. в разделе <xref:System.Data.OracleClient.OracleConnection.ConnectionString%2A>.  
  
## <a name="see-also"></a>См. также раздел

- [Строки подключения](connection-strings.md)
- [Подключение к источнику данных](connecting-to-a-data-source.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
