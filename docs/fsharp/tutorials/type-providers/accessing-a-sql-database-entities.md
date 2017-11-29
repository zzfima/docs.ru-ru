---
title: "Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов и сущностей (F#)"
description: "Узнайте, как получить доступ к типизированным данным для базы данных SQL в зависимости от модели EDM ADO.NET в F # 3.0."
keywords: "visual f#, f#, функциональное программирование"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: dc82a932-5401-4d19-9fb3-92c50d8db514
ms.openlocfilehash: 770d405921758eeb7e8d7ea98b95c29c99631475
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/18/2017
---
# <a name="walkthrough-accessing-a-sql-database-by-using-type-providers-and-entities"></a>Пошаговое руководство. Доступ к базе данных SQL с помощью поставщиков типов и сущностей

> [!NOTE]
В этом руководстве, была написана для F # 3.0 и будут обновлены.  Актуальные сведения о кроссплатформенных поставщиках типов см. в описании [FSharp.Data](http://fsharp.github.io/FSharp.Data/).

> [!NOTE]
Справочные ссылки API, вы перейдете MSDN.  Работа над справочником по API docs.microsoft.com не завершена.

В этом пошаговом руководстве для F# 3.0 показывается, как получить доступ к типизированным данным для базы данных SQL на основе модели EDM ADO.NET. В нем также рассматриваются настройка поставщика типов `SqlEntityConnection` языка F# для использования с базой данных SQL, правила написания запросов к данным, вызов хранимых процедур в базе данных, а также использование некоторых типов и методов ADO.NET Entity Framework для обновления базы данных.

В этом пошаговом руководстве описываются перечисленные ниже задачи, которые необходимо выполнить в указанном порядке.


- Создание базы данных School
<br />

- Создание и настройка проекта F#
<br />

- Настройка поставщика типов и подключение к модели EDM
<br />

- Запрос к базе данных
<br />

- Обновление базы данных
<br />


## <a name="prerequisites"></a>Предварительные требования
Необходимо иметь доступ к серверу с работающим программным обеспечением SQL Server, где можно создать базу данных для выполнения указанных ниже действий.

## <a name="create-the-school-database"></a>Создание базы данных School
Базу данных School можно создать на любом сервере с работающим программным обеспечением SQL Server, к которому имеется административный доступ. Можно также использовать LocalDB.


#### <a name="to-create-the-school-database"></a>Действия для создания базы данных School

1. В **обозревателя серверов**, откройте контекстное меню для **подключения к данным** узел и выберите **добавить подключение**.
<br />  **Добавить подключение** откроется диалоговое окно.
<br />

