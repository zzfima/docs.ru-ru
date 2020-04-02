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
# <a name="app-configuration"></a><span data-ttu-id="92aca-103">конфигурация приложения;</span><span class="sxs-lookup"><span data-stu-id="92aca-103">App configuration</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="92aca-104">Основной способ загрузки конфигурации приложения в web-формах —&mdash;это записи в файле *web.config* либо на сервере, либо в соответствующем файле конфигурации, на который ссылается *web.config.* Статичный `ConfigurationManager` объект можно использовать для взаимодействия с настройками приложения, строками подключения к репозиторию данных и другими поставщиками расширенной конфигурации, которые добавляются в приложение.</span><span class="sxs-lookup"><span data-stu-id="92aca-104">The primary way to load app configuration in Web Forms is with entries in the *web.config* file&mdash;either on the server or a related configuration file referenced by *web.config*. You can use the static `ConfigurationManager` object to interact with app settings, data repository connection strings, and other extended configuration providers that are added into the app.</span></span> <span data-ttu-id="92aca-105">Это типично, чтобы увидеть взаимодействия с конфигурацией приложения, как видно из следующего кода:</span><span class="sxs-lookup"><span data-stu-id="92aca-105">It's typical to see interactions with app configuration as seen in the following code:</span></span>

```csharp
var configurationValue = ConfigurationManager.AppSettings["ConfigurationSettingName"];
var connectionString = ConfigurationManager.ConnectionStrings["MyDatabaseConnectionName"].ConnectionString;
```

<span data-ttu-id="92aca-106">С ASP.NET Core и сервера стороне Blazor, *web.config* файл может присутствовать, если ваше приложение размещается на сервере Windows IIS.</span><span class="sxs-lookup"><span data-stu-id="92aca-106">With ASP.NET Core and server-side Blazor, the *web.config* file MAY be present if your app is hosted on a Windows IIS server.</span></span> <span data-ttu-id="92aca-107">Однако нет `ConfigurationManager` никакого взаимодействия с этой конфигурацией, и вы можете получить более структурированную конфигурацию приложения из других источников.</span><span class="sxs-lookup"><span data-stu-id="92aca-107">However, there's no `ConfigurationManager` interaction with this configuration, and you can receive more structured app configuration from other sources.</span></span> <span data-ttu-id="92aca-108">Давайте взглянем на то, как собирается конфигурация и как вы можете получить доступ к информации о конфигурации из файла *web.config.*</span><span class="sxs-lookup"><span data-stu-id="92aca-108">Let's take a look at how configuration is gathered and how you can still access configuration information from a *web.config* file.</span></span>

## <a name="configuration-sources"></a><span data-ttu-id="92aca-109">Источники конфигураций</span><span class="sxs-lookup"><span data-stu-id="92aca-109">Configuration sources</span></span>

<span data-ttu-id="92aca-110">ASP.NET Core признает, что существует множество источников конфигурации, которые вы можете использовать для вашего приложения.</span><span class="sxs-lookup"><span data-stu-id="92aca-110">ASP.NET Core recognizes there are many configuration sources you may want to use for your app.</span></span> <span data-ttu-id="92aca-111">Платформа пытается предложить вам лучшее из этих функций по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="92aca-111">The framework attempts to offer you the best of these features by default.</span></span> <span data-ttu-id="92aca-112">Конфигурация считывается и агрегируется из этих различных источников ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="92aca-112">Configuration is read and aggregated from these various sources by ASP.NET Core.</span></span> <span data-ttu-id="92aca-113">Позже загруженные значения для той же конфигурации ключа имеют приоритет над более ранними значениями.</span><span class="sxs-lookup"><span data-stu-id="92aca-113">Later loaded values for the same configuration key take precedence over earlier values.</span></span>

