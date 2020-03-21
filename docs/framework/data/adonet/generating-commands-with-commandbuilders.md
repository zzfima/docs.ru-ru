---
title: Создание команд с помощью построителей CommandBuilder
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6e3fb8b5-373b-4f9e-ab03-a22693df8e91
ms.openlocfilehash: 76c2a6cb0661a0e39fc3a0dd599fcbb3c046f382
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149616"
---
# <a name="generating-commands-with-commandbuilders"></a>Создание команд с помощью построителей CommandBuilder
Если свойство `SelectCommand` задается динамически во время выполнения, например при помощи средства запроса, принимающего от пользователя текстовые команды, то во время разработки нельзя задавать соответствующие свойства `InsertCommand`, `UpdateCommand` или `DeleteCommand`. Если <xref:System.Data.DataTable> сопоставляется с одной таблицей базы данных или создается из нее, то можно воспользоваться преимуществом объекта <xref:System.Data.Common.DbCommandBuilder> для автоматического создания сущностей `DeleteCommand`, `InsertCommand` и `UpdateCommand` объекта <xref:System.Data.Common.DbDataAdapter>.  
  
 Минимальным требованием для работы автоматического создания команд является задание свойства `SelectCommand`. Схема таблицы, получаемая свойством `SelectCommand`, определяет синтаксис автоматически созданных инструкций INSERT, UPDATE и DELETE.  
  
 Для возврата метаданных, необходимых для создания команд INSERT, UPDATE и DELETE SQL, объект <xref:System.Data.Common.DbCommandBuilder> должен выполнить команду `SelectCommand`. В результате необходим дополнительный цикл приема-передачи с источником данных, что может снизить производительность. Для достижения оптимальной производительности вместо использования <xref:System.Data.Common.DbCommandBuilder> следует задать команды явным образом.  
  
 Свойство `SelectCommand` должно также возвратить по крайней мере один столбец первичного ключа или столбец с атрибутом UNIQUE. Если отсутствует и то и другое, то возникнет исключение `InvalidOperation` и команда сформирована не будет.  
  
 При наличии связи с `DataAdapter` объект <xref:System.Data.Common.DbCommandBuilder> автоматически создает свойства `InsertCommand`, `UpdateCommand` и `DeleteCommand` объекта `DataAdapter`, если они являются пустыми ссылками. Если для свойства уже существует `Command`, используется существующая `Command`.  
  
 Представления базы данных, созданные соединением двух или более таблиц, не считаются одной таблицей базы данных. В данном экземпляре нельзя использовать <xref:System.Data.Common.DbCommandBuilder> для автоматического создания команд. Необходимо указать команды явным образом. Для получения информации о явном настройке команд для разрешения обновлений к источнику `DataSet` данных см. Об [обновлении источников данных с помощью DataAdapters.](updating-data-sources-with-dataadapters.md)  
  
 Может потребоваться сопоставить выходные параметры с обновленной строкой `DataSet`. Одной общей задачей будет извлечение значения автоматически созданного поля идентификатора или временной метки из источника данных. <xref:System.Data.Common.DbCommandBuilder> по умолчанию не будет сопоставлять выходные параметры со столбцами обновленной строки. В данном экземпляре необходимо указать команду явным образом. Например, отображение автоматического поля идентификации обратно в столбец вставленной [строки см.](retrieving-identity-or-autonumber-values.md)  
  
## <a name="rules-for-automatically-generated-commands"></a>Правила для автоматически созданных команд  
 В следующей таблице показаны правила создания автоматически созданных команд.  
  
|Get-Help|Правило|  
|-------------|----------|  
|`InsertCommand`|Выполняет операцию вставки строки в источнике данных для всех строк таблицы со свойством <xref:System.Data.DataRow.RowState%2A> равным <xref:System.Data.DataRowState.Added>. Вставляет значения для всех обновляемых столбцов (за исключением идентификаторов, выражений или временных меток).|  
|`UpdateCommand`|Выполняет обновление строк в источнике данных для всех строк таблицы со свойством `RowState` равным <xref:System.Data.DataRowState.Modified>. Обновляет значения всех столбцов, за исключением столбцов, которые не являются обновляемыми, например идентификаторов или выражений. Обновляет все строки, в которых значения столбцов в источнике данных совпадают со значениями столбцов первичных ключей строки и в которых оставшиеся в источнике данных столбцы совпадают с исходными значениями строки. Дополнительные сведения см. в подразделе «Модель оптимистичного параллелизма для обновлений и удалений» далее в этом разделе.|  
|`DeleteCommand`|Выполняет операцию удаления строки в источнике данных для всех строк таблицы, у которых свойство `RowState` равно <xref:System.Data.DataRowState.Deleted>. Удаляет все строки, в которых значения столбцов совпадают со значениями столбцов первичных ключей строки и в которых оставшиеся в источнике данных столбцы совпадают с исходными значениями строки. Дополнительные сведения см. в подразделе «Модель оптимистичного параллелизма для обновлений и удалений» далее в этом разделе.|  
  
