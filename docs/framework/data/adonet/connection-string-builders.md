---
title: Построители строк подключения
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8434b608-c4d3-43d3-8ae3-6d8c6b726759
ms.openlocfilehash: e1f8d636e793b2d8b984fe1aa0b823fa58a4981d
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2019
ms.locfileid: "73040180"
---
# <a name="connection-string-builders"></a>Построители строк подключения
В более ранних версиях ADO.NET проверка строк подключения со сцепленными строковыми значениями не выполнялась, так что во время выполнения неверное ключевое слово создавало <xref:System.ArgumentException>. Каждый из .NET Framework поставщиков данных поддерживал разный синтаксис для ключевых слов строки подключения, что делает несложным создание допустимых строк соединения, если это сделано вручную. Для решения этой проблемы в ADO.NET 2,0 появились новые построители строк подключения для каждого .NET Framework поставщика данных. Каждый поставщик данных включает класс построителя строк соединения со строгой типизацией, наследованный от класса <xref:System.Data.Common.DbConnectionStringBuilder>. В следующей таблице перечислены поставщики данных .NET Framework и связанные с ними классы построителя строк подключения.  
  
|Поставщик|Класс ConnectionStringBuilder|  
|--------------|-----------------------------------|  
|<xref:System.Data.SqlClient>|<xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OleDb>|<xref:System.Data.OleDb.OleDbConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.Odbc>|<xref:System.Data.Odbc.OdbcConnectionStringBuilder?displayProperty=nameWithType>|  
|<xref:System.Data.OracleClient>|<xref:System.Data.OracleClient.OracleConnectionStringBuilder?displayProperty=nameWithType>|  
  
## <a name="connection-string-injection-attacks"></a>Атаки путем внедрения данных в строку подключения  
 Атака путем внедрения данных в строку соединения может произойти при использовании динамического объединения строк для построения строк соединения, основанных на входных данных пользователя. Если строка не проверяется, а вредоносный текст или символы не экранируются, злоумышленник может получить потенциальный доступ к конфиденциальным данным или другим ресурсам сервера. Например, злоумышленник может осуществить атаку, установив точку с запятой и добавив дополнительное значение. Строка соединения анализируется с помощью алгоритма «по последнему значению», и допустимое значение заменяется вредоносными данными.  
  
 Классы построителей строк соединения созданы для устранения предположений и защиты от синтаксических ошибок и уязвимостей системы безопасности. Они предоставляют методы и свойства, соответствующие известным парам «ключ-значение», разрешенным каждым поставщиком данных. Каждый класс поддерживает фиксированную коллекцию синонимов и может переводить синоним в соответствующее общеизвестное ключевое имя. Выполняются проверки на допустимые пары «ключ-значение», и недопустимая пара вызывает исключение. Кроме того, внедренные значения обрабатываются безопасным образом.  
  
 В следующем примере демонстрируется обработка с помощью объекта <xref:System.Data.SqlClient.SqlConnectionStringBuilder> дополнительного значения для параметра `Initial Catalog`.  
  
```vb  
Dim builder As New System.Data.SqlClient.SqlConnectionStringBuilder  
builder("Data Source") = "(local)"  
builder("Integrated Security") = True  
builder("Initial Catalog") = "AdventureWorks;NewValue=Bad"  
Console.WriteLine(builder.ConnectionString)  
```  
  
```csharp  
System.Data.SqlClient.SqlConnectionStringBuilder builder =  
  new System.Data.SqlClient.SqlConnectionStringBuilder();  
builder["Data Source"] = "(local)";  
builder["integrated Security"] = true;  
builder["Initial Catalog"] = "AdventureWorks;NewValue=Bad";  
Console.WriteLine(builder.ConnectionString);  
```  
  
 Выход показывает, что объект <xref:System.Data.SqlClient.SqlConnectionStringBuilder> правильно выполняет обработку параметра путем экранирования дополнительного значения, заключенного в двойные кавычки, вместо того чтобы добавить его в строку соединения в качестве новой пары «ключ-значение».  
  
```output  
data source=(local);Integrated Security=True;  
initial catalog="AdventureWorks;NewValue=Bad"  
```  
  
## <a name="building-connection-strings-from-configuration-files"></a>Построение строк соединения из файлов конфигурации  
 Если некоторые элементы строки соединения известны заранее, их можно сохранить в файле конфигурации и во время выполнения получить для построения полной строки соединения. Например, в отличие от имени сервера, имя базы данных может быть известно заранее. Также можно принудительно задать ввод пользователем имени и пароля во время выполнения, чтобы исключить возможность внедрения других значений в строку соединения.  
  
 Один из перегруженных конструкторов для построителя строки соединения принимает в качестве аргумента значение типа <xref:System.String>, что позволяет использовать частичную строку соединения, которую впоследствии пользователь может дополнить. Частичную строку соединения можно сохранить в файле конфигурации и получить во время выполнения.  
  
> [!NOTE]
> Пространство имен <xref:System.Configuration> обеспечивает программный доступ к файлам конфигурации, предоставляя класс <xref:System.Web.Configuration.WebConfigurationManager> для веб-приложений и класс <xref:System.Configuration.ConfigurationManager> для приложений Windows. Дополнительные сведения о работе со строками подключения и файлами конфигурации см. в разделе [строки подключения и файлы конфигурации](connection-strings-and-configuration-files.md).  
  
### <a name="example"></a>Пример  
 В этом примере демонстрируется получение частичной строки соединения из файла конфигурации и ее завершение путем установки свойств <xref:System.Data.SqlClient.SqlConnectionStringBuilder.DataSource%2A>, <xref:System.Data.SqlClient.SqlConnectionStringBuilder.UserID%2A> и <xref:System.Data.SqlClient.SqlConnectionStringBuilder.Password%2A> для объекта <xref:System.Data.SqlClient.SqlConnectionStringBuilder>. Файл конфигурации определяется следующим образом.  
  
```xml  
<connectionStrings>  
  <clear/>  
  <add name="partialConnectString"   
    connectionString="Initial Catalog=Northwind;"  
    providerName="System.Data.SqlClient" />  
</connectionStrings>  
```  
  
> [!NOTE]
> Для запуска кода необходимо задать в проекте ссылку на библиотеку `System.Configuration.dll`.  
  
 [!code-csharp[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/CS/source.cs#1)]
 [!code-vb[DataWorks SqlConnectionStringBuilder.UserNamePwd#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlConnectionStringBuilder.UserNamePwd/VB/source.vb#1)]  
  
## <a name="see-also"></a>См. также

- [Строки подключения](connection-strings.md)
- [Конфиденциальность и безопасность данных](privacy-and-data-security.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
