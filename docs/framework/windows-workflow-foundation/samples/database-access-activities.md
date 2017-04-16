---
title: "Действия доступа к базе данных | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 174a381e-1343-46a8-a62c-7c2ae2c4f0b2
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Действия доступа к базе данных
Действия доступа к базе данных позволяют обращаться к базе данных из рабочего процесса.Эти действия позволяют обеспечивают доступ к базам данных для получения и изменения данных, а также позволяют использовать для доступа к базе данных использования [ADO.NET](http://go.microsoft.com/fwlink/?LinkId=166081).  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу загрузки, чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`  
  
## Действия базы данных  
 В следующих разделах приведен список действий, входящих в этот образец.  
  
## DbUpdate  
 Выполняет SQL\-запрос, который реализует изменение в базе данных \(вставку, обновление, удаление или иные изменения\).  
  
 Этот класс выполняет работу асинхронно \(он является производным от класса <xref:System.Activities.AsyncCodeActivity> и использует его возможности для асинхронной работы\).  
  
 Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика \(`ProviderName`\) и строку соединения \(`ConnectionString`\) или использовать имя конфигурации строки соединения \(`ConfigFileSectionName`\) из файла конфигурации приложения.  
  
 Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.  
  
 После выполнения `DbUpdate` количество измененных записей возвращается в свойстве `AffectedRecords`.  
  
```  
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
  
|||  
|-|-|  
|Аргумент|Описание|  
|ProviderName|Неизменяемое имя поставщика ADO.NET.Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|  
|ConnectionString|Строка соединения для подключения к базе данных.Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|  
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении.Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|  
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|  
|Sql|Выполняемая команда SQL.|  
|Параметры|Коллекция параметров SQL\-запроса.|  
|AffectedRecords|Количество записей, на которые повлияла последняя операция.|  
  
## DbQueryScalar  
 Выполняет запрос, возвращающий единичное значение данные из базы данных.  
  
 Этот класс выполняет работу асинхронно \(он является производным от класса <xref:System.Activities.AsyncCodeActivity%601> и использует его возможности для асинхронной работы\).  
  
 Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика \(`ProviderName`\) и строку соединения \(`ConnectionString`\) или использовать имя конфигурации строки соединения \(`ConfigFileSectionName`\) из файла конфигурации приложения.  
  
 Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.  
  
 После выполнения `DbQueryScalar` скалярное значение возвращается в аргументе `Result``out` \(типа `TResult`, который определен в базовом классе <xref:System.Activities.AsyncCodeActivity%601>\).  
  
```  
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
  
|||  
|-|-|  
|Аргумент|Описание|  
|ProviderName|Неизменяемое имя поставщика ADO.NET.Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|  
|ConnectionString|Строка соединения для подключения к базе данных.Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|  
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении.Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|  
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|  
|Sql|Выполняемая команда SQL.|  
|Параметры|Коллекция параметров SQL\-запроса.|  
|Результат|Скаляр, полученный после выполнения запроса.Этот аргумент имеет тип `TResult`.|  
  
## DbQuery  
 Выполняет запрос, который возвращает список объектов.После выполнения запроса выполняется функция сопоставления \(это может быть <xref:System.Func%601>\<`DbDataReader`, `TResult`\> или <xref:System.Activities.ActivityFunc%601>\<`DbDataReader`, `TResult`\>\).Эта функция сопоставления получает запись в `DbDataReader` и сопоставляет ее возвращаемому объекту.  
  
 Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика \(`ProviderName`\) и строку соединения \(`ConnectionString`\) или использовать имя конфигурации строки соединения \(`ConfigFileSectionName`\) из файла конфигурации приложения.  
  
 Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.  
  
 Результаты SQL\-запроса извлекаются с использованием `DbDataReader`.Действие выполняет перебор по `DbDataReader` и сопоставляет строки в `DbDataReader` с экземпляром `TResult`.Пользователь `DbQuery` должен предоставить код сопоставления, что может быть сделано двумя способами: с использованием <xref:System.Func%601>\<`DbDataReader`, `TResult`\> или с использованием <xref:System.Activities.ActivityFunc%601>\<`DbDataReader`, `TResult`\>.В первом случае сопоставление совершается на одном шаге выполнения.Поэтому этот способ быстрее, но сериализация в XAML невозможна.Во втором случае сопоставление выполняется в несколько шагов.Поэтому может потребоваться больше времени, зато возможны сериализация в XAML и декларативное авторство \(любое существующее действие может участвовать в сопоставлении\).  
  
```  
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
  
|||  
|-|-|  
|Аргумент|Описание|  
|ProviderName|Неизменяемое имя поставщика ADO.NET.Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|  
|ConnectionString|Строка соединения для подключения к базе данных.Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|  
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении.Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|  
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|  
|Sql|Выполняемая команда SQL.|  
|Параметры|Коллекция параметров SQL\-запроса.|  
|Сопоставитель|Функция сопоставления \(<xref:System.Func%601>\<`DbDataReader`, `TResult`\>\), которая принимает запись в объекте `DataReader`, полученном в результате выполнения запроса, и возвращает экземпляр типа `TResult` для добавления в коллекцию `Result`.<br /><br /> В этом случае сопоставление совершается на одном шаге выполнения, но декларативное авторство с использованием конструктора невозможно.|  
|MapperFunc|Функция сопоставления \(<xref:System.Activities.ActivityFunc%601>\<`DbDataReader`, `TResult`\>\), которая принимает запись в объекте `DataReader`, полученном в результате выполнения запроса, и возвращает экземпляр типа `TResult` для добавления в коллекцию `Result`.<br /><br /> В этом случае сопоставление совершается в несколько шагов выполнения.Для этой функции возможны сериализация в XAML и декларативное авторство \(любое существующее действие может участвовать в сопоставлении\).|  
|Результат|Список объектов, полученный в результате выполнения запроса и выполнения функции сопоставления для каждой записи в `DataReader`.|  
  
## DbQueryDataSet  
 Выполняет запрос, который возвращает <xref:System.Data.DataSet>.Этот класс выполняет работу асинхронно.Он является производным от класса <xref:System.Activities.AsyncCodeActivity>\<`TResult`\> и использует его асинхронные возможности.  
  
 Чтобы настроить сведения о соединении, можно задать неизменяемое имя поставщика \(`ProviderName`\) и строку соединения \(`ConnectionString`\) или использовать имя конфигурации строки соединения \(`ConfigFileSectionName`\) из файла конфигурации приложения.  
  
 Запрос для выполнения настраивается в свойстве `Sql`, а параметры передаются через коллекцию `Parameters`.  
  
 После выполнения `DbQueryDataSet``DataSet` возвращается в аргументе `Result``out` \(типа `TResult`, определенного в базовом классе <xref:System.Activities.AsyncCodeActivity%601>\).  
  
```  
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
  
|||  
|-|-|  
|Аргумент|Описание|  
|ProviderName|Неизменяемое имя поставщика ADO.NET.Если этот аргумент задан, то необходимо задать и аргумент `ConnectionString`.|  
|ConnectionString|Строка соединения для подключения к базе данных.Если этот аргумент задан, то необходимо задать и аргумент `ProviderName`.|  
|ConfigName|Имя раздела файла конфигурации, в котором хранятся сведения о соединении.Если этот аргумент задан, то аргументы `ProviderName` и `ConnectionString` не требуются.|  
|CommandType|Тип выполняемой команды <xref:System.Data.Common.DbCommand>.|  
|Sql|Выполняемая команда SQL.|  
|Параметры|Коллекция параметров SQL\-запроса.|  
|Результат|<xref:System.Data.DataSet>, полученный после выполнения запроса.|  
  
## Настройка сведений о соединении  
 Все DbActivities используют одни и те же параметры конфигурации.Их можно настроить двумя способами.  
  
-   `ConnectionString + InvariantName`: Укажите неизменяемое имя поставщика ADO.NET и строку соединения.  
  
    ```  
    Activity dbSelectCount = new DbQueryScalar<DateTime>()  
    {  
        ProviderName = "System.Data.SqlClient",  
        ConnectionString = @"Data Source=.\SQLExpress;  
                             Initial Catalog=DbActivitiesSample;  
                             Integrated Security=True",  
        Sql = "SELECT GetDate()"  
    };  
    ```  
  
-   `ConfigName`: Укажите имя раздела конфигурации, в котором содержатся сведения о соединении.  
  
    ```  
    <connectionStrings>      
        <add name="DbActivitiesSample"  
             providerName="System.Data.SqlClient"  
             connectionString="Data Source=.\SQLExpress;Initial Catalog=DbActivitiesSample;Integrated Security=true"/>  
      </connectionStrings>  
    ```  
  
-   В действии:  
  
    ```  
    Activity dbSelectCount = new DbQueryScalar<int>()  
    {                  
        ConfigName = "DbActivitiesSample",  
        Sql = "SELECT COUNT(*) FROM Roles"  
    };  
    ```  
  
## Выполнение образца  
  
### Инструкции по установке  
 Этот образец использует базу данных.Вместе с образцом предоставляется скрипт установки и загрузки \(Setup.cmd\).Этот файл необходимо выполнить из командной строки.  
  
 Скрипт Setup.cmd вызывает файл скрипта CreateDb.sql, который содержит команды SQL и выполняет следующие операции.  
  
-   Создает базу данных под именем DbActivitiesSample.  
  
-   Создает таблицу Roles.  
  
-   Создает таблицу Employees.  
  
-   Вставляет 3 записи в таблицу Roles.  
  
-   Вставляет двенадцать записей в таблицу Employees.  
  
##### Запуск команды Setup.cmd  
  
1.  Откройте окно командной строки.  
  
2.  Перейдите в папку образца DbActivities.  
  
3.  Введите «setup.cmd» и нажмите клавишу «ВВОД».  
  
    > [!NOTE]
    >  Скрипт Setup.cmd пытается установить образец базы данных на экземпляр SQLExpress на локальном компьютере.Если образец необходимо установить на другом экземпляре сервера SQL, измените Setup.cmd, указав другое имя экземпляра.  
  
##### Удаление образца базы данных  
  
1.  Выполните в командной строке файл Cleanup.cmd из папки образца.  
  
##### Запуск образца  
  
1.  Откройте решение в среде [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
2.  Для компиляции решения нажмите CTRL\+SHIFT\+B.  
  
3.  Чтобы запустить образец без отладки, нажмите сочетание клавиш CTRL\+F5.  
  
> [!IMPORTANT]
>  Образцы уже могут быть установлены на компьютере.Перед продолжением проверьте следующий каталог \(по умолчанию\).  
>   
>  `<диск_установки>:\WF_WCF_Samples`  
>   
>  Если этот каталог не существует, перейдите на страницу [Образцы Windows Communication Foundation \(WCF\) и Windows Workflow Foundation \(WF\) для .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780), чтобы загрузить все образцы [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] и [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Этот образец расположен в следующем каталоге.  
>   
>  `<диск_установки>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\DbActivities`