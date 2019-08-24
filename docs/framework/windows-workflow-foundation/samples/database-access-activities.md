---
title: Действия доступа к базе данных
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: 31794a583e87b5948457fac754cb5bf66fafa09c
ms.sourcegitcommit: 121ab70c1ebedba41d276e436dd2b1502748a49f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/24/2019
ms.locfileid: "70016039"
---
# <a name="database-access-activities"></a>Действия доступа к базе данных

Действия доступа к базе данных позволяют обращаться к базе данных из рабочего процесса. Эти действия позволяют обращаться к базам данных для получения или изменения информации и использовать [ADO.NET](https://go.microsoft.com/fwlink/?LinkId=166081) для доступа к базе данных.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите на страницу (страница загрузки), чтобы скачать все Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`

## <a name="database-activities"></a>Действия базы данных

В следующих разделах приведен список действий, входящих в этот образец.

## <a name="dbupdate"></a>DbUpdate

Выполняет SQL-запрос, который реализует изменение в базе данных (вставку, обновление, удаление или иные изменения).

Этот класс выполняет работу асинхронно (он является производным от класса <xref:System.Activities.AsyncCodeActivity> и использует его возможности для асинхронной работы).

Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика (`ProviderName`) и строку соединения (`ConnectionString`) или использовать имя конфигурации строки соединения (`ConfigFileSectionName`) из файла конфигурации приложения.

Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.

После выполнения `DbUpdate` количество измененных записей возвращается в свойстве `AffectedRecords`.

```csharp
Public class DbUpdate: AsyncCodeActivity
{
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [DependsOn("Parameters")]
    public OutArgument<int> AffectedRecords { get; set; }
}
```

|Аргумент|Описание|
|-|-|
|ProviderName|Неизменяемое имя поставщика ADO.NET. Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|
|ConnectionString|Строка соединения для подключения к базе данных. Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении. Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|
|Sql|Выполняемая команда SQL.|
|Параметры|Коллекция параметров SQL-запроса.|
|AffectedRecords|Количество записей, на которые повлияла последняя операция.|

## <a name="dbqueryscalar"></a>DbQueryScalar

Выполняет запрос, возвращающий единичное значение данные из базы данных.

Этот класс выполняет работу асинхронно (он является производным от класса <xref:System.Activities.AsyncCodeActivity%601> и использует его возможности для асинхронной работы).

Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика (`ProviderName`) и строку соединения (`ConnectionString`) или использовать имя конфигурации строки соединения (`ConfigFileSectionName`) из файла конфигурации приложения.

Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.

После `DbQueryScalar` выполнения, скаляр возвращается `Result out` в аргументе (типа `TResult`, который определен в базовом классе <xref:System.Activities.AsyncCodeActivity%601>).

```csharp
public class DbQueryScalar<TResult> : AsyncCodeActivity<TResult>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|Аргумент|Описание|
|-|-|
|ProviderName|Неизменяемое имя поставщика ADO.NET. Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|
|ConnectionString|Строка соединения для подключения к базе данных. Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении. Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|
|Sql|Выполняемая команда SQL.|
|Параметры|Коллекция параметров SQL-запроса.|
|Результат|Скаляр, полученный после выполнения запроса. Этот аргумент имеет тип `TResult`.|

## <a name="dbquery"></a>DbQuery

Выполняет запрос, который возвращает список объектов. После выполнения <xref:System.Func%601>запроса выполняется функция сопоставления (она может быть `DbDataReader` <xref:System.Activities.ActivityFunc%601> `DbDataReader` <, `TResult`> или <, `TResult`>). Эта функция сопоставления получает запись в `DbDataReader` и сопоставляет ее возвращаемому объекту.

Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика (`ProviderName`) и строку соединения (`ConnectionString`) или использовать имя конфигурации строки соединения (`ConfigFileSectionName`) из файла конфигурации приложения.

Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.

Результаты SQL-запроса извлекаются с использованием `DbDataReader`. Действие выполняет перебор по `DbDataReader` и сопоставляет строки в `DbDataReader` с экземпляром `TResult`. `DbQuery` Пользователь `TResult`должен предоставить код сопоставления, и это можно сделать двумя способами: < <xref:System.Func%601> `DbDataReader`с помощью, `TResult`> или <xref:System.Activities.ActivityFunc%601> < `DbDataReader`>. В первом случае сопоставление совершается на одном шаге выполнения. Поэтому этот способ быстрее, но сериализация в XAML невозможна. Во втором случае сопоставление выполняется в несколько шагов. Поэтому может потребоваться больше времени, зато возможны сериализация в XAML и декларативное авторство (любое существующее действие может участвовать в сопоставлении).

```csharp
public class DbQuery<TResult> : AsyncCodeActivity<IList<TResult>> where TResult : class
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }

    [OverloadGroup("DirectMapping")]
    [DefaultValue(null)]
    public Func<DbDataReader, TResult> Mapper { get; set; }

    [OverloadGroup("MultiplePulseMapping")]
    [DefaultValue(null)]
    public ActivityFunc<DbDataReader, TResult> MapperFunc { get; set; }
}
```

|Аргумент|Описание|
|-|-|
|ProviderName|Неизменяемое имя поставщика ADO.NET. Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|
|ConnectionString|Строка соединения для подключения к базе данных. Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении. Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|
|Sql|Выполняемая команда SQL.|
|Параметры|Коллекция параметров SQL-запроса.|
|Сопоставитель|Функция сопоставления (<xref:System.Func%601>< `DataReader` , >), которая принимает запись в полученном виде в результате выполнения запроса и возвращает экземпляр объекта типа `TResult` для добавления в `TResult``DbDataReader` `Result` коллекция.<br /><br /> В этом случае сопоставление совершается на одном шаге выполнения, но декларативное авторство с использованием конструктора невозможно.|
|MapperFunc|Функция сопоставления (<xref:System.Activities.ActivityFunc%601>< `DataReader` , >), которая принимает запись в полученном виде в результате выполнения запроса и возвращает экземпляр объекта типа `TResult` для добавления в `TResult``DbDataReader` `Result` коллекция.<br /><br /> В этом случае сопоставление совершается в несколько шагов выполнения. Для этой функции возможны сериализация в XAML и декларативное авторство (любое существующее действие может участвовать в сопоставлении).|
|Результат|Список объектов, полученный в результате выполнения запроса и выполнения функции сопоставления для каждой записи в `DataReader`.|

## <a name="dbquerydataset"></a>DbQueryDataSet

Выполняет запрос, который возвращает <xref:System.Data.DataSet>. Этот класс выполняет работу асинхронно. Он является производным <xref:System.Activities.AsyncCodeActivity>от < `TResult`> и использует его асинхронные возможности.

Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика (`ProviderName`) и строку соединения (`ConnectionString`) или использовать имя конфигурации строки соединения (`ConfigFileSectionName`) из файла конфигурации приложения.

Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.

`Result out` `TResult`После выполнения объект возвращается в аргументе (типа, который определен в базовом классе <xref:System.Activities.AsyncCodeActivity%601>). `DataSet` `DbQueryDataSet`

```csharp
public class DbQueryDataSet : AsyncCodeActivity<DataSet>
{
    // public arguments
    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DefaultValue(null)]
    public InArgument<string> ProviderName { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConnectionString")]
    [DependsOn("ProviderName")]
    [DefaultValue(null)]
    public InArgument<string> ConnectionString { get; set; }

    [RequiredArgument]
    [OverloadGroup("ConfigFileSectionName")]
    [DefaultValue(null)]
    public InArgument<string> ConfigName { get; set; }

    [DefaultValue(null)]
    public CommandType CommandType { get; set; }

    [RequiredArgument]
    public InArgument<string> Sql { get; set; }

    [DependsOn("Sql")]
    [DefaultValue(null)]
    public IDictionary<string, Argument> Parameters { get; }
}
```

|Аргумент|Описание|
|-|-|
|ProviderName|Неизменяемое имя поставщика ADO.NET. Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|
|ConnectionString|Строка соединения для подключения к базе данных. Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении. Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|
|Sql|Выполняемая команда SQL.|
|Параметры|Коллекция параметров SQL-запроса.|
|Результат|<xref:System.Data.DataSet>, полученный после выполнения запроса.|

## <a name="configuring-connection-information"></a>Настройка сведений о соединении

Все DbActivities используют одни и те же параметры конфигурации. Их можно настроить двумя способами.

- `ConnectionString + InvariantName`: Задайте неизменяемое имя поставщика ADO.NET и строку подключения.

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<DateTime>()
  {
      ProviderName = "System.Data.SqlClient",
      ConnectionString = @"Data Source=.\SQLExpress;
                            Initial Catalog=DbActivitiesSample;
                            Integrated Security=True",
      Sql = "SELECT GetDate()"
  };
  ```

