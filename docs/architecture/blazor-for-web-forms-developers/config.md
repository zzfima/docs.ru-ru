---
title: конфигурация приложения;
description: Узнайте, как настроить приложения Blazor без использования ConfigurationManager.
author: csharpfritz
ms.author: jefritz
ms.date: 04/01/2020
ms.openlocfilehash: c780a395f72e2520af86c20c7f6618953a528ff7
ms.sourcegitcommit: 961ec21c22d2f1d55c9cc8a7edf2ade1d1fd92e3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2020
ms.locfileid: "80588245"
---
# <a name="app-configuration"></a>конфигурация приложения;

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

Основной способ загрузки конфигурации приложения в web-формах —&mdash;это записи в файле *web.config* либо на сервере, либо в соответствующем файле конфигурации, на который ссылается *web.config.* Статичный `ConfigurationManager` объект можно использовать для взаимодействия с настройками приложения, строками подключения к репозиторию данных и другими поставщиками расширенной конфигурации, которые добавляются в приложение. Это типично, чтобы увидеть взаимодействия с конфигурацией приложения, как видно из следующего кода:

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

С ASP.NET Core и сервера стороне Blazor, *web.config* файл может присутствовать, если ваше приложение размещается на сервере Windows IIS. Однако нет `ConfigurationManager` никакого взаимодействия с этой конфигурацией, и вы можете получить более структурированную конфигурацию приложения из других источников. Давайте взглянем на то, как собирается конфигурация и как вы можете получить доступ к информации о конфигурации из файла *web.config.*

## <a name="configuration-sources"></a>Источники конфигураций

ASP.NET Core признает, что существует множество источников конфигурации, которые вы можете использовать для вашего приложения. Платформа пытается предложить вам лучшее из этих функций по умолчанию. Конфигурация считывается и агрегируется из этих различных источников ASP.NET Core. Позже загруженные значения для той же конфигурации ключа имеют приоритет над более ранними значениями.

ASP.NET Core был разработан, чтобы быть облачным и сделать конфигурацию приложений проще как для операторов, так и для разработчиков. ASP.NET Core знает окружающую среду и знает, `Production` `Development` работает ли оно в вашей среде или в среде. Индикатор среды устанавливается `ASPNETCORE_ENVIRONMENT` в переменной среды системы. Если значение не настроено, приложение по умолчанию работает в среде. `Production`

Приложение может вызвать и добавить конфигурацию из нескольких источников в зависимости от имени среды. По умолчанию конфигурация загружается из следующих ресурсов в перечисленном порядке:

1. *appsettings.json* файл, если присутствует
1. *appsettings. файл ENVIRONMENT_NAME.json,* если он присутствует
1. Файл секретов пользователя на диске, если он присутствует
1. Переменные среды
1. аргументов командной строки;

## <a name="appsettingsjson-format-and-access"></a>формат appsettings.json и доступ

Файл *appsettings.json* может быть иерархическим с значениями, структурированными как следующие JSON:

```json
{
  "section0": {
    "key0": "value",
    "key1": "value"
  },
  "section1": {
    "key0": "value",
    "key1": "value"
  }
}
```

При представлении предыдущего JSON система конфигурации выравнивает значения ребенка и ссылается на их полностью квалифицированные иерархические пути. Символ толстой`:`кишки () отделяет каждое свойство в иерархии. Например, ключ `section1:key0` конфигурации `section1` получает доступ к `key0` значению объекта в буквальном смысле.

## <a name="user-secrets"></a>Секреты пользователя

Секреты пользователя:

* Значения конфигурации, хранящиеся в файле JSON на рабочей станции разработчика, вне папки разработки приложения.
* Только загружается `Development` при запуске в окружающую среду.
* Сопряженс с конкретным приложением.
* Управляется с `user-secrets` командой .NET Core CLI.

Назначьте приложение для хранения секретов, `user-secrets` выражая команду:

```dotnetcli
dotnet user-secrets init
```

Предыдущая команда `UserSecretsId` добавляет элемент в файл проекта. Элемент содержит GUID, который используется для ассоциировать секреты с приложением. Затем вы можете определить `set` секрет с командой. Пример:

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

Предыдущая команда `Parent:ApiKey` делает ключ конфигурации доступным на рабочей `12345`станции разработчика со значением.

Более подробную информацию о создании, хранении и управлении секретами пользователей можно узнать [в документе ASP.NET Core.](/aspnet/core/security/app-secrets)

## <a name="environment-variables"></a>Переменные среды

Следующий набор значений, загруженных в конфигурацию приложения, — это переменные среды системы. Все параметры переменных среды вашей системы теперь доступны вам через API конфигурации. Иерархические значения сплющиваются и разделены символами толстой кишки при чтении внутри приложения. Тем не менее, некоторые операционные системы не позволяют переменным названиям среды символов толстой кишки. ASP.NET Core устраняет это ограничение, преобразовывая значения, которые имеют двойные значения ()`__`в толстую кишку при доступе к ним. Значение `Parent:ApiKey` из раздела секретов пользователя выше может `Parent__ApiKey`быть переопределено с переменной среды.