<span data-ttu-id="92aca-114">ASP.NET Core был разработан, чтобы быть облачным и сделать конфигурацию приложений проще как для операторов, так и для разработчиков.</span><span class="sxs-lookup"><span data-stu-id="92aca-114">ASP.NET Core was designed to be cloud-aware and to make configuration of apps easier for both operators and developers.</span></span> <span data-ttu-id="92aca-115">ASP.NET Core знает окружающую среду и знает, `Production` `Development` работает ли оно в вашей среде или в среде.</span><span class="sxs-lookup"><span data-stu-id="92aca-115">ASP.NET Core is environment-aware and knows if it's running in your `Production` or `Development` environment.</span></span> <span data-ttu-id="92aca-116">Индикатор среды устанавливается `ASPNETCORE_ENVIRONMENT` в переменной среды системы.</span><span class="sxs-lookup"><span data-stu-id="92aca-116">The environment indicator is set in the `ASPNETCORE_ENVIRONMENT` system environment variable.</span></span> <span data-ttu-id="92aca-117">Если значение не настроено, приложение по умолчанию работает в среде. `Production`</span><span class="sxs-lookup"><span data-stu-id="92aca-117">If no value is configured, the app defaults to running in the `Production` environment.</span></span>

<span data-ttu-id="92aca-118">Приложение может вызвать и добавить конфигурацию из нескольких источников в зависимости от имени среды.</span><span class="sxs-lookup"><span data-stu-id="92aca-118">Your app can trigger and add configuration from several sources based on the environment's name.</span></span> <span data-ttu-id="92aca-119">По умолчанию конфигурация загружается из следующих ресурсов в перечисленном порядке:</span><span class="sxs-lookup"><span data-stu-id="92aca-119">By default, configuration is loaded from the following resources in the order listed:</span></span>

1. <span data-ttu-id="92aca-120">*appsettings.json* файл, если присутствует</span><span class="sxs-lookup"><span data-stu-id="92aca-120">*appsettings.json* file, if present</span></span>
1. <span data-ttu-id="92aca-121">*appsettings. файл ENVIRONMENT_NAME.json,* если он присутствует</span><span class="sxs-lookup"><span data-stu-id="92aca-121">*appsettings.{ENVIRONMENT_NAME}.json* file, if present</span></span>
1. <span data-ttu-id="92aca-122">Файл секретов пользователя на диске, если он присутствует</span><span class="sxs-lookup"><span data-stu-id="92aca-122">User secrets file on disk, if present</span></span>
1. <span data-ttu-id="92aca-123">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="92aca-123">Environment variables</span></span>
1. <span data-ttu-id="92aca-124">аргументов командной строки;</span><span class="sxs-lookup"><span data-stu-id="92aca-124">Command-line arguments</span></span>

## <a name="appsettingsjson-format-and-access"></a><span data-ttu-id="92aca-125">формат appsettings.json и доступ</span><span class="sxs-lookup"><span data-stu-id="92aca-125">appsettings.json format and access</span></span>

<span data-ttu-id="92aca-126">Файл *appsettings.json* может быть иерархическим с значениями, структурированными как следующие JSON:</span><span class="sxs-lookup"><span data-stu-id="92aca-126">The *appsettings.json* file can be hierarchical with values structured like the following JSON:</span></span>

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

<span data-ttu-id="92aca-127">При представлении предыдущего JSON система конфигурации выравнивает значения ребенка и ссылается на их полностью квалифицированные иерархические пути.</span><span class="sxs-lookup"><span data-stu-id="92aca-127">When presented with the preceding JSON, the configuration system flattens child values and references their fully qualified hierarchical paths.</span></span> <span data-ttu-id="92aca-128">Символ толстой`:`кишки () отделяет каждое свойство в иерархии.</span><span class="sxs-lookup"><span data-stu-id="92aca-128">A colon (`:`) character separates each property in the hierarchy.</span></span> <span data-ttu-id="92aca-129">Например, ключ `section1:key0` конфигурации `section1` получает доступ к `key0` значению объекта в буквальном смысле.</span><span class="sxs-lookup"><span data-stu-id="92aca-129">For example, the configuration key `section1:key0` accesses the `section1` object literal's `key0` value.</span></span>

## <a name="user-secrets"></a><span data-ttu-id="92aca-130">Секреты пользователя</span><span class="sxs-lookup"><span data-stu-id="92aca-130">User secrets</span></span>