2. В **имя сервера** поле, укажите имя экземпляра SQL Server, к которому имеется административный доступ или укажите (localdb\v11. 0), при отсутствии доступа к серверу.
<br />  SQL Server Express LocalDB предоставляет упрощенный сервер базы данных для разработки и тестирования на компьютере. Дополнительные сведения о LocalDB см. в разделе [Пошаговое руководство: Создание локального файла базы данных в Visual Studio](https://msdn.microsoft.com/library/ms233763.aspx).
<br />  Создается новый узел в **обозревателя серверов** под **подключения к данным**.
<br />

3. Откройте контекстное меню для нового узла подключения и выберите **новый запрос**.
<br />

4. Откройте [Создание образца базы данных School](http://go.microsoft.com/fwlink/?LinkID=237278) в веб-сайте Майкрософт, а затем скопировать и вставить скрипт базы данных, создает студента базу данных в окно редактора.
<br />


## <a name="BKMK_CreateConfigFSProj"> </a>

## <a name="create-and-configure-an-f-project"></a>Создание и настройка проекта F#
На данном шаге создается проект и он настраивается на использование поставщика типов.


#### <a name="to-create-and-configure-an-f-project"></a>Действия для создания и настройки проекта F#

1. Закройте предыдущий проект, создайте другой проект и назовите его **SchoolEDM**.
<br />

2. В **обозревателе решений**, откройте контекстное меню для **ссылки**и нажмите кнопку **добавить ссылку**.
<br />

3. Выберите **Framework** узел, а затем в **Framework** выберите **System.Data**, **System.Data.Entity**и **System.Data.Linq**.
<br />

4. Выберите **расширения** узел, добавьте ссылку на [FSharp.Data.TypeProviders](https://msdn.microsoft.com/library/a858f859-047a-44ab-945b-8731d7a0e6e3) сборки и нажмите кнопку **ОК** кнопку, чтобы закрыть диалоговое окно.
<br />

5. Добавьте представленный ниже код для определения внутреннего модуля и откройте соответствующие пространства имен. Поставщик типов может вводить типы только в закрытое или внутреннее пространство имен.
<br />

```fsharp
module internal SchoolEDM

open System.Data.Linq
open System.Data.Entity
open Microsoft.FSharp.Data.TypeProviders
```

6. Выполнение кода в этом пошаговом руководстве в интерактивном режиме в виде скрипта, а не как компилированной программы, откройте контекстное меню узла проекта, выберите **добавить новый элемент**, добавьте файл скрипта F # и затем добавьте код в каждом шаге в скрипт. Для загрузки ссылок на сборку добавьте следующие строки.
<br />

```fsharp
#r "System.Data.Entity.dll"
#r "FSharp.Data.TypeProviders.dll"
#r "System.Data.Linq.dll"
```

7. Выделите каждый блок кода при его добавлении и нажмите клавиши Alt + ВВОД для запуска в F# Interactive.
<br />

## <a name="configure-the-type-provider-and-connect-to-the-entity-data-model"></a>Настройка поставщика типов и подключение к модели EDM
На этом шаге настраивается поставщик типов с подключением к данным и производится получение контекста данных, позволяющего работать с ними.


#### <a name="to-configure-the-type-provider-and-connect-to-the-entity-data-model"></a>Действия для настройки поставщика типов и подключения к модели EDM

1. Введите представленный ниже код, чтобы настроить поставщик типов `SqlEntityConnection`, формирующий типы F# на основе ранее созданной модели EDM. Вместо полной строки подключения EDMX используйте только строку подключения SQL.
<br />

```fsharp
type private EntityConnection = SqlEntityConnection<ConnectionString="Server=SERVER\InstanceName;Initial Catalog=School;Integrated Security=SSPI;MultipleActiveResultSets=true",Pluralize = true>
```

  Это действие настраивает поставщик типов с созданным ранее подключением к базе данных. Свойство `MultipleActiveResultSets` необходимо при использовании ADO.NET Entity Framework, поскольку допускает асинхронное выполнение нескольких команд для базы данных в одном подключении. Такое может часто происходить в коде ADO.NET Entity Framework. Дополнительные сведения см. в разделе [Несколько активных результирующих наборов (MARS)](/sql/relational-databases/native-client/features/using-multiple-active-result-sets-mars).
<br />

2. Получите контекст данных, который представляет собой объект, содержащий таблицы базы данных в качестве свойств и хранимые процедуры и функции базы данных в качестве методов.
<br />

```fsharp
let context = EntityConnection.GetDataContext()
```

## <a name="querying-the-database"></a>Запрос к базе данных
На этом шаге используются выражения запросов F# для выполнения различных запросов к базе данных.


#### <a name="to-query-the-data"></a>Действия для запроса данных

- Введите представленный ниже код для запроса данных из модели EDM. Обратите внимание, что Pluralize = true изменяет таблицы базы данных Course на Courses и Person на People.
<br />

```fsharp
query { 
  for course in context.Courses do
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

query { 
  for person in context.People do
  select person 
} |> Seq.iter (fun person -> printfn "%s %s" person.FirstName person.LastName)

// Add a where clause to filter results.
query {
  for course in context.Courses do
  where (course.DepartmentID = 1)
  select course
} |> Seq.iter (fun course -> printfn "%s" course.Title)

// Join two tables.
query { 
  for course in context.Courses do
  join dept in context.Departments on (course.DepartmentID = dept.DepartmentID)
  select (course, dept.Name) 
} |> Seq.iter (fun (course, deptName) -> printfn "%s %s" course.Title deptName)
```

## <a name="updating-the-database"></a>Обновление базы данных
Для обновления базы данных можно использовать классы и методы Entity Framework. С поставщиком типов SQLEntityConnection можно использовать два типа контекста данных. Первый тип `ServiceTypes.SimpleDataContextTypes.EntityContainer` является упрощенным контекстом данных, который содержит только предоставленные свойства, представляющие таблицы и столбцы базы данных. Второй тип, полный контекст данных, — это экземпляр класса Entity Framework `System.Data.Objects.ObjectContext`, содержащий метод `System.Data.Objects.ObjectContext.AddObject(System.String,System.Object)` для добавления строк в базу данных. Entity Framework распознает таблицы и отношения между ними, обеспечивая тем самым согласованность базы данных.


#### <a name="to-update-the-database"></a>Обновление базы данных

1. Добавьте в программу представленный ниже код. В этом примере добавляются два объекта с отношением между ними, а также инструктор и распределение аудиторий. Таблица `OfficeAssignments` содержит столбец `InstructorID`, в котором имеется ссылка на столбец `PersonID` в таблице `Person`.
<br />

```fsharp
// The full data context
let fullContext = context.DataContext

// A helper function.
let nullable value = new System.Nullable<_>(value)

let addInstructor(lastName, firstName, hireDate, office) =
  let hireDate = DateTime.Parse(hireDate)
  let newPerson = new EntityConnection.ServiceTypes.Person(LastName = lastName,
                                                           FirstName = firstName,
                                                           HireDate = nullable hireDate)
  fullContext.AddObject("People", newPerson)

  let newOffice = new EntityConnection.ServiceTypes.OfficeAssignment(Location = office)

  fullContext.AddObject("OfficeAssignments", newOffice)
  fullContext.CommandTimeout <- nullable 1000
  fullContext.SaveChanges() |> printfn "Saved changes: %d object(s) modified."

addInstructor("Parker", "Darren", "1/1/1998", "41/3720")
```

До вызова метода `System.Data.Objects.ObjectContext.SaveChanges` в базе данных ничего не изменяется.
<br />

2. Теперь восстановите предшествующее состояние базы данных, удалив добавленные объекты.
<br />

```fsharp
let deleteInstructor(lastName, firstName) =
  query {
    for person in context.People do
    where (person.FirstName = firstName &&
           person.LastName = lastName)
    select person
  } |> Seq.iter (fun person->
                    query {
                      for officeAssignment in context.OfficeAssignments do
                      where (officeAssignment.Person.PersonID = person.PersonID)
                      select officeAssignment
                    } |> Seq.iter (fun officeAssignment -> fullContext.DeleteObject(officeAssignment))

                    fullContext.DeleteObject(person))

  // The call to SaveChanges should be outside of any iteration on the queries.
  fullContext.SaveChanges() |> printfn "Saved changed: %d object(s) modified."

deleteInstructor("Parker", "Darren")
```

>[!WARNING] 
При использовании выражения запроса необходимо помнить, что такой запрос подвержен отложенным вычислениям. Поэтому база данных остается открытой для чтения при выполнении всех цепочек вычислений, например блоков лямбда-выражений после каждого выражения запроса. Любая операция базы данных, явно или неявно использующая транзакцию, должна произойти после завершения операций чтения.


## <a name="next-steps"></a>Дальнейшие действия
Исследовать другие параметры запроса, просмотрев операторы запроса, доступные в [выражения запросов](../../language-reference/query-expressions.md), а также просмотреть [ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572) чтобы понять, какие функции доступны при можно использовать этот поставщик типов.


## <a name="see-also"></a>См. также
[Поставщики типов](index.md)

[Поставщик типов SqlEntityConnection](https://msdn.microsoft.com/visualfsharpdocs/conceptual/sqlentityconnection-type-provider-%5bfsharp%5d)

[Пошаговое руководство: Создание типов F # из файла схемы EDMX](generating-fsharp-types-from-edmx.md)

[Платформа ADO.NET Entity Framework](https://msdn.microsoft.com/library/bb399572)

[Общие сведения о файлах .edmx](https://msdn.microsoft.com/library/f4c8e7ce-1db6-417e-9759-15f8b55155d4)

[Генератор модели EDM &#40; EdmGen.exe &#41;](https://msdn.microsoft.com/library/bb387165)
