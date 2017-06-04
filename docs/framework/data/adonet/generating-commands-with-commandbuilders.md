---
title: "Создание команд с помощью объекта CommandBuilders | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6e3fb8b5-373b-4f9e-ab03-a22693df8e91
caps.latest.revision: 6
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 6
---
# Создание команд с помощью объекта CommandBuilders
Если свойство `SelectCommand` задается динамически во время выполнения, например при помощи средства запроса, принимающего от пользователя текстовые команды, то во время разработки нельзя задавать соответствующие свойства `InsertCommand`, `UpdateCommand` или `DeleteCommand`.  Если <xref:System.Data.DataTable> сопоставляется с одной таблицей базы данных или создается из нее, то можно воспользоваться преимуществом объекта <xref:System.Data.Common.DbCommandBuilder> для автоматического создания сущностей `DeleteCommand`, `InsertCommand` и `UpdateCommand` объекта <xref:System.Data.Common.DbDataAdapter>.  
  
 Минимальным требованием для работы автоматического создания команд является задание свойства `SelectCommand`.  Схема таблицы, получаемая свойством `SelectCommand`, определяет синтаксис автоматически созданных инструкций INSERT, UPDATE и DELETE.  
  
 Для возврата метаданных, необходимых для создания команд INSERT, UPDATE и DELETE SQL, объект <xref:System.Data.Common.DbCommandBuilder> должен выполнить команду `SelectCommand`.  В результате необходим дополнительный цикл приема\-передачи с источником данных, что может снизить производительность.  Для достижения оптимальной производительности вместо использования <xref:System.Data.Common.DbCommandBuilder> следует задать команды явным образом.  
  
 Свойство `SelectCommand` должно также возвратить по крайней мере один столбец первичного ключа или столбец с атрибутом UNIQUE.  Если отсутствует и то и другое, то возникнет исключение `InvalidOperation` и команда сформирована не будет.  
  
 При наличии связи с `DataAdapter` объект <xref:System.Data.Common.DbCommandBuilder> автоматически создает свойства `InsertCommand`, `UpdateCommand` и `DeleteCommand` объекта `DataAdapter`, если они являются пустыми ссылками.  Если для свойства уже существует `Command`, используется существующая `Command`.  
  
 Представления базы данных, созданные соединением двух или более таблиц, не считаются одной таблицей базы данных.  В данном экземпляре нельзя использовать <xref:System.Data.Common.DbCommandBuilder> для автоматического создания команд. Необходимо указать команды явным образом.  Сведения о явном задании команд для внесения обновлений, выполненных для `DataSet`, обратно в источник данных см. в разделе [Обновление источников данных с помощью объектов DataAdapter](../../../../docs/framework/data/adonet/updating-data-sources-with-dataadapters.md).  
  
 Может потребоваться сопоставить выходные параметры с обновленной строкой `DataSet`.  Одной общей задачей будет извлечение значения автоматически созданного поля идентификатора или временной метки из источника данных.  <xref:System.Data.Common.DbCommandBuilder> по умолчанию не будет сопоставлять выходные параметры со столбцами обновленной строки.  В данном экземпляре необходимо указать команду явным образом.  Пример сопоставления автоматически созданного поля идентификатора со столбцом вставленной строки см. в разделе [Получение значений идентификаторов или автонумерации](../../../../docs/framework/data/adonet/retrieving-identity-or-autonumber-values.md).  
  
## Правила для автоматически созданных команд  
 В следующей таблице показаны правила создания автоматически созданных команд.  
  
|Команда|Правило|  
|-------------|-------------|  
|`InsertCommand`|Выполняет операцию вставки строки в источнике данных для всех строк таблицы со свойством <xref:System.Data.DataRow.RowState%2A> равным <xref:System.Data.DataRowState>.  Вставляет значения для всех обновляемых столбцов \(за исключением идентификаторов, выражений или временных меток\).|  
|`UpdateCommand`|Выполняет обновление строк в источнике данных для всех строк таблицы со свойством `RowState` равным <xref:System.Data.DataRowState>.  Обновляет значения всех столбцов, за исключением столбцов, которые не являются обновляемыми, например идентификаторов или выражений.  Обновляет все строки, в которых значения столбцов в источнике данных совпадают со значениями столбцов первичных ключей строки и в которых оставшиеся в источнике данных столбцы совпадают с исходными значениями строки.  Дополнительные сведения см. в подразделе «Модель оптимистичного параллелизма для обновлений и удалений» далее в этом разделе.|  
|`DeleteCommand`|Выполняет операцию удаления строки в источнике данных для всех строк таблицы, у которых свойство `RowState` равно <xref:System.Data.DataRowState>.  Удаляет все строки, в которых значения столбцов совпадают со значениями столбцов первичных ключей строки и в которых оставшиеся в источнике данных столбцы совпадают с исходными значениями строки.  Дополнительные сведения см. в подразделе «Модель оптимистичного параллелизма для обновлений и удалений» далее в этом разделе.|  
  
