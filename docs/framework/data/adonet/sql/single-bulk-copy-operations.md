---
title: "Отдельные операции массового копирования"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5e7ff0be-3f23-4996-a92c-bd54d65c3836
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 001bd24d46d0106887ad693534c51d152eedfb1d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="single-bulk-copy-operations"></a>Отдельные операции массового копирования
Самый простой способ выполнения операции массового копирования в SQL Server заключается в выполнении одной операции для базы данных. По умолчанию операция массового копирования выполняется как изолированная, без использования транзакции и без возможности отката.  
  
> [!NOTE]
>  Если в случае ошибки необходимо откатить все или часть массового копирования, можно либо воспользоваться транзакцией под управлением <xref:System.Data.SqlClient.SqlBulkCopy>, либо выполнить операцию массового копирования в рамках существующей транзакции. **SqlBulkCopy** также будет работать с <xref:System.Transactions> Если соединение прикреплено (явно или неявно) в **System.Transactions** транзакции.  
>   
>  Дополнительные сведения см. в разделе [транзакции и операции массового копирования](../../../../../docs/framework/data/adonet/sql/transaction-and-bulk-copy-operations.md).  
  
 Далее приведены общие шаги по выполнению операции массового копирования.  
  
1.  Подключитесь к серверу-источнику и получите данные для копирования. Если данные можно получить из объекта <xref:System.Data.IDataReader> или <xref:System.Data.DataTable>, они также могут поступать из других источников.  
  
2.  Подключение к серверу назначения (если не требуется **SqlBulkCopy** для установления соединения автоматически).  
  
3.  Создайте объект <xref:System.Data.SqlClient.SqlBulkCopy>, задав необходимые свойства.  
  
4.  Задать **DestinationTableName** свойство, указывающее целевую таблицу для массовой операции вставки.  
  
5.  Вызовите один из **WriteToServer** методы.  
  
6.  При необходимости обновите свойства и вызвать метод **WriteToServer** еще раз при необходимости.  
  
7.  Вызовите метод <xref:System.Data.SqlClient.SqlBulkCopy.Close%2A> или заключите операции массового копирования в оболочку из инструкции `Using`.  
  
> [!CAUTION]
>  Рекомендуется, чтобы типы данных исходного и целевого столбца были одинаковыми. Если типы данных не совпадают, **SqlBulkCopy** попытается преобразовать каждое исходное значение в целевой тип данных, с помощью правил, применяемых методом <xref:System.Data.SqlClient.SqlParameter.Value%2A>. Преобразования могут ухудшать производительность, а также приводить к непредвиденным ошибкам. Например, в большинстве случаев тип данных `Double` можно преобразовать в тип данных `Decimal`, однако иногда это невозможно.  
  
## <a name="example"></a>Пример  
 Следующее приложение командной строки демонстрирует, как загружать данные при помощи класса <xref:System.Data.SqlClient.SqlBulkCopy>. В этом примере <xref:System.Data.SqlClient.SqlDataReader> используется для копирования данных из **Production.Product** в таблицу [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] **AdventureWorks** базы данных в аналогичную таблицу в той же базе данных.  
  
> [!IMPORTANT]
>  Этот образец не запустится, пока вы не создадите рабочие таблицы, как описано в [пример настройки массового копирования](../../../../../docs/framework/data/adonet/sql/bulk-copy-example-setup.md). Данный код предназначен для демонстрации синтаксиса использования **SqlBulkCopy** только. Если исходная и целевая таблицы расположены в одном и том же экземпляре SQL Server, легче и быстрее использовать для копирования данных инструкцию `INSERT … SELECT` языка Transact-SQL.  
  
 [!code-csharp[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/CS/source.cs#1)]
 [!code-vb[DataWorks BulkCopy.Single#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks BulkCopy.Single/VB/source.vb#1)]  
  
## <a name="performing-a-bulk-copy-operation-using-transact-sql-and-the-command-class"></a>Выполнение операции массового копирования при помощи Transact-SQL и класса команды  
 В следующем примере иллюстрируется, как применять метод <xref:System.Data.SqlClient.SqlCommand.ExecuteNonQuery%2A> для выполнения инструкции BULK INSERT.  
  
> [!NOTE]
>  Путь к файлу для источника данных указан относительно сервера. Чтобы операция массового копирования была успешной, процесс сервера должен иметь доступ к этому пути.  
  
```vb  
Using connection As SqlConnection = New SqlConnection(connectionString)  
Dim queryString As String = _  
    "BULK INSERT Northwind.dbo.[Order Details] FROM " & _  
    "'f:\mydata\data.tbl' WITH (FORMATFILE='f:\mydata\data.fmt' )"  
connection.Open()  
SqlCommand command = New SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery()  
End Using  
```  
  
```csharp  
using (SqlConnection connection = New SqlConnection(connectionString))  
{  
string queryString =  "BULK INSERT Northwind.dbo.[Order Details] " +  
    "FROM 'f:\mydata\data.tbl' " +  
    "WITH ( FORMATFILE='f:\mydata\data.fmt' )";  
connection.Open();  
SqlCommand command = new SqlCommand(queryString, connection);  
  
command.ExecuteNonQuery();  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Операции массового копирования в SQL Server](../../../../../docs/framework/data/adonet/sql/bulk-copy-operations-in-sql-server.md)  
 [Центр разработчиков наборов данных и управляемых поставщиков ADO.NET](http://go.microsoft.com/fwlink/?LinkId=217917)
