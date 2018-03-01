---
title: "Пошаговое руководство. Создание типов F# из файла схемы EDMX (F#)"
description: "Узнайте, как создание типов F # для данных, представленных в модели данных сущности (EDM) в F # 3.0, где схема задана в EDMX-файл."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 81adb2eb-625f-4ad8-aeaa-8f672a6d79a2
ms.openlocfilehash: 901457dce358f768b4f4c980703e09f6c744918e
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/28/2018
---
# <a name="walkthrough-generating-f-types-from-an-edmx-schema-file"></a>Пошаговое руководство. Создание типов F# из файла схемы EDMX

> [!NOTE]
В этом руководстве, была написана для F # 3.0 и будут обновлены.  Актуальные сведения о кроссплатформенных поставщиках типов см. в описании [FSharp.Data](https://fsharp.github.io/FSharp.Data/).

> [!NOTE]
Справочные ссылки API, вы перейдете MSDN.  Работа над справочником по API docs.microsoft.com не завершена.

В этом пошаговом руководстве для F# 3.0 показано создание типов для данных, представляемых моделью EDM, схема для которой определена в EDMX-файле. В этом пошаговом руководстве также описано использование поставщика типов EdmxFile. Сначала рассмотрим, не является ли поставщик типов SqlEntityConnection более подходящим поставщиком. Поставщик типов SqlEntityConnection оптимально подходит для сценариев, где имеется база данных реального времени, к которой можно подключаться на этапе разработки проекта, и у вас нет возражений против указания строки подключения во время компиляции. Однако этот поставщик типов предоставляет меньше функциональных возможностей базы данных по сравнению с поставщиком типов EdmxFile. Кроме того, при отсутствии подключения к базе данных реального времени для проекта базы данных, использующего модель EDM, можно использовать EDMX-файл, чтобы реализовать код для базы данных. При использовании поставщика типов EdmxFile компилятор F# выполняет программу EdmGen.exe для создания типов, которые он предоставляет.

В этом пошаговом руководстве рассмотрены перечисленные ниже задачи, которые необходимо выполнить в указанном порядке.


- Создание EDMX-файла
<br />

- Создание проекта
<br />

- Поиск или создание строки подключения модели EDM
<br />

- Настройка поставщика типов
<br />

- Запрос данных
<br />

- Вызов хранимой процедуры
<br />


## <a name="prerequisites"></a>Предварительные требования

## <a name="creating-an-edmx-file"></a>Создание EDMX-файла
Если EDMX-файл уже есть, этот шаг можно пропустить.


#### <a name="to-create-an-edmx-file"></a>Создание EDMX-файла