- `ConfigName`: Задайте имя раздела конфигурации, содержащего сведения о соединении.

  ```xml
  <connectionStrings>
      <add name="DbActivitiesSample"
            providerName="System.Data.SqlClient"
            connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>
    </connectionStrings>
  ```

- В действии:

  ```csharp
  Activity dbSelectCount = new DbQueryScalar<int>()
  {
      ConfigName = "DbActivitiesSample",
      Sql = "SELECT COUNT(*) FROM Roles"
  };
  ```

## <a name="running-this-sample"></a>Выполнение образца

### <a name="setup-instructions"></a>Инструкции по установке

Этот образец использует базу данных. Вместе с образцом предоставляется скрипт установки и загрузки (Setup.cmd). Этот файл необходимо выполнить из командной строки.

Скрипт Setup.cmd вызывает файл скрипта CreateDb.sql, который содержит команды SQL и выполняет следующие операции.

- Создает базу данных под именем DbActivitiesSample.

- Создает таблицу Roles.

- Создает таблицу Employees.

- Вставляет 3 записи в таблицу Roles.

- Вставляет двенадцать записей в таблицу Employees.

##### <a name="to-run-setupcmd"></a>Запуск команды Setup.cmd

1. Откройте окно командной строки.

2. Перейдите в папку образца DbActivities.

3. Введите "Setup. cmd" и нажмите клавишу ВВОД.

    > [!NOTE]
    > Скрипт Setup.cmd пытается установить образец базы данных на экземпляр SQLExpress на локальном компьютере. Если образец необходимо установить на другом экземпляре сервера SQL, измените Setup.cmd, указав другое имя экземпляра.

##### <a name="to-uninstall-the-sample-database"></a>Удаление образца базы данных

1. Выполните в командной строке файл Cleanup.cmd из папки образца.

##### <a name="to-run-the-sample"></a>Выполнение образца

1. Открытие решения в Visual Studio 2010

2. Для компиляции решения нажмите CTRL+SHIFT+B.

3. Чтобы запустить образец без отладки, нажмите сочетание клавиш CTRL+F5.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , чтобы скачать все Windows Communication Foundation (WCF) [!INCLUDE[wf1](../../../../includes/wf1-md.md)] и примеры. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