<span data-ttu-id="92aca-131">Секреты пользователя:</span><span class="sxs-lookup"><span data-stu-id="92aca-131">User secrets are:</span></span>

* <span data-ttu-id="92aca-132">Значения конфигурации, хранящиеся в файле JSON на рабочей станции разработчика, вне папки разработки приложения.</span><span class="sxs-lookup"><span data-stu-id="92aca-132">Configuration values that are stored in a JSON file on the developer's workstation, outside of the app development folder.</span></span>
* <span data-ttu-id="92aca-133">Только загружается `Development` при запуске в окружающую среду.</span><span class="sxs-lookup"><span data-stu-id="92aca-133">Only loaded when running in the `Development` environment.</span></span>
* <span data-ttu-id="92aca-134">Сопряженс с конкретным приложением.</span><span class="sxs-lookup"><span data-stu-id="92aca-134">Associated with a specific app.</span></span>
* <span data-ttu-id="92aca-135">Управляется с `user-secrets` командой .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="92aca-135">Managed with the .NET Core CLI's `user-secrets` command.</span></span>

<span data-ttu-id="92aca-136">Назначьте приложение для хранения секретов, `user-secrets` выражая команду:</span><span class="sxs-lookup"><span data-stu-id="92aca-136">Configure your app for secrets storage by executing the `user-secrets` command:</span></span>

```dotnetcli
dotnet user-secrets init
```

<span data-ttu-id="92aca-137">Предыдущая команда `UserSecretsId` добавляет элемент в файл проекта.</span><span class="sxs-lookup"><span data-stu-id="92aca-137">The preceding command adds a `UserSecretsId` element to the project file.</span></span> <span data-ttu-id="92aca-138">Элемент содержит GUID, который используется для ассоциировать секреты с приложением.</span><span class="sxs-lookup"><span data-stu-id="92aca-138">The element contains a GUID, which is used to associate secrets with the app.</span></span> <span data-ttu-id="92aca-139">Затем вы можете определить `set` секрет с командой.</span><span class="sxs-lookup"><span data-stu-id="92aca-139">You can then define a secret with the `set` command.</span></span> <span data-ttu-id="92aca-140">Пример:</span><span class="sxs-lookup"><span data-stu-id="92aca-140">For example:</span></span>

```dotnetcli
dotnet user-secrets set "Parent:ApiKey" "12345"
```

<span data-ttu-id="92aca-141">Предыдущая команда `Parent:ApiKey` делает ключ конфигурации доступным на рабочей `12345`станции разработчика со значением.</span><span class="sxs-lookup"><span data-stu-id="92aca-141">The preceding command makes the `Parent:ApiKey` configuration key available on a developer's workstation with the value `12345`.</span></span>

<span data-ttu-id="92aca-142">Более подробную информацию о создании, хранении и управлении секретами пользователей можно узнать [в документе ASP.NET Core.](/aspnet/core/security/app-secrets)</span><span class="sxs-lookup"><span data-stu-id="92aca-142">For more information about creating, storing, and managing user secrets, see the [Safe storage of app secrets in development in ASP.NET Core](/aspnet/core/security/app-secrets) document.</span></span>

## <a name="environment-variables"></a><span data-ttu-id="92aca-143">Переменные среды</span><span class="sxs-lookup"><span data-stu-id="92aca-143">Environment variables</span></span>

