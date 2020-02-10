---
title: Действия доступа к базе данных
ms.date: 03/30/2017
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
ms.openlocfilehash: ed3f0ad3f2fd19f622c9cb0faf7d5cd864b81995
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/09/2020
ms.locfileid: "77094648"
---
# <a name="database-access-activities"></a>Действия доступа к базе данных

Действия доступа к базе данных позволяют обращаться к базе данных из рабочего процесса. Эти действия позволяют обращаться к базам данных для получения или изменения информации и использовать [ADO.NET](../../data/adonet/index.md) для доступа к базе данных.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите на страницу (страница загрузки), чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
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

|Аргумент|Description|
|-|-|
|ProviderName|Неизменяемое имя поставщика ADO.NET. Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|
|ConnectionString|Строка соединения для подключения к базе данных. Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении. Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|
|SQL|Команда SQL для выполнения.|
|Параметры|Коллекция параметров SQL-запроса.|
|AffectedRecords|Количество записей, на которые повлияла последняя операция.|

## <a name="dbqueryscalar"></a>DbQueryScalar

Выполняет запрос, возвращающий единичное значение данные из базы данных.

Этот класс выполняет работу асинхронно (он является производным от класса <xref:System.Activities.AsyncCodeActivity%601> и использует его возможности для асинхронной работы).

Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика (`ProviderName`) и строку соединения (`ConnectionString`) или использовать имя конфигурации строки соединения (`ConfigFileSectionName`) из файла конфигурации приложения.

Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.

После выполнения `DbQueryScalar` скаляр возвращается в `Result out` аргументе (типа `TResult`, который определен в базовом классе <xref:System.Activities.AsyncCodeActivity%601>).

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

|Аргумент|Description|
|-|-|
|ProviderName|Неизменяемое имя поставщика ADO.NET. Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|
|ConnectionString|Строка соединения для подключения к базе данных. Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении. Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|
|SQL|Команда SQL для выполнения.|
|Параметры|Коллекция параметров SQL-запроса.|
|Результат|Скаляр, полученный после выполнения запроса. Этот аргумент имеет тип `TResult`.|

## <a name="dbquery"></a>DbQuery

Выполняет запрос, который возвращает список объектов. После выполнения запроса выполняется функция сопоставления (ее можно <xref:System.Func%601><`DbDataReader`, `TResult`> или <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>). Эта функция сопоставления получает запись в `DbDataReader` и сопоставляет ее возвращаемому объекту.

Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика (`ProviderName`) и строку соединения (`ConnectionString`) или использовать имя конфигурации строки соединения (`ConfigFileSectionName`) из файла конфигурации приложения.

Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.

Результаты SQL-запроса извлекаются с использованием `DbDataReader`. Действие выполняет перебор по `DbDataReader` и сопоставляет строки в `DbDataReader` с экземпляром `TResult`. Пользователь `DbQuery` должен предоставить код сопоставления, и это можно сделать двумя способами: с помощью <xref:System.Func%601><`DbDataReader`, `TResult`> или <xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>. В первом случае сопоставление совершается на одном шаге выполнения. Поэтому этот способ быстрее, но сериализация в XAML невозможна. Во втором случае сопоставление выполняется в несколько шагов. Поэтому может потребоваться больше времени, зато возможны сериализация в XAML и декларативное авторство (любое существующее действие может участвовать в сопоставлении).

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

|Аргумент|Description|
|-|-|
|ProviderName|Неизменяемое имя поставщика ADO.NET. Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|
|ConnectionString|Строка соединения для подключения к базе данных. Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении. Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|
|SQL|Команда SQL для выполнения.|
|Параметры|Коллекция параметров SQL-запроса.|
|Сопоставитель|Функция сопоставления (<xref:System.Func%601><`DbDataReader`, `TResult`>), которая принимает запись в `DataReader`, полученную в результате выполнения запроса, и возвращает экземпляр объекта типа `TResult`, добавляемого в коллекцию `Result`.<br /><br /> В этом случае сопоставление совершается на одном шаге выполнения, но декларативное авторство с использованием конструктора невозможно.|
|MapperFunc|Функция сопоставления (<xref:System.Activities.ActivityFunc%601><`DbDataReader`, `TResult`>), которая принимает запись в `DataReader`, полученную в результате выполнения запроса, и возвращает экземпляр объекта типа `TResult`, добавляемого в коллекцию `Result`.<br /><br /> В этом случае сопоставление совершается в несколько шагов выполнения. Для этой функции возможны сериализация в XAML и декларативное авторство (любое существующее действие может участвовать в сопоставлении).|
|Результат|Список объектов, полученный в результате выполнения запроса и выполнения функции сопоставления для каждой записи в `DataReader`.|

## <a name="dbquerydataset"></a>DbQueryDataSet

Выполняет запрос, который возвращает <xref:System.Data.DataSet>. Этот класс выполняет работу асинхронно. Он является производным от <xref:System.Activities.AsyncCodeActivity><`TResult`> и использует его асинхронные возможности.

Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика (`ProviderName`) и строку соединения (`ConnectionString`) или использовать имя конфигурации строки соединения (`ConfigFileSectionName`) из файла конфигурации приложения.

Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.

После выполнения `DbQueryDataSet` `DataSet` возвращается в аргументе `Result out` (типа `TResult`, который определен в базовом классе <xref:System.Activities.AsyncCodeActivity%601>).

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

|Аргумент|Description|
|-|-|
|ProviderName|Неизменяемое имя поставщика ADO.NET. Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|
|ConnectionString|Строка соединения для подключения к базе данных. Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении. Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|
|SQL|Команда SQL для выполнения.|
|Параметры|Коллекция параметров SQL-запроса.|
|Результат|<xref:System.Data.DataSet>, полученный после выполнения запроса.|

## <a name="configuring-connection-information"></a>Настройка сведений о соединении

Все DbActivities используют одни и те же параметры конфигурации. Их можно настроить двумя способами.

- `ConnectionString + InvariantName`: Укажите неизменяемое имя поставщика ADO.NET и строку соединения.

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

- `ConfigName`: Укажите имя раздела конфигурации, в котором содержатся сведения о соединении.

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

1. Откройте командную строку.

2. Перейдите в папку образца DbActivities.

3. Введите "Setup. cmd" и нажмите клавишу ВВОД.

    > [!NOTE]
    > Скрипт Setup.cmd пытается установить образец базы данных на экземпляр SQLExpress на локальном компьютере. Если образец необходимо установить на другом экземпляре сервера SQL, измените Setup.cmd, указав другое имя экземпляра.

##### <a name="to-uninstall-the-sample-database"></a>Удаление образца базы данных

1. Выполните в командной строке файл Cleanup.cmd из папки образца.

##### <a name="to-run-the-sample"></a>Запуск образца

1. Открытие решения в Visual Studio 2010

2. Для компиляции решения нажмите CTRL+SHIFT+B.

3. Чтобы запустить образец без отладки, нажмите сочетание клавиш CTRL+F5.

> [!IMPORTANT]
> Образцы уже могут быть установлены на компьютере. Перед продолжением проверьте следующий каталог (по умолчанию).
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> Если этот каталог не существует, перейдите к [примерам Windows Communication Foundation (WCF) и Windows Workflow Foundation (WF) для .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , чтобы скачать все Windows Communication Foundation (WCF) и [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Samples. Этот образец расположен в следующем каталоге.
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`
