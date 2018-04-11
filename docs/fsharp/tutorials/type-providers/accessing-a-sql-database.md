---
title: Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов (F#)
description: 'Сведения об использовании поставщика типов SqlDataConnection (LINQ to SQL) в F # 3.0 для создания типов для базы данных SQL, при наличии подключения реального времени.'
keywords: visual f#, f#, функциональное программирование
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1c413eb0-16a5-4c1a-9a4e-ad6877e645d6
ms.openlocfilehash: dbc5d889fb7883b4327180fdf34accf45bf519e7
ms.sourcegitcommit: b750a8e3979749b214e7e10c82efb0a0524dfcb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/10/2018
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers"></a>Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов

> [!NOTE]
В этом руководстве, была написана для F # 3.0 и будут обновлены.  Актуальные сведения о кроссплатформенных поставщиках типов см. в описании [FSharp.Data](https://fsharp.github.io/FSharp.Data/).

> [!NOTE]
Справочные ссылки API, вы перейдете MSDN.  Работа над справочником по API docs.microsoft.com не завершена.

В этом пошаговом руководстве описывается использование поставщика типов SqlDataConnection (LINQ to SQL), который доступен в F # 3.0 для создания типов данных в базе данных SQL, при наличии динамического подключения к базе данных. Если у вас активное соединение к базе данных, но нужно LINQ файл схемы SQL (DBML-файл), см. раздел [Пошаговое руководство: Создание типов F # из файла dBm](generating-fsharp-types-from-dbml.md).

В данном пошаговом руководстве рассмотрены следующие задачи. Эти задачи необходимо выполнять в указанном порядке для данного пошагового руководства для успешного выполнения:


- Подготовка тестовой базой данных.

- Создание проекта

- Настройка поставщика типов

- Запрос данных

- Работа с полями, допускающие значение NULL

- Вызов хранимой процедуры

- Обновление базы данных

- Выполнение кода Transact-SQL

- Полный контекст данных с помощью

- Удаление данных

- Создайте тестовую базу данных (при необходимости)

## <a name="preparing-a-test-database"></a>Подготовка тестовой базой данных.
На сервере, на котором выполняется SQL Server создайте базу данных в целях тестирования. Можно использовать базу данных создать скрипт в нижней части этой страницы в разделе [Создание тестовой базы данных](#creating-a-test-database) это сделать.


#### <a name="to-prepare-a-test-database"></a>Для подготовки тестовой базы данных

Чтобы выполнить скрипт создания MyDatabase, откройте **представление** меню и выберите **обозреватель объектов SQL Server** или нажмите сочетание клавиш Ctrl +\, клавиши Ctrl + S. В **обозреватель объектов SQL Server** окна, откройте контекстное меню для соответствующего экземпляра, **новый запрос**, скопируйте сценарий в нижней части этой страницы и затем вставить скрипт в редакторе. Чтобы запустить скрипт SQL, выберите значок панели инструментов треугольное символом или нажмите сочетание клавиш Ctrl + Q. Дополнительные сведения о **обозреватель объектов SQL Server**, в разделе [разработка подключенной базы данных](https://msdn.microsoft.com/library/hh272679(VS.103).aspx).


## <a name="creating-the-project"></a>Создание проекта
Создайте проект приложения F #.


#### <a name="to-create-and-set-up-the-project"></a>Создание и настройка проекта

1. Создайте новый проект приложения F #.

2. Добавьте ссылки на [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3), а также `System.Data`, и `System.Data.Linq`.

3. Откройте соответствующие пространства имен, добавив следующий код в верхнюю часть вашего файла кода F # Program.fs.

  ```fsharp
open System
open System.Data
open System.Data.Linq
open Microsoft.FSharp.Data.TypeProviders
open Microsoft.FSharp.Linq
```

4. Как и в большинстве программ F #, может выполнять код в этом пошаговом руководстве как компилированной программы или интерактивном режиме запустить ее как сценарий. Если вы предпочитаете использовать сценарии, откройте контекстное меню узла проекта, выберите **добавить новый элемент**, добавьте файл скрипта F # и добавьте код в каждом шаге в скрипт. Необходимо добавить следующие строки в верхней части файла для загрузки ссылок на сборки.

  ```fsharp
#r "System.Data.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

  Затем можно выбрать каждый блок кода, как добавить его и нажмите клавиши Alt + ВВОД для запуска в F # Interactive.

## <a name="setting-up-a-type-provider"></a>Настройка поставщика типов
На этом шаге создается тип поставщика схемы базы данных.


#### <a name="to-set-up-the-type-provider-from-a-direct-database-connection"></a>Чтобы настроить поставщик типов подключения прямых базы данных

Существуют две важные строки кода, необходимое для создания типов, которые можно использовать для запросов к базе данных SQL с помощью поставщика типов. Во-первых можно создать экземпляр поставщика типа. Чтобы сделать это, создайте как сокращенную форму для типа выглядит `SqlDataConnection` с статический универсальный параметр. `SqlDataConnection` — Это поставщик типа SQL и их не следует путать с `SqlConnection` типа, используемые при программировании ADO.NET. Если имеется база данных, необходимо подключиться к, а строка подключения, используйте следующий код для вызова поставщика типов. Замените строки подключения для примера строка заданному. Например если сервер MYSERVER и экземпляр базы данных — ЭКЗЕМПЛЯР, имя базы данных — MyDatabase и вы хотите использовать проверку подлинности Windows для доступа к базе данных, то строка подключения будет как имеется в следующем примере кода.

```fsharp
type dbSchema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;">
let db = dbSchema.GetDataContext()

// Enable the logging of database activity to the console.
db.DataContext.Log <- System.Console.Out
```

Теперь у вас есть тип, `dbSchema`, который является родительским типом, содержащий созданные типы, представляющие таблицы базы данных. Также имеется объект, `db`, который имеет членами всех таблиц в базе данных. Имена таблиц представляются свойства и тип этих свойств создается компилятором F #. Самих типов отображаются как вложенные типы под `dbSchema.ServiceTypes`. Таким образом любые данные, полученные для строк из этих таблиц — это экземпляр соответствующего типа, который был создан для этой таблицы. Имя типа `ServiceTypes.Table1`.

Чтобы ознакомиться с интерпретацией запросов в запросы SQL языка F #, просмотрите строки, которая задает `Log` свойства в контексте данных.

Для дальнейшего изучения типов, созданных поставщиком типов, добавьте следующий код.

```fsharp
let table1 = db.Table1
```

Наведите указатель мыши на `table1` для просмотра его тип. Его тип — `System.Data.Linq.Table<dbSchema.ServiceTypes.Table1>` и универсального аргумента подразумевается, что тип каждой строки является созданного типа `dbSchema.ServiceTypes.Table1`. Компилятор создает аналогичного для каждой таблицы в базе данных.

## <a name="querying-the-data"></a>Запрос данных
На этом этапе запись запроса с помощью выражения запросов F #.


#### <a name="to-query-the-data"></a>Действия для запроса данных

1. Теперь можно создайте запрос для этой таблицы в базе данных. Добавьте следующий код.

  ```fsharp
   let query1 =
     query {
       for row in db.Table1 do
       select row
     }
   query1 |> Seq.iter (fun row -> printfn "%s %d" row.Name row.TestData1)
```

  Внешний вид слово `query` указывает, что это выражение запроса, тип вычисления выражения, которое создает коллекцию результаты, аналогичные запроса обычной базой данных. При наведении на запрос, вы увидите, что он является экземпляром [класс Linq.QueryBuilder](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.querybuilder-class-%5bfsharp%5d), тип, который определяет query-вычислительное выражение. При наведении `query1`, вы увидите, что он является экземпляром `System.Linq.IQueryable`. Как видно из имени, `System.Linq.IQueryable` представляет данные, которые могут запрашиваться не является результатом запроса. Запрос регулируется отложенные вычисления, что означает, что база данных доступна только запросы при вычислении запроса. Последняя строка передает запрос с помощью `Seq.iter`. Запросы перечисляемую и может выполнить итерацию как последовательности. Дополнительные сведения см. в разделе [выражения запросов](../../language-reference/query-expressions.md).

2. Теперь добавьте оператор запроса в запрос. Существует несколько операторов запроса, что можно использовать для создания более сложных запросов. В этом примере также показано, можно исключить переменной запроса и вместо этого используйте оператор конвейера.

  ```fsharp
   query {
     for row in db.Table1 do
     where (row.TestData1 > 2)
     select row
   } |> Seq.iter (fun row -> printfn "%d %s" row.TestData1 row.Name)
```

3. Добавьте более сложный запрос с соединение двух таблиц.

  ```fsharp
   query {
     for row1 in db.Table1 do
     join row2 in db.Table2 on (row1.Id = row2.Id)
     select (row1, row2)
   } |> Seq.iteri (fun index (row1, row2) ->
                   if (index = 0) then printfn "Table1.Id TestData1 TestData2 Name Table2.Id TestData1 TestData2 Name"
                   printfn "%d %d %f %s %d %d %f %s" row1.Id row1.TestData1 row1.TestData2 row1.Name
                     row2.Id (row2.TestData1.GetValueOrDefault()) (row2.TestData2.GetValueOrDefault()) row2.Name)
```

4. Обычно в реальном коде параметров в запросе являются значения или переменные, константы не во время компиляции. Добавьте следующий код, который создает оболочку для запроса в функции, которая принимает параметр, а затем вызывает эту функцию со значением 10.

  ```fsharp
   let findData param =
     query {
       for row in db.Table1 do
       where (row.TestData1 = param)
       select row
     }

   findData 10 |> Seq.iter (fun row -> printfn "Found row: %d %d %f %s" row.Id row.TestData1 row.TestData2 row.Name)
```

## <a name="working-with-nullable-fields"></a>Работа с полями, допускающие значение NULL
В базах данных поля часто разрешены значения null. В системе типов .NET нельзя использовать обычные числовыми типами данных для данных, допускающий значения NULL, так как эти типы не имеют возможности значение null. Таким образом, эти значения представлены экземплярами `System.Nullable` типа. Вместо обращения к значения таких полей непосредственно с именем поля, необходимо выполнить некоторые дополнительные действия. Можно использовать `System.Nullable.Value` свойство для доступа к значению базового типа nullable. `System.Nullable.Value` Свойство вызывает исключение, если объект имеет значение null, вместо того чтобы использовать значение. Можно использовать `System.Nullable.HasValue` логический метод, чтобы определить, если значение существует, или используйте `System.Nullable.GetValueOrDefault()` для убедитесь, что фактическое значение во всех случаях. Если вы используете `System.Nullable.GetValueOrDefault()` и в базе данных имеется значение null, то он заменяется со значением, такие как пустую строку для строковых типов, 0 для целочисленных типов или 0,0 чисел с плавающей запятой.

Если необходим для выполнения проверок на равенство или сравнения на значения NULL в `where` предложения в запросе можно использовать операторы допускает значения NULL, в [модуль Linq.NullableOperators](https://msdn.microsoft.com/visualfsharpdocs/conceptual/linq.nullableoperators-module-%5bfsharp%5d). Они похожи на операторы сравнения, регулярные `=`, `>`, `<=`, и т. д., за исключением того, знак вопроса появляется слева или справа от оператора в которых значения NULL. Например, оператор `>?` больше-оператор со значением, допускающие значения NULL в правой части. Эти операторы работают в том случае, если один из операндов выражения принимает значение null, то выражение принимает значение `false`. В `where` предложение, обычно это означает что строки, содержащие поля со значением null не выбран и не возвращается в результатах запроса.


#### <a name="to-work-with-nullable-fields"></a>Для работы с полями, допускающие значение NULL

Ниже показана работа со значениями NULL; предполагается, что **TestData1** является целочисленным полем, допускающий значения NULL.

```fsharp
query {
  for row in db.Table2 do
  where (row.TestData1.HasValue && row.TestData1.Value > 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" row.TestData1.Value row.Name)

query {
  for row in db.Table2 do
  // Use a nullable operator ?>
  where (row.TestData1 ?> 2)
  select row
} |> Seq.iter (fun row -> printfn "%d %s" (row.TestData1.GetValueOrDefault()) row.Name)
```

## <a name="calling-a-stored-procedure"></a>Вызов хранимой процедуры
Все хранимые процедуры в базе данных может вызываться из F #. Необходимо задать параметр static `StoredProcedures` для `true` в реализации поставщика типа. Поставщик типов `SqlDataConnection` содержит несколько статических методов, которые можно использовать для настройки созданные типы. Полное описание из них см. в разделе [поставщика типов SqlDataConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d). Метод в типе контекста данных создается для каждой хранимой процедуры.


#### <a name="to-call-a-stored-procedure"></a>Действия для вызова хранимой процедуры

Если хранимые процедуры принимает параметры, допускающие значения NULL, необходимо передать соответствующей `System.Nullable` значение. Возвращаемое значение метода хранимой процедуры, возвращающей скалярное или таблицы является `System.Data.Linq.ISingleResult`, который содержит свойства, которые позволяют получить доступ к возвращаемых данных. Тип аргумента для `System.Data.Linq.ISingleResult` также является одним из типов, создаваемых поставщиком типа и зависит от определенной процедуры. Для хранимой процедуры с именем `Procedure1`, тип — `Procedure1Result`. Тип `Procedure1Result` содержит имена столбцов в таблице результатов или для хранимой процедуры, возвращающей скалярное значение, он представляет возвращаемое значение.

В следующем коде предполагается, что является процедурой `Procedure1` в базе данных, которая принимает два целых числа допускает значения NULL, как параметры, выполняют запрос, который возвращает столбец с именем `TestData1`и возвращает целое число.

```fsharp
type schema = SqlDataConnection<"Data Source=MYSERVER\INSTANCE;Initial Catalog=MyDatabase;Integrated Security=SSPI;", StoredProcedures = true>

let testdb = schema.GetDataContext()

let nullable value = new System.Nullable<_>(value)

let callProcedure1 a b =
  let results = testdb.Procedure1(nullable a, nullable b)
  for result in results do
    printfn "%d" (result.TestData1.GetValueOrDefault())
  results.ReturnValue :?> int

printfn "Return Value: %d" (callProcedure1 10 20)
```

## <a name="updating-the-database"></a>Обновление базы данных
Тип LINQ DataContext содержит методы, которые упрощают процесс для выполнения обновления с поддержкой транзакций базы данных полностью введенного образом с помощью создаваемых типов.


#### <a name="to-update-the-database"></a>Обновление базы данных

1. В следующем коде несколько строки добавляются в базу данных. При добавлении строки можно использовать `System.Data.Linq.Table.InsertOnSubmit()` для указания новой строки для добавления. При вставке нескольких строк, следует помещать их в коллекцию и вызова `System.Data.Linq.Table.InsertAllOnSubmit(System.Collections.Generic.IEnumerable)`. При вызове любого из этих методов, базы данных не изменяется немедленно. Необходимо вызвать метод `System.Data.Linq.DataContext.SubmitChanges` для фактического применения изменений. По умолчанию все действия выполняются прежде чем вызывать `System.Data.Linq.DataContext.SubmitChanges` неявным образом является частью той же транзакции.

 ```fsharp
   let newRecord = new dbSchema.ServiceTypes.Table1(Id = 100,
                                                    TestData1 = 35, 
                                                    TestData2 = 2.0,
                                                    Name = "Testing123")

   let newValues =
     [ for i in [1 .. 10] ->
       new dbSchema.ServiceTypes.Table3(Id = 700 + i,
         Name = "Testing" + i.ToString(),
         Data = i) ]

   // Insert the new data into the database.
   db.Table1.InsertOnSubmit(newRecord)
   db.Table3.InsertAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully inserted new rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

2. Теперь очистите строки, вызвав операцию удаления.

  ```fsharp
   // Now delete what was added.
   db.Table1.DeleteOnSubmit(newRecord)
   db.Table3.DeleteAllOnSubmit(newValues)

   try
     db.DataContext.SubmitChanges()
     printfn "Successfully deleted all pending rows."
   with
   | exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="executing-transact-sql-code"></a>Выполнение кода Transact-SQL
Можно также указать Transact-SQL непосредственно с помощью `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` метод `DataContext` класса.


#### <a name="to-execute-custom-sql-commands"></a>Для выполнения пользовательских команд SQL

Ниже показано, как для отправки команд SQL для вставки записи в таблицу и удалить запись из таблицы.

```fsharp
try
  db.DataContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'Testing', 55)") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message

try //AND Name = 'Testing' AND Data = 55
  db.DataContext.ExecuteCommand("DELETE FROM Table3 WHERE Id = 102 ") |> ignore
with
| exn -> printfn "Exception:\n%s" exn.Message
```

## <a name="using-the-full-data-context"></a>Полный контекст данных с помощью
В предыдущих примерах `GetDataContext` метод, использованный для получения, называемый *упрощенным контекстом данных* для схемы базы данных. Для использования при построении запросов, так как нет всех членов, доступных проще упрощенным контекстом данных. Таким образом при просмотре свойств в IntelliSense, можно сосредоточиться на структуру базы данных, таких как таблицы и хранимые процедуры. Однако имеется ограничение для действий, выполняемых с упрощенным контекстом данных. Полный контекст данных, обеспечивает возможность выполнения других действий. также доступен этот файл находится в `ServiceTypes` и имеет имя *DataContext* статического параметра, если он указан. Если оно не было указано, имя типа контекста данных формируется автоматически на основе других данных SqlMetal.exe. Полный контекст данных наследует от `System.Data.Linq.DataContext` и предоставляет доступ к членам базового класса, включая ссылки на типы данных ADO.NET, такие как `Connection` объектов, методов, таких как `System.Data.Linq.DataContext.ExecuteCommand(System.String,System.Object[])` и `System.Data.Linq.DataContext.ExecuteQuery(System.String,System.Object[])` , можно использовать для написания запросов в SQL а также средства для работы с транзакциями, явным образом.


#### <a name="to-use-the-full-data-context"></a>Чтобы использовать полный контекст данных

В следующем коде показано получение объекта контекста полного набора данных и использовать его для выполнения команд непосредственно к базе данных. В этом случае две команды выполняются в рамках одной транзакции.

```fsharp
let dbConnection = testdb.Connection
let fullContext = new dbSchema.ServiceTypes.MyDatabase(dbConnection)

dbConnection.Open()

let transaction = dbConnection.BeginTransaction()
fullContext.Transaction <- transaction

try
  let result1 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (102, 'A', 55)")
  printfn "ExecuteCommand Result: %d" result1
  let result2 = fullContext.ExecuteCommand("INSERT INTO Table3 (Id, Name, Data) VALUES (103, 'B', -2)")
  printfn "ExecuteCommand Result: %d" result2
  if (result1 <> 1 || result2 <> 1) then
    transaction.Rollback()
    printfn "Rolled back creation of two new rows."
  else
    transaction.Commit()
  printfn "Successfully committed two new rows."
with
| exn ->
  transaction.Rollback()
  printfn "Rolled back creation of two new rows due to exception:\n%s" exn.Message

dbConnection.Close()
```

## <a name="deleting-data"></a>Удаление данных
Этот шаг показывает, как удалить строки из таблицы данных.


#### <a name="to-delete-rows-from-the-database"></a>Для удаления строк из базы данных

Теперь очистки любого добавлено строк путем написания функции, которая удаляет строки из указанной таблицы, экземпляр `System.Data.Linq.Table` класса. Затем написать запрос для нахождения всех строк, которые требуется удалить и передать результаты запроса в `deleteRows` функции. Этот код использует возможности предоставления частичного применения аргументов функции.

```fsharp
let deleteRowsFrom (table:Table<_>) rows =
  table.DeleteAllOnSubmit(rows)

query {
  for rows in db.Table3 do
  where (rows.Id > 10)
  select rows
} |> deleteRowsFrom db.Table3

db.DataContext.SubmitChanges()
printfn "Successfully deleted rows with Id greater than 10 in Table3."
```

## <a name="creating-a-test-database"></a>Создание тестовой базой данных.
В этом разделе показано, как настроить тестовую базу данных для использования в этом пошаговом руководстве.

Обратите внимание, что если база данных каким-либо образом изменены, необходимо будет сбросить тип поставщика. Чтобы сбросить тип поставщика, перестроения или очистки проект, который содержит тип поставщика.


#### <a name="to-create-the-test-database"></a>Создание тестовой базы данных

1. В **обозревателя серверов**, откройте контекстное меню для **подключения к данным** узел и выберите **добавить подключение**. **Добавить подключение** откроется диалоговое окно.

2. В **имя сервера** поле, укажите имя экземпляра SQL Server, имеют административный доступ к или если нет доступа к серверу, укажите (localdb\v11. 0). SQL Express LocalDB предоставляет упрощенный сервер базы данных для разработки и тестирования на компьютере. Создается новый узел в **обозревателя серверов** под **подключения к данным**. Дополнительные сведения о LocalDB см. в разделе [Пошаговое руководство: Создание локального файла базы данных в Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).

3. Откройте контекстное меню для нового узла подключения и выберите **новый запрос**.

4. Скопируйте следующий скрипт SQL и вставьте его в редакторе запросов выберите **Execute** на панели инструментов или нажмите сочетание клавиш Ctrl + Shift + E.

```sql
SET ANSI_NULLS ON
GO
SET QUOTED_IDENTIFIER ON
GO

USE [master];
GO

IF EXISTS (SELECT * FROM sys.databases WHERE name = 'MyDatabase')
  DROP DATABASE MyDatabase;
GO

-- Create the MyDatabase database.
CREATE DATABASE MyDatabase;
GO

-- Specify a simple recovery model 
-- to keep the log growth to a minimum.
ALTER DATABASE MyDatabase 
SET RECOVERY SIMPLE;
GO

USE MyDatabase;
GO

-- Create the Table1 table.
CREATE TABLE [dbo].[Table1] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NOT NULL,
  [TestData2] FLOAT (53) NOT NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);

-- Create the Table2 table.
CREATE TABLE [dbo].[Table2] (
  [Id]        INT        NOT NULL,
  [TestData1] INT        NULL,
  [TestData2] FLOAT (53) NULL,
  [Name]      NTEXT      NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
);


-- Create the Table3 table.
CREATE TABLE [dbo].[Table3] (
  [Id]   INT           NOT NULL,
  [Name] NVARCHAR (50) NOT NULL,
  [Data] INT           NOT NULL,
  PRIMARY KEY CLUSTERED ([Id] ASC)
  );
GO

CREATE PROCEDURE [dbo].[Procedure1]
  @param1 int = 0,
  @param2 int
AS
SELECT TestData1 FROM Table1
RETURN 0
GO

USE MyDatabase

-- Insert data into the Table1 table.
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table1 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');

-- Insert data into the Table2 table.
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(1, 10, 5.5, 'Testing1');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(2, 20, -1.2, 'Testing2');
INSERT INTO Table2 (Id, TestData1, TestData2, Name)
  VALUES(3, NULL, NULL, 'Testing3');

-- Insert data into the Table3 table.
INSERT INTO Table3 (Id, Name, Data)
  VALUES (1, 'Testing1', 10);
INSERT INTO Table3 (Id, Name, Data)
  VALUES (2, 'Testing2', 100);
```


## <a name="see-also"></a>См. также
[Поставщики типов](index.md)

[Поставщик типов SqlDataConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqldataconnection-type-provider-%5bfsharp%5d)

[Пошаговое руководство: Создание типов F # из DBML-файла](generating-fsharp-types-from-dbml.md)

[Выражения запросов](../../language-reference/query-expressions.md)

[LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)

[SqlMetal.exe &#40;средство создания кода&#41;](https://msdn.microsoft.com/library/bb386987)