<span data-ttu-id="92aca-144">Следующий набор значений, загруженных в конфигурацию приложения, — это переменные среды системы.</span><span class="sxs-lookup"><span data-stu-id="92aca-144">The next set of values loaded into your app configuration is the system's environment variables.</span></span> <span data-ttu-id="92aca-145">Все параметры переменных среды вашей системы теперь доступны вам через API конфигурации.</span><span class="sxs-lookup"><span data-stu-id="92aca-145">All of your system's environment variable settings are now accessible to you through the configuration API.</span></span> <span data-ttu-id="92aca-146">Иерархические значения сплющиваются и разделены символами толстой кишки при чтении внутри приложения.</span><span class="sxs-lookup"><span data-stu-id="92aca-146">Hierarchical values are flattened and separated by colon characters when read inside your app.</span></span> <span data-ttu-id="92aca-147">Тем не менее, некоторые операционные системы не позволяют переменным названиям среды символов толстой кишки.</span><span class="sxs-lookup"><span data-stu-id="92aca-147">However, some operating systems don't allow the colon character environment variable names.</span></span> <span data-ttu-id="92aca-148">ASP.NET Core устраняет это ограничение, преобразовывая значения, которые имеют двойные значения ()`__`в толстую кишку при доступе к ним.</span><span class="sxs-lookup"><span data-stu-id="92aca-148">ASP.NET Core addresses this limitation by converting values that have double-underscores (`__`) into a colon when they're accessed.</span></span> <span data-ttu-id="92aca-149">Значение `Parent:ApiKey` из раздела секретов пользователя выше может `Parent__ApiKey`быть переопределено с переменной среды.</span><span class="sxs-lookup"><span data-stu-id="92aca-149">The `Parent:ApiKey` value from the user secrets section above can be overridden with the environment variable `Parent__ApiKey`.</span></span>

## <a name="command-line-arguments"></a><span data-ttu-id="92aca-150">аргументов командной строки;</span><span class="sxs-lookup"><span data-stu-id="92aca-150">Command-line arguments</span></span>

<span data-ttu-id="92aca-151">Конфигурация также может быть предоставлена в качестве аргументов командной строки при начале работы приложения.</span><span class="sxs-lookup"><span data-stu-id="92aca-151">Configuration can also be provided as command-line arguments when your app is started.</span></span> <span data-ttu-id="92aca-152">Используйте двойной`--`тире ()`/`или вперед-слэш ( ) обозначение, чтобы указать имя значения конфигурации, чтобы установить и значение, которое будет настроено.</span><span class="sxs-lookup"><span data-stu-id="92aca-152">Use the double-dash (`--`) or forward-slash (`/`) notation to indicate the name of the configuration value to set and the value to be configured.</span></span> <span data-ttu-id="92aca-153">Синтаксис напоминает следующие команды:</span><span class="sxs-lookup"><span data-stu-id="92aca-153">The syntax resembles the following commands:</span></span>

```dotnetcli
dotnet run CommandLineKey1=value1 --CommandLineKey2=value2 /CommandLineKey3=value3
dotnet run --CommandLineKey1 value1 /CommandLineKey2 value2
dotnet run Parent:ApiKey=67890
```

## <a name="the-return-of-webconfig"></a><span data-ttu-id="92aca-154">Возвращение web.config</span><span class="sxs-lookup"><span data-stu-id="92aca-154">The return of web.config</span></span>

<span data-ttu-id="92aca-155">Если вы развернули приложение в Windows на IIS, файл *web.config* по-прежнему настраивает IIS на управление приложением.</span><span class="sxs-lookup"><span data-stu-id="92aca-155">If you've deployed your app to Windows on IIS, the *web.config* file still configures IIS to manage your app.</span></span> <span data-ttu-id="92aca-156">По умолчанию IIS добавляет ссылку на ASP.NET основной модуль (ANCM).</span><span class="sxs-lookup"><span data-stu-id="92aca-156">By default, IIS adds a reference to the ASP.NET Core Module (ANCM).</span></span> <span data-ttu-id="92aca-157">ANCM — это родной модуль IIS, в котором размещается ваше приложение вместо веб-сервера Kestrel.</span><span class="sxs-lookup"><span data-stu-id="92aca-157">ANCM is a native IIS module that hosts your app in place of the Kestrel web server.</span></span> <span data-ttu-id="92aca-158">Этот раздел *web.config* напоминает следующую разметку XML:</span><span class="sxs-lookup"><span data-stu-id="92aca-158">This *web.config* section resembles the following XML markup:</span></span>

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