## Модель оптимистичного параллелизма для обновлений и удалений  
 Логика автоматического создания команд для инструкций UPDATE и DELETE базируется на *оптимистичном параллелизме*, т. е. записи не блокируются для редактирования и могут быть в любое время изменены другими пользователями или процессами.  Вследствие того что запись можно изменить после ее возврата из инструкции SELECT, но до вызова инструкции UPDATE или DELETE, автоматически созданная инструкция UPDATE или DELETE содержит предложение WHERE, указывающее на то, что строка обновляется только в случае наличия в ней всех исходных значений и она не была удалена из источника данных.  Это делается во избежание перезаписи новых данных.  Когда автоматически созданное обновление пытается обновить строку, которая была удалена или не содержит исходные значения, найденные в <xref:System.Data.DataSet>, команда не изменяет записи и вызывается исключение <xref:System.Data.DBConcurrencyException>.  
  
 Если требуется выполнить инструкцию UPDATE или DELETE независимо от исходных значений, необходимо явно задать свойство `UpdateCommand` для `DataAdapter` и не полагаться на автоматическое создание команд.  
  
## Ограничения логики автоматического создания команд  
 На автоматическое создание команд накладываются следующие ограничения.  
  
### Только несвязанные таблицы  
 Логика автоматического создания команд создает инструкции INSERT, UPDATE или DELETE для изолированных таблиц, не принимая во внимание связи с другими таблицами в источнике данных.  В результате при вызове `Update` для отправки изменений столбца, участвующего в ограничении внешнего ключа базы данных, может произойти ошибка.  Чтобы избежать этого исключения, не следует использовать <xref:System.Data.Common.DbCommandBuilder> для обновления столбцов, вовлеченных в ограничение внешнего ключа. Вместо этого нужно явно задать инструкции, используемые для выполнения операции.  
  
### Имена таблиц и столбцов  
 Логика автоматического создания команд может дать сбой при наличии в именах столбцов или таблиц любых специальных символов, например пробелов, точек, двойных кавычек или других символов, отличных от буквенно\-цифровых, даже отделенных квадратными скобками.  В зависимости от поставщика, задавая параметры QuotePrefix и QuoteSuffix, можно дать возможность логике создания обрабатывать пробелы, но для специальных символов это не сработает.  Поддерживаются полностью указанные имена таблиц в виде *catalog.schema.table*.  
  
## Использование построителя команд для автоматического создания инструкции SQL  
 Чтобы автоматически создать инструкции SQL для `DataAdapter`, сначала следует установить его свойство `SelectCommand`, затем создать объект `CommandBuilder` и в качестве аргумента, для которого `CommandBuilder` автоматически создаст инструкции SQL, указать `DataAdapter`.  
  
```vb  
' Assumes that connection is a valid SqlConnection object   
' inside of a Using block.  
Dim adapter As SqlDataAdapter = New SqlDataAdapter( _  
  "SELECT * FROM dbo.Customers", connection)  
Dim builder As SqlCommandBuilder = New SqlCommandBuilder(adapter)  
builder.QuotePrefix = "["  
builder.QuoteSuffix = "]"  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object  
// inside of a using block.  
SqlDataAdapter adapter = new SqlDataAdapter(  
  "SELECT * FROM dbo.Customers", connection);  
SqlCommandBuilder builder = new SqlCommandBuilder(adapter);  
builder.QuotePrefix = "[";  
builder.QuoteSuffix = "]";  
```  
  
## Изменение SelectCommand  
 При изменении свойства `CommandText`, принадлежащего свойству `SelectCommand`, после автоматического создания команд INSERT, UPDATE или DELETE может возникнуть исключение.  Если измененное свойство `SelectCommand.CommandText` содержит сведения о схеме, которые не согласованы с используемыми `SelectCommand.CommandText` сведениями при автоматическом создании команд INSERT, UPDATE или DELETE, то последующие вызовы к методу `DataAdapter.Update` могут содержать попытки обращения к столбцам, которых больше нет в текущей таблице, на которую ссылается `SelectCommand`, и в этом случае возникнет исключение.  
  
 Для обновления сведений о схеме, используемой `CommandBuilder` для автоматического создания команд, следует вызвать метод `RefreshSchema` объекта `CommandBuilder`.  
  
 Чтобы узнать, какая команда была автоматически создана, необходимо с помощью методов `GetInsertCommand`, `GetUpdateCommand` и `GetDeleteCommand` объекта `CommandBuilder` получить ссылку на автоматически созданные команды и проверить свойство `CommandText`, соответствующее команде.  
  
 Следующий пример кода записывает в консоль автоматически созданную команду UPDATE.  
  
```  
Console.WriteLine(builder.GetUpdateCommand().CommandText)  
```  
  
 В следующем примере повторно создается таблица `Customers` из набора данных `custDS`.  Метод **RefreshSchema** вызывается для внесения новых сведений о столбцах в автоматически созданные команды.  
  
```vb  
' Assumes an open SqlConnection and SqlDataAdapter inside of a Using block.  
adapter.SelectCommand.CommandText = _  
  "SELECT CustomerID, ContactName FROM dbo.Customers"  
builder.RefreshSchema()  
  
custDS.Tables.Remove(custDS.Tables("Customers"))  
adapter.Fill(custDS, "Customers")  
```  
  
```csharp  
// Assumes an open SqlConnection and SqlDataAdapter inside of a using block.  
adapter.SelectCommand.CommandText =   
  "SELECT CustomerID, ContactName FROM dbo.Customers";  
builder.RefreshSchema();  
  
custDS.Tables.Remove(custDS.Tables["Customers"]);  
adapter.Fill(custDS, "Customers");  
```  
  
## См. также  
 [Команды и параметры](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Выполнение команды](../../../../docs/framework/data/adonet/executing-a-command.md)   
 [DbConnection, DbCommand и DbException](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)   
 [Центр разработчиков, поставщики ADO.NET Managed Provider и набор данных](http://go.microsoft.com/fwlink/?LinkId=217917)