## <a name="command-line-arguments"></a>аргументов командной строки;

Конфигурация также может быть предоставлена в качестве аргументов командной строки при начале работы приложения. Используйте двойной`--`тире ()`/`или вперед-слэш ( ) обозначение, чтобы указать имя значения конфигурации, чтобы установить и значение, которое будет настроено. Синтаксис напоминает следующие команды:

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a>Возвращение web.config

Если вы развернули приложение в Windows на IIS, файл *web.config* по-прежнему настраивает IIS на управление приложением. По умолчанию IIS добавляет ссылку на ASP.NET основной модуль (ANCM). ANCM — это родной модуль IIS, в котором размещается ваше приложение вместо веб-сервера Kestrel. Этот раздел *web.config* напоминает следующую разметку XML:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <location path="." inheritInChildApplications="false">
    <system.webServer>
      <handlers>
        <add name="aspNetCore" path="*" verb="*" modules="AspNetCoreModuleV2" resourceType="Unspecified" />
      </handlers>
      <aspNetCore processPath=".\MyApp.exe"
                  stdoutLogEnabled="false"
                  stdoutLogFile=".\logs\stdout"
                  hostingModel="inprocess" />
    </system.webServer>
  </location>
</configuration>
```

Конфигурация приложения может быть определена `environmentVariables` путем `aspNetCore` вложения элемента в элемент. Значения, определенные в этом разделе, представлены ASP.NET приложению Core в качестве переменных среды. Переменные среды загружаются надлежащим образом во время этого сегмента запуска приложения.

```xml
<aspNetCore processPath="dotnet"
      arguments=".\MyApp.dll"
      stdoutLogEnabled="false"
      stdoutLogFile=".\logs\stdout"
      hostingModel="inprocess">
  <environmentVariables>
    <environmentVariable name="ASPNETCORE_ENVIRONMENT" value="Development" />
    <environmentVariable name="Parent:ApiKey" value="67890" />
  </environmentVariables>
</aspNetCore>
```

## <a name="read-configuration-in-the-app"></a>Читать конфигурацию в приложении

ASP.NET Core обеспечивает конфигурацию <xref:Microsoft.Extensions.Configuration.IConfiguration> приложения через интерфейс. Этот интерфейс конфигурации должен быть запрошен компонентами Blazor, страницами Blazor и любым другим классом, управляемым ASP.NET Core, который нуждается в доступе к конфигурации. Платформа ASP.NET Core автоматически заполнит этот интерфейс решенной конфигурацией, настроенной ранее. На странице Blazor или разметке Razor компонента `IConfiguration` можно `@inject` ввести объект с директивой в верхней части *файла .razor* следующим образом:

```razor
@inject IConfiguration Configuration
```

Это предыдущее `IConfiguration` утверждение делает `Configuration` объект доступным в качестве переменной на протяжении всей остальной части шаблона Razor.

Индивидуальные настройки конфигурации можно прочитать, указав иерархию параметров настройки конфигурации, испрашиваемую в качестве параметра индекса:

```csharp
var mySetting = Configuration["section1:key0"];
```

Вы можете получить целые <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> разделы конфигурации, используя метод для получения коллекции `GetSection("section1")` ключей в определенном месте с синтаксисом, аналогичным для получения конфигурации для раздела 1 из предыдущего примера.

## <a name="strongly-typed-configuration"></a>Сильно набранная конфигурация

С помощью Web Forms можно было создать сильно набранный <xref:System.Configuration.ConfigurationSection> тип конфигурации, унаследованный от типа и связанных типов. Позволяет `ConfigurationSection` настроить некоторые бизнес-правила и обработку для этих значений конфигурации.

В ASP.NET Core можно указать иерархию классов, которая будет получать значения конфигурации. Эти классы:

* Не нужно наследовать от родительского класса.
* Следует `public` включать свойства, которые соответствуют свойствам и ссылкам на тип ы для структуры конфигурации, которую вы хотите захватить.

Для более раннего образца *appsettings.json* можно определить следующие классы для захвата значений:

```csharp
public class MyConfig
{
    public MyConfigSection section0 { get; set;}

    public MyConfigSection section1 { get; set;}
}

public class MyConfigSection
{
    public string key0 { get; set; }

    public string key1 { get; set; }
}
```

Эта иерархия классов может быть засена, добавляя следующую строку к методу: `Startup.ConfigureServices`

```csharp
services.Configure<MyConfig>(Configuration);
```

В остальной части приложения можно добавить параметр ввода в классы или директиву `@inject` в шаблонах типа `IOptions<MyConfig>` Razor для получения сильно набранных параметров конфигурации. Свойство `IOptions<MyConfig>.Value` даст `MyConfig` значение, заселенное настройками конфигурации.

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

Более подробную информацию о функции Options можно найти в [шаблоне Options в ASP.NET core](/aspnet/core/fundamentals/configuration/options#options-interfaces) документе.

>[!div class="step-by-step"]
>[Назад](middleware.md)
>[Вперед](security-authentication-authorization.md)