## <a name="optimistic-concurrency-model-for-updates-and-deletes"></a>Модель оптимистичного параллелизма для обновлений и удалений  
 Логика автоматического генерации команд для обновлений и DELETE-инструкций основана на *оптимистичном параллели,* то есть записи не блокируются для редактирования и могут быть изменены другими пользователями или процессами в любое время. Вследствие того что запись можно изменить после ее возврата из инструкции SELECT, но до вызова инструкции UPDATE или DELETE, автоматически созданная инструкция UPDATE или DELETE содержит предложение WHERE, указывающее на то, что строка обновляется только в случае наличия в ней всех исходных значений и она не была удалена из источника данных. Это делается во избежание перезаписи новых данных. Когда автоматически созданное обновление пытается обновить строку, которая была удалена или не содержит исходные значения, найденные в <xref:System.Data.DataSet>, команда не изменяет записи и вызывается исключение <xref:System.Data.DBConcurrencyException>.  
  
 Если требуется выполнить инструкцию UPDATE или DELETE независимо от исходных значений, необходимо явно задать свойство `UpdateCommand` для `DataAdapter` и не полагаться на автоматическое создание команд.  
  
## <a name="limitations-of-automatic-command-generation-logic"></a>Ограничения логики автоматического создания команд  
 На автоматическое создание команд накладываются следующие ограничения.  
  
### <a name="unrelated-tables-only"></a>Только несвязанные таблицы  
 Логика автоматического создания команд создает инструкции INSERT, UPDATE или DELETE для изолированных таблиц, не принимая во внимание связи с другими таблицами в источнике данных. В результате при вызове `Update` для отправки изменений столбца, участвующего в ограничении внешнего ключа базы данных, может произойти ошибка. Чтобы избежать этого исключения, не следует использовать <xref:System.Data.Common.DbCommandBuilder> для обновления столбцов, вовлеченных в ограничение внешнего ключа. Вместо этого нужно явно задать инструкции, используемые для выполнения операции.  
  
### <a name="table-and-column-names"></a>Имена таблиц и столбцов  
 Логика автоматического создания команд может дать сбой при наличии в именах столбцов или таблиц любых специальных символов, например пробелов, точек, двойных кавычек или других символов, отличных от буквенно-цифровых, даже отделенных квадратными скобками. В зависимости от поставщика, задавая параметры QuotePrefix и QuoteSuffix, можно дать возможность логике создания обрабатывать пробелы, но для специальных символов это не сработает. Поддерживаются полностью квалифицированные названия таблиц в виде *каталога.schema.table.*  
  
## <a name="using-the-commandbuilder-to-automatically-generate-an-sql-statement"></a>Использование построителя команд для автоматического создания инструкции SQL  
 Чтобы автоматически создать инструкции SQL для `DataAdapter`, сначала следует установить его свойство `SelectCommand`, затем создать объект `DataAdapter` и в качестве аргумента, для которого `CommandBuilder` автоматически создаст инструкции SQL, указать `DataAdapter`.  
  
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
  
## <a name="modifying-the-selectcommand"></a>Изменение SelectCommand  
 При изменении свойства `CommandText`, принадлежащего свойству `SelectCommand`, после автоматического создания команд INSERT, UPDATE или DELETE может возникнуть исключение. Если измененное свойство `SelectCommand.CommandText` содержит сведения о схеме, которые не согласованы с используемыми `SelectCommand.CommandText` сведениями при автоматическом создании команд INSERT, UPDATE или DELETE, то последующие вызовы к методу `DataAdapter.Update` могут содержать попытки обращения к столбцам, которых больше нет в текущей таблице, на которую ссылается `SelectCommand`, и в этом случае возникнет исключение.  
  
 Для обновления сведений о схеме, используемой `CommandBuilder` для автоматического создания команд, следует вызвать метод `RefreshSchema` объекта `CommandBuilder`.  
  
 Чтобы узнать, какая команда была автоматически создана, необходимо с помощью методов `GetInsertCommand`, `GetUpdateCommand` и `GetDeleteCommand` объекта `CommandBuilder` получить ссылку на автоматически созданные команды и проверить свойство `CommandText`, соответствующее команде.  
  
 Следующий пример кода записывает в консоль автоматически созданную команду UPDATE.  
  
```vb
Console.WriteLine(builder.GetUpdateCommand().CommandText)  
```

```csharp
Console.WriteLine(builder.GetUpdateCommand().CommandText);
```
  
 В следующем примере повторно создается таблица `Customers` из набора данных `custDS`. Метод **RefreshSchema** вызывается для обновления автоматически генерируемых команд с помощью этой новой информации о столбце.  
  
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
  
## <a name="see-also"></a>См. также раздел

- [Команды и параметры](commands-and-parameters.md)
- [Выполнение командования](executing-a-command.md)
- [DbConnection, DbCommand и DbException](dbconnection-dbcommand-and-dbexception.md)
- [Общие сведения об ADO.NET](ado-net-overview.md)