- Если у вас еще нет EDMX-файла, можно выполнить действия, в конце этого пошагового руководства в разделе [Настройка модели EDM](generating-fsharp-types-from-edmx.md#configuring-the-entity-data-model).
<br />

## <a name="creating-the-project"></a>Создание проекта
На этом шаге создается проект и добавляются необходимые ссылки на него для использования поставщика типов EDMX.


#### <a name="to-create-and-set-up-an-f-project"></a>Действия для создания и настройки проекта F#

1. Закройте предыдущий проект, создайте другой проект и назовите его SchoolEDM.
<br />

2. В **обозревателе решений**, откройте контекстное меню для **ссылки**и нажмите кнопку **добавить ссылку**.
<br />

3. В **сборки** области, выберите **Framework** узла.
<br />

4. В списке доступных сборок выберите **System.Data.Entity** и **System.Data.Linq** сборки, а затем выберите **добавить** кнопку, чтобы добавить ссылки на эти сборки в проект.
<br />

5. В **сборки** выберите **расширения** узла.
<br />

6. В списке доступных расширений добавьте ссылку на сборку FSharp.Data.TypeProviders.
<br />

7. Добавьте представленный ниже код, чтобы открыть соответствующие пространства имен.
<br />

```fsharp
open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

## <a name="finding-or-creating-the-connection-string-for-the-entity-data-model"></a>Поиск или создание строки подключения для модели EDM
Строка подключения для модели EDM (строка подключения EDMX) содержит не только строку подключения для поставщика базы данных, но и дополнительные сведения. Например, строка подключения EDMX для простой базы данных SQL Server подобна следующему коду.

```fsharp
let edmConnectionString = "metadata=res://*/;provider=System.Data.SqlClient;Provider Connection String='Server=SERVER\Instance;Initial Catalog=DatabaseName;Integrated Security=SSPI;'"
```

Дополнительные сведения о строках подключения EDMX см. в разделе [строки подключения](../../../../docs/framework/data/adonet/connection-strings-and-configuration-files.md).


#### <a name="to-find-or-create-the-connection-string-for-the-entity-data-model"></a>Действия для поиска или создания строки подключения для модели EDM

1. Строки подключения EDMX трудно создавать вручную, поэтому можно сэкономить время, создавая их программно. Если строка подключения EDMX известна, можно пропустить этот шаг и просто использовать эту строку на следующем шаге. Если строка неизвестна, используйте показанный ниже код для создания строки подключения EDMX из строки подключения к базе данных, которую необходимо предоставить.
<br />

```fsharp
open System
open System.Data
open System.Data.SqlClient
open System.Data.EntityClient
open System.Data.Metadata.Edm

let getEDMConnection(dbConnectionString) =
  let dbConnection = new SqlConnection(dbConnectionString)
  let resourceArray = [| "res://*/" |]
  let assemblyList = [| System.Reflection.Assembly.GetCallingAssembly() |]
  let metaData = MetadataWorkspace(resourceArray, assemblyList)
  new EntityConnection(metaData, dbConnection)
```

## <a name="configuring-the-type-provider"></a>Настройка поставщика типов
На этом шаге создается и настраивается поставщик типов со строкой подключения EDMX, а также создаются типы для схемы, определенной в EMDX-файле.


#### <a name="to-configure-the-type-provider-and-generate-types"></a>Настройка поставщика типов и создание типов

1. Скопируйте EDMX-файл, созданный на первом шаге данного пошагового руководства, в папку проекта.
<br />

2. Откройте контекстное меню узла проекта в проекте F #, выберите команду **Добавление существующего элемента**, а затем выберите EDMX-файл, чтобы добавить его в проект.
<br />

3. Введите представленный ниже код, чтобы активировать поставщик типов для EDMX-файла. Замените *сервера*\*экземпляр * с именем сервера, на котором работает SQL Server и имя экземпляра и используйте имя EDMX-файла с первым шагом в этом пошаговом руководстве.
<br />

```fsharp
type edmx = EdmxFile<"Model1.edmx", ResolutionFolder = @"<path-tofolder-that-containsyour.edmx-file>">

use edmConnection =
  getEDMConnection("Data Source=SERVER\instance;Initial Catalog=School;Integrated Security=true;")
use context = new edmx.SchoolModel.SchoolEntities(edmConnection)
```

## <a name="querying-the-data"></a>Запрос данных
На этом шаге используются выражения запросов F# для запроса к базе данных.


#### <a name="to-query-the-data"></a>Действия для запроса данных

- Введите представленный ниже код, чтобы запросить данные в модели EDM.
<br />

```fsharp
query { 
  for course in context.Courses do
  select course 
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.Person do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results
query { 
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="calling-a-stored-procedure"></a>Вызов хранимой процедуры
Хранимые процедуры можно вызывать с помощью поставщика типов EDMX. В следующей процедуре базы данных School содержит хранимую процедуру, **UpdatePerson**, которая обновляет запись, используя новые значения для столбцов. Эту хранимую процедуру можно использовать, поскольку она предоставляется в качестве метода типа DataContext.


#### <a name="to-call-a-stored-procedure"></a>Действия для вызова хранимой процедуры

- Добавьте к записям обновления следующий код.
<br />

```fsharp
// Call a stored procedure.
let nullable value = new System.Nullable<_>(value)

// Assume now that you must correct someone's hire date.
// Throw an exception if more than one matching person is found.
let changeHireDate(lastName, firstName, hireDate) =

  query { 
    for person in context.People do
    where (person.LastName = lastName &&
           person.FirstName = firstName)
    exactlyOne 
  } |> (fun person ->
            context.UpdatePerson(nullable person.PersonID, person.LastName, person.FirstName, nullable hireDate, person.EnrollmentDate))

changeHireDate("Abercrombie", "Kim", DateTime.Parse("1/12/1998"))
|> printfn "Result: %d"
```

В случае успеха результатом будет значение 1. Обратите внимание, что **exactlyOne** используется в выражении запроса, чтобы убедиться, что только один результат возвращен; в противном случае, создается исключение. Кроме того, для упрощения работы со значениями NULL можно использовать простой **nullable** функции, который определен в этом коде для создания значения, допускающие значения NULL из обычного значения.

<br />

## <a name="configuring-the-entity-data-model"></a>Настройка модели EDM
Эту процедуру следует выполнить, только если необходимо знать, как создать полную модель EDM из базы данных при отсутствии базы данных для тестирования.


#### <a name="to-configure-the-entity-data-model"></a>Действия для настройки модели EDM

1. В строке меню выберите **SQL**, **редактора Transact-SQL**, **новый запрос** для создания базы данных. В случае получения запроса укажите сервер и экземпляр базы данных.
<br />

2. Скопируйте и вставьте содержимое скрипта базы данных, который создает базу данных студентов, как описано в [документации по Entity Framework](https://msdn.microsoft.com/data/JJ614587.aspx) в центр разработчиков данных.
<br />

3. Запустите скрипт SQL, выбрав кнопку панели инструментов с треугольником, или нажмите клавиши Ctrl + Q.
<br />

4. В **обозревателя серверов**, откройте контекстное меню для **подключения к данным**, выберите **добавить подключение**, а затем введите имя сервера базы данных, имя экземпляра и базы данных School.
<br />

5. Создайте проект C# или консольное приложение Visual Basic, откройте ее контекстное меню, выберите **Добавление нового элемента**, а затем выберите **ADO.NET Entity Data Model**.
<br />  Откроется мастер моделей EDM. С помощью этого мастера можно выбрать способ создания модели EDM.
<br />

6. В разделе **Выбор содержимого модели**выберите **создать из базы данных** флажок.
<br />

7. На следующей странице выберите только что созданную базу данных School в качестве подключения к данным.
<br />  Это подключение должно быть подобно  **&lt;servername&gt;.&lt; instancename&gt;. School.dbo**.
<br />

8. Скопируйте строку подключения сущности в буфер обмена, поскольку эта строка может пригодиться в будущем.
<br />

9. Убедитесь, что флажок, чтобы сохранить строку подключения сущности в **App.Config** файл выбран и запишите значение строки в текстовом поле, которое поможет найти строку подключения позже, при необходимости.
<br />

10. На следующей странице выберите **таблиц** и **хранимые процедуры и функции**.
<br />  При выборе этих узлов верхнего уровня выбираются все таблицы, хранимые процедуры и функции. При необходимости можно также выбрать их отдельно.
<br />

11. Убедитесь, что установлены флажки для других параметров.
<br />  Первый **единственном или множественном числе формировать имена объектов** флажок указывает, следует ли изменить форм единственного числа для во множественном числе, чтобы соответствовать соглашениям по именованию объектов, представляющих таблицы базы данных. **Включить столбцы внешних ключей в модель** флажок определяет, следует ли включать поля, для которых предназначен для соединения с другими полями в типах объектов, созданных для схемы базы данных. Третий флажок указывает, следует ли включать в модель хранимые процедуры и функции.
<br />

12. Выберите **Готово** кнопку, чтобы создать EDMX-файл, содержащий модель EDM, основанный на базу данных School.
<br />  Файл, **Model1.edmx**, добавляется в проект, и появляется диаграмма базы данных.
<br />

13. В строке меню выберите **представление**, **другие окна**, **браузер моделей EDM** для просмотра всех сведений о модели или **сведения о сопоставлении данных модели EDM**  чтобы открыть окно, в котором показано, как созданная модель объектов сопоставляется таблицам базы данных и столбцов.
<br />


## <a name="next-steps"></a>Следующие шаги
Изучение других запросов, просмотрев доступны операторы, перечисленные в [выражения запросов](../../language-reference/query-expressions.md).


## <a name="see-also"></a>См. также
[Поставщики типов](index.md)

[Поставщик типов EdmxFile](https://msdn.microsoft.com/visualfsharpdocs/conceptual/edmxfile-type-provider-%5bfsharp%5d)

[Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов и сущностей](accessing-a-sql-database-entities.md)

[Entity Framework](https://msdn.microsoft.com/data/ef)

[Общие сведения о файлах .edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[Генератор модели EDM &#40; EdmGen.exe &#41;](https://msdn.microsoft.com/library/bb387165)