<span data-ttu-id="92aca-159">Конфигурация приложения может быть определена `environmentVariables` путем `aspNetCore` вложения элемента в элемент.</span><span class="sxs-lookup"><span data-stu-id="92aca-159">App-specific configuration can be defined by nesting an `environmentVariables` element in the `aspNetCore` element.</span></span> <span data-ttu-id="92aca-160">Значения, определенные в этом разделе, представлены ASP.NET приложению Core в качестве переменных среды.</span><span class="sxs-lookup"><span data-stu-id="92aca-160">The values defined in this section are presented to the ASP.NET Core app as environment variables.</span></span> <span data-ttu-id="92aca-161">Переменные среды загружаются надлежащим образом во время этого сегмента запуска приложения.</span><span class="sxs-lookup"><span data-stu-id="92aca-161">The environment variables load appropriately during that segment of app startup.</span></span>

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

## <a name="read-configuration-in-the-app"></a><span data-ttu-id="92aca-162">Читать конфигурацию в приложении</span><span class="sxs-lookup"><span data-stu-id="92aca-162">Read configuration in the app</span></span>

<span data-ttu-id="92aca-163">ASP.NET Core обеспечивает конфигурацию <xref:Microsoft.Extensions.Configuration.IConfiguration> приложения через интерфейс.</span><span class="sxs-lookup"><span data-stu-id="92aca-163">ASP.NET Core provides app configuration through the <xref:Microsoft.Extensions.Configuration.IConfiguration> interface.</span></span> <span data-ttu-id="92aca-164">Этот интерфейс конфигурации должен быть запрошен компонентами Blazor, страницами Blazor и любым другим классом, управляемым ASP.NET Core, который нуждается в доступе к конфигурации.</span><span class="sxs-lookup"><span data-stu-id="92aca-164">This configuration interface should be requested by your Blazor components, Blazor pages, and any other ASP.NET Core-managed class that needs access to configuration.</span></span> <span data-ttu-id="92aca-165">Платформа ASP.NET Core автоматически заполнит этот интерфейс решенной конфигурацией, настроенной ранее.</span><span class="sxs-lookup"><span data-stu-id="92aca-165">The ASP.NET Core framework will automatically populate this interface with the resolved configuration configured earlier.</span></span> <span data-ttu-id="92aca-166">На странице Blazor или разметке Razor компонента `IConfiguration` можно `@inject` ввести объект с директивой в верхней части *файла .razor* следующим образом:</span><span class="sxs-lookup"><span data-stu-id="92aca-166">On a Blazor page or a component's Razor markup, you can inject the `IConfiguration` object with an `@inject` directive at the top of the *.razor* file like this:</span></span>

```razor
@inject IConfiguration Configuration
```

<span data-ttu-id="92aca-167">Это предыдущее `IConfiguration` утверждение делает `Configuration` объект доступным в качестве переменной на протяжении всей остальной части шаблона Razor.</span><span class="sxs-lookup"><span data-stu-id="92aca-167">This preceding statement makes the `IConfiguration` object available as the `Configuration` variable throughout the rest of the Razor template.</span></span>

<span data-ttu-id="92aca-168">Индивидуальные настройки конфигурации можно прочитать, указав иерархию параметров настройки конфигурации, испрашиваемую в качестве параметра индекса:</span><span class="sxs-lookup"><span data-stu-id="92aca-168">Individual configuration settings can be read by specifying the configuration setting hierarchy sought as an indexer parameter:</span></span>

```csharp
var mySetting = Configuration["section1:key0"];
```

<span data-ttu-id="92aca-169">Вы можете получить целые <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> разделы конфигурации, используя метод для получения коллекции `GetSection("section1")` ключей в определенном месте с синтаксисом, аналогичным для получения конфигурации для раздела 1 из предыдущего примера.</span><span class="sxs-lookup"><span data-stu-id="92aca-169">You can fetch entire configuration sections by using the <xref:Microsoft.Extensions.Configuration.IConfiguration.GetSection%2A> method to retrieve a collection of keys at a specific location with a syntax similar to `GetSection("section1")` to retrieve the configuration for section1 from the earlier example.</span></span>

## <a name="strongly-typed-configuration"></a><span data-ttu-id="92aca-170">Сильно набранная конфигурация</span><span class="sxs-lookup"><span data-stu-id="92aca-170">Strongly typed configuration</span></span>

<span data-ttu-id="92aca-171">С помощью Web Forms можно было создать сильно набранный <xref:System.Configuration.ConfigurationSection> тип конфигурации, унаследованный от типа и связанных типов.</span><span class="sxs-lookup"><span data-stu-id="92aca-171">With Web Forms, it was possible to create a strongly typed configuration type that inherited from the <xref:System.Configuration.ConfigurationSection> type and associated types.</span></span> <span data-ttu-id="92aca-172">Позволяет `ConfigurationSection` настроить некоторые бизнес-правила и обработку для этих значений конфигурации.</span><span class="sxs-lookup"><span data-stu-id="92aca-172">A `ConfigurationSection` allowed you to configure some business rules and processing for those configuration values.</span></span>

<span data-ttu-id="92aca-173">В ASP.NET Core можно указать иерархию классов, которая будет получать значения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="92aca-173">In ASP.NET Core, you can specify a class hierarchy that will receive the configuration values.</span></span> <span data-ttu-id="92aca-174">Эти классы:</span><span class="sxs-lookup"><span data-stu-id="92aca-174">These classes:</span></span>

* <span data-ttu-id="92aca-175">Не нужно наследовать от родительского класса.</span><span class="sxs-lookup"><span data-stu-id="92aca-175">Don't need to inherit from a parent class.</span></span>
* <span data-ttu-id="92aca-176">Следует `public` включать свойства, которые соответствуют свойствам и ссылкам на тип ы для структуры конфигурации, которую вы хотите захватить.</span><span class="sxs-lookup"><span data-stu-id="92aca-176">Should include `public` properties that match the properties and type references for the configuration structure you wish to capture.</span></span>

<span data-ttu-id="92aca-177">Для более раннего образца *appsettings.json* можно определить следующие классы для захвата значений:</span><span class="sxs-lookup"><span data-stu-id="92aca-177">For the earlier *appsettings.json* sample, you could define the following classes to capture the values:</span></span>

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

<span data-ttu-id="92aca-178">Эта иерархия классов может быть засена, добавляя следующую строку к методу: `Startup.ConfigureServices`</span><span class="sxs-lookup"><span data-stu-id="92aca-178">This class hierarchy can be populated by adding the following line to the `Startup.ConfigureServices` method:</span></span>

```csharp
services.Configure<MyConfig>(Configuration);
```

<span data-ttu-id="92aca-179">В остальной части приложения можно добавить параметр ввода в классы или директиву `@inject` в шаблонах типа `IOptions<MyConfig>` Razor для получения сильно набранных параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="92aca-179">In the rest of the app, you can add an input parameter to classes or an `@inject` directive in Razor templates of type `IOptions<MyConfig>` to receive the strongly typed configuration settings.</span></span> <span data-ttu-id="92aca-180">Свойство `IOptions<MyConfig>.Value` даст `MyConfig` значение, заселенное настройками конфигурации.</span><span class="sxs-lookup"><span data-stu-id="92aca-180">The `IOptions<MyConfig>.Value` property will yield the `MyConfig` value populated from the configuration settings.</span></span>

```razor
@inject IOptions<MyConfig> options
@code {
    var MyConfiguration = options.Value;
    var theSetting = MyConfiguration.section1.key0;
}
```

<span data-ttu-id="92aca-181">Более подробную информацию о функции Options можно найти в [шаблоне Options в ASP.NET core](/aspnet/core/fundamentals/configuration/options#options-interfaces) документе.</span><span class="sxs-lookup"><span data-stu-id="92aca-181">More information about the Options feature can be found in the [Options pattern in ASP.NET Core](/aspnet/core/fundamentals/configuration/options#options-interfaces) document.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="92aca-182">[Назад](middleware.md)
>[Вперед](security-authentication-authorization.md)</span><span class="sxs-lookup"><span data-stu-id="92aca-182">[Previous](middleware.md)
[Next](security-authentication-authorization.md)</span></span>
