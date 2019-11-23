---
title: Самостоятельные приложения gRPC — gRPC для разработчиков WCF
description: Развертывание ASP.NET Core gRPC приложений как самостоятельных служб.
ms.date: 09/02/2019
ms.openlocfilehash: 59f6275dbf85442bca3a98a1521597ef40e9675b
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73967211"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="ec79f-103">Приложения gRPC с самостоятельным размещением</span><span class="sxs-lookup"><span data-stu-id="ec79f-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="ec79f-104">Несмотря на то, что приложения ASP.NET Core 3,0 могут размещаться в IIS в Windows Server, в настоящее время невозможно разместить приложение gRPC в IIS, так как некоторые функции HTTP/2 еще не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="ec79f-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't yet supported.</span></span> <span data-ttu-id="ec79f-105">Эта функция ожидается в будущем обновлении Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ec79f-105">This functionality is expected in a future update to Windows Server.</span></span>

<span data-ttu-id="ec79f-106">Вы можете запустить приложение как службу Windows или как службу Linux, управляемую [системой](https://en.wikipedia.org/wiki/Systemd), благодаря некоторым новым функциям в расширениях размещения .net Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="ec79f-106">You can run your application as a Windows Service, or as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), thanks to some new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="ec79f-107">Запуск приложения как службы Windows</span><span class="sxs-lookup"><span data-stu-id="ec79f-107">Run your app as a Windows service</span></span>

<span data-ttu-id="ec79f-108">Чтобы настроить приложение ASP.NET Core для работы в качестве службы Windows, установите пакет [Microsoft. Extensions. Hosting. службы Windows](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) из NuGet.</span><span class="sxs-lookup"><span data-stu-id="ec79f-108">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="ec79f-109">Затем добавьте вызов `UseWindowsService` в метод `CreateHostBuilder` в `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="ec79f-109">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseWindowsService() // Enable running as a Windows service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="ec79f-110">Если приложение не работает как служба Windows, метод `UseWindowsService` не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="ec79f-110">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="ec79f-111">Теперь опубликуйте приложение из Visual Studio, щелкнув проект правой кнопкой мыши и выбрав пункт *опубликовать* в контекстном меню или .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="ec79f-111">Now publish your application, either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI.</span></span>

<span data-ttu-id="ec79f-112">При публикации приложения .NET Core можно создать *зависимое от платформы* развертывание или *автономное* развертывание.</span><span class="sxs-lookup"><span data-stu-id="ec79f-112">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="ec79f-113">Для развертываний, зависящих от платформы, требуется, чтобы общая среда выполнения .NET Core была установлена на узле, где они выполняются.</span><span class="sxs-lookup"><span data-stu-id="ec79f-113">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="ec79f-114">Автономные развертывания публикуются с полной копией среды выполнения и платформы .NET Core и могут выполняться на любом узле.</span><span class="sxs-lookup"><span data-stu-id="ec79f-114">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="ec79f-115">Дополнительные сведения, включая преимущества и недостатки каждого подхода, см. в документации по [развертыванию приложений .NET Core](https://docs.microsoft.com/dotnet/core/deploying/) .</span><span class="sxs-lookup"><span data-stu-id="ec79f-115">For more information, including the advantages and disadvantages of each approach, refer to the [.NET Core application deployment](https://docs.microsoft.com/dotnet/core/deploying/) documentation.</span></span>

<span data-ttu-id="ec79f-116">Чтобы опубликовать автономную сборку приложения, которая не требует установки среды выполнения .NET Core 3,0 на узле, укажите среду выполнения, которая будет включена в приложение, используя флаг `-r` (или `--runtime`).</span><span class="sxs-lookup"><span data-stu-id="ec79f-116">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application using the `-r` (or `--runtime`) flag.</span></span>

```console
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="ec79f-117">Чтобы опубликовать сборку, зависящую от платформы, опустите флаг `-r`.</span><span class="sxs-lookup"><span data-stu-id="ec79f-117">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```console
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="ec79f-118">Скопируйте полное содержимое каталога `publish` в папку установки и используйте [служебную программу SC](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) для создания службы Windows для исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="ec79f-118">Copy the complete contents of the `publish` directory to an installation folder, and use the [sc utility](https://docs.microsoft.com/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-windows-event-log"></a><span data-ttu-id="ec79f-119">Журнал событий Windows</span><span class="sxs-lookup"><span data-stu-id="ec79f-119">Log to Windows Event Log</span></span>

<span data-ttu-id="ec79f-120">Метод `UseWindowsService` автоматически добавляет поставщик [ведения журнала](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) , записывающий сообщения журнала в журнал событий Windows.</span><span class="sxs-lookup"><span data-stu-id="ec79f-120">The `UseWindowsService` method automatically adds a [Logging](https://docs.microsoft.com/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0) provider that writes log messages to the Windows Event Log.</span></span> <span data-ttu-id="ec79f-121">Вы можете настроить ведение журнала для этого поставщика, добавив запись `EventLog` в раздел `Logging` в `appsettings.json` или другом источнике конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec79f-121">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or other configuration source.</span></span> <span data-ttu-id="ec79f-122">Исходное имя, используемое в журнале событий, можно переопределить, задав свойство `SourceName` в этих параметрах. Если не указать имя, будет использоваться имя приложения по умолчанию (обычно имя исполняемой сборки).</span><span class="sxs-lookup"><span data-stu-id="ec79f-122">The source name used in Event Log can be overridden by setting a `SourceName` property in these settings; if you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="ec79f-123">Дополнительные сведения о ведении журнала приведены в конце этой главы.</span><span class="sxs-lookup"><span data-stu-id="ec79f-123">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="ec79f-124">Запуск приложения как службы Linux с помощью системы</span><span class="sxs-lookup"><span data-stu-id="ec79f-124">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="ec79f-125">Чтобы настроить приложение ASP.NET Core для работы в качестве службы Linux (или *управляющей* программы в Linux терминах), установите пакет [Microsoft. Extensions. Hosting. System](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) из NuGet.</span><span class="sxs-lookup"><span data-stu-id="ec79f-125">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="ec79f-126">Затем добавьте вызов `UseSystemd` в метод `CreateHostBuilder` в `Program.cs`.</span><span class="sxs-lookup"><span data-stu-id="ec79f-126">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .UseSystemd() // Enable running as a Systemd service
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
        });
```

> [!NOTE]
> <span data-ttu-id="ec79f-127">Если приложение не работает как служба Linux, метод `UseSystemd` не выполняет никаких действий.</span><span class="sxs-lookup"><span data-stu-id="ec79f-127">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="ec79f-128">Теперь опубликуйте приложение (зависящее от платформы или автономно для соответствующей среды выполнения Linux, например `linux-x64`), либо из Visual Studio, щелкнув проект правой кнопкой мыши и выбрав пункт *опубликовать* в контекстном меню, либо из .NET Core CLI с помощью следующей команды.</span><span class="sxs-lookup"><span data-stu-id="ec79f-128">Now publish your application (either framework-dependent, or self-contained for the relevant Linux runtime, e.g. `linux-x64`), either from Visual Studio by right-clicking the project and choosing *Publish* from the context menu, or from the .NET Core CLI using the following command.</span></span>

```console
dotnet publish -c Release -r linux-x64 -o ./publish
```

<span data-ttu-id="ec79f-129">Скопируйте полное содержимое каталога `publish` в папку установки на узле Linux.</span><span class="sxs-lookup"><span data-stu-id="ec79f-129">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="ec79f-130">Для регистрации службы требуется специальный файл, называемый "файлом единицы", для добавления в каталог `/etc/systemd/system`.</span><span class="sxs-lookup"><span data-stu-id="ec79f-130">Registering the service requires a special file, called a "unit file", to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="ec79f-131">Для создания файла в этой папке необходимо разрешение root.</span><span class="sxs-lookup"><span data-stu-id="ec79f-131">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="ec79f-132">Присвойте файлу имя, которое будет использоваться `systemd` и расширением `.service`.</span><span class="sxs-lookup"><span data-stu-id="ec79f-132">Name the file with the identifier you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="ec79f-133">Например, `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="ec79f-133">For example, `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="ec79f-134">Файл службы использует формат INI, как показано в этом примере.</span><span class="sxs-lookup"><span data-stu-id="ec79f-134">The service file uses INI format, as shown in this example.</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="ec79f-135">Свойство `Type=notify` указывает `systemd`, что приложение будет уведомлять его при запуске и завершении работы.</span><span class="sxs-lookup"><span data-stu-id="ec79f-135">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="ec79f-136">Параметр `WantedBy=multi-user.target` приведет к запуску службы при достижении системой Linux "runlevel 2", то есть активной неграфической оболочки с несколькими пользователями.</span><span class="sxs-lookup"><span data-stu-id="ec79f-136">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2", meaning a non-graphical multi-user shell is active.</span></span>

<span data-ttu-id="ec79f-137">Прежде чем `systemd` распознает службу, необходимо перезагрузить ее конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="ec79f-137">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="ec79f-138">Управление `systemd` осуществляется с помощью команды `systemctl`.</span><span class="sxs-lookup"><span data-stu-id="ec79f-138">You control `systemd` using the `systemctl` command.</span></span> <span data-ttu-id="ec79f-139">После перезагрузки используйте подкоманду `status`, чтобы убедиться, что приложение успешно зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="ec79f-139">After reloading, use the `status` subcommand to confirm the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="ec79f-140">Если служба настроена правильно, будут отображены следующие выходные данные:</span><span class="sxs-lookup"><span data-stu-id="ec79f-140">If you've configured the service correctly, the following output will be shown:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="ec79f-141">Для запуска службы используйте команду `start`.</span><span class="sxs-lookup"><span data-stu-id="ec79f-141">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="ec79f-142">При использовании `systemctl start`расширение `.service` необязательно.</span><span class="sxs-lookup"><span data-stu-id="ec79f-142">The `.service` extension is optional when using `systemctl start`.</span></span>

<span data-ttu-id="ec79f-143">Чтобы указать `systemd` запускать службу автоматически при запуске системы, используйте команду `enable`.</span><span class="sxs-lookup"><span data-stu-id="ec79f-143">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="ec79f-144">Регистрация в журнале</span><span class="sxs-lookup"><span data-stu-id="ec79f-144">Log to journald</span></span>

<span data-ttu-id="ec79f-145">Аналогом журнала событий Windows в Linux является `journald`, структурированная системная служба ведения журналов, входящая в `systemd`.</span><span class="sxs-lookup"><span data-stu-id="ec79f-145">The Linux equivalent of the Windows Event Log is `journald`, a structured logging system service that is part of `systemd`.</span></span> <span data-ttu-id="ec79f-146">Сообщения журнала, записанные в стандартный вывод управляющей программой Linux, автоматически записываются в `journald`, поэтому для настройки уровней ведения журнала используйте раздел `Console` конфигурации ведения журнала.</span><span class="sxs-lookup"><span data-stu-id="ec79f-146">Log messages written to the standard output by a Linux daemon are automatically written to `journald`, so to configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="ec79f-147">Метод построителя `UseSystemd` узла автоматически настраивает формат вывода консоли в соответствии с журналом.</span><span class="sxs-lookup"><span data-stu-id="ec79f-147">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="ec79f-148">Поскольку `journald` является стандартом для журналов Linux, существует множество средств, которые интегрируются с ним, и вы можете легко маршрутизировать журналы из `journald` во внешнюю систему ведения журналов.</span><span class="sxs-lookup"><span data-stu-id="ec79f-148">Because `journald` is the standard for Linux logs, there are a variety of tools that integrate with it, and you can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="ec79f-149">Работая локально на узле, можно использовать команду `journalctl` для просмотра журналов из командной строки.</span><span class="sxs-lookup"><span data-stu-id="ec79f-149">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="ec79f-150">Если на вашем узле доступна среда графического пользовательского интерфейса, для Linux доступны несколько графических средств просмотра журналов, таких как *кжаурналктл* и *GNOME-Logs*.</span><span class="sxs-lookup"><span data-stu-id="ec79f-150">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="ec79f-151">Дополнительные сведения о запросе системного журнала из командной строки с `journalctl`см. [на справочных страницах](https://manpages.debian.org/buster/systemd/journalctl.1).</span><span class="sxs-lookup"><span data-stu-id="ec79f-151">To learn more about querying the systemd journal from the command line with `journalctl`, see [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="ec79f-152">HTTPS-сертификаты для приложений, размещаемых в собственном размещении</span><span class="sxs-lookup"><span data-stu-id="ec79f-152">HTTPS Certificates for self-hosted applications</span></span>

<span data-ttu-id="ec79f-153">При запуске приложения gRPC в рабочей среде следует использовать сертификат TLS из доверенного центра сертификации (ЦС).</span><span class="sxs-lookup"><span data-stu-id="ec79f-153">When running a gRPC application in production, you should use a TLS certificate from a trusted Certificate Authority (CA).</span></span> <span data-ttu-id="ec79f-154">Этот ЦС может быть общедоступным или внутренним центром для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ec79f-154">This CA could be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="ec79f-155">На узлах Windows сертификат может быть загружен из защищенного [хранилища сертификатов](https://docs.microsoft.com/windows/win32/seccrypto/managing-certificates-with-certificate-stores) с помощью [класса X509Store](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509store?view=netcore-3.0).</span><span class="sxs-lookup"><span data-stu-id="ec79f-155">On Windows hosts, the certificate may be loaded from a secure [Certificate Store](https://docs.microsoft.com/windows/win32/seccrypto/managing-certificates-with-certificate-stores) using the [X509Store class](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509store?view=netcore-3.0).</span></span> <span data-ttu-id="ec79f-156">Класс `X509Store` также можно использовать с хранилищем ключей OpenSSL на некоторых узлах Linux.</span><span class="sxs-lookup"><span data-stu-id="ec79f-156">The `X509Store` class can also be used with the OpenSSL key-store on some Linux hosts.</span></span>

<span data-ttu-id="ec79f-157">Сертификаты также могут быть созданы с помощью одного из [конструкторов X509Certificate2](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0)либо из файла (например, `.pfx` файла, защищенного надежным паролем), либо из двоичных данных, полученных из службы безопасного хранения, например [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span><span class="sxs-lookup"><span data-stu-id="ec79f-157">Certificates may also be created using one of the [X509Certificate2 constructors](https://docs.microsoft.com/dotnet/api/system.security.cryptography.x509certificates.x509certificate.-ctor?view=netcore-3.0), either from a file (for example a `.pfx` file protected by a strong password), or from binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/).</span></span>

<span data-ttu-id="ec79f-158">Kestrel можно настроить для использования сертификата двумя способами: из конфигурации или в коде.</span><span class="sxs-lookup"><span data-stu-id="ec79f-158">Kestrel can be configured to use a certificate in two ways: from configuration, or in code.</span></span>

### <a name="set-https-certificates-using-configuration"></a><span data-ttu-id="ec79f-159">Настройка сертификатов HTTPS с помощью конфигурации</span><span class="sxs-lookup"><span data-stu-id="ec79f-159">Set HTTPS certificates using configuration</span></span>

<span data-ttu-id="ec79f-160">Подход к настройке требует установки пути к сертификату `.pfx` файл и пароль в разделе конфигурации Kestrel.</span><span class="sxs-lookup"><span data-stu-id="ec79f-160">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="ec79f-161">В `appsettings.json`, который будет выглядеть следующим образом.</span><span class="sxs-lookup"><span data-stu-id="ec79f-161">In `appsettings.json` that would look like this.</span></span>

```json
{
  "Kestrel": {
    "Certificates": {
      "Default": {
        "Path": "cert.pfx",
        "Password": "DO NOT STORE PLAINTEXT PASSWORDS IN APPSETTINGS FILES"
      }
    }
  }
}
```

<span data-ttu-id="ec79f-162">Пароль должен быть предоставлен с помощью безопасного источника конфигурации, такого как Azure KeyVault или Hashicorp Vault.</span><span class="sxs-lookup"><span data-stu-id="ec79f-162">The password should be provided using a secure configuration source such as Azure KeyVault or Hashicorp Vault.</span></span>

<span data-ttu-id="ec79f-163">НЕ храните незашифрованные пароли в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec79f-163">You SHOULD NOT store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="ec79f-164">Настройка сертификатов HTTPS в коде</span><span class="sxs-lookup"><span data-stu-id="ec79f-164">Set HTTPS certificates in code</span></span>

<span data-ttu-id="ec79f-165">Чтобы настроить HTTPS для Kestrel в коде, используйте метод `ConfigureKestrel` для `IWebHostBuilder` в классе `Program`.</span><span class="sxs-lookup"><span data-stu-id="ec79f-165">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

```csharp
public static IHostBuilder CreateHostBuilder(string[] args) =>
    Host.CreateDefaultBuilder(args)
        .ConfigureWebHostDefaults(webBuilder =>
        {
            webBuilder.UseStartup<Startup>();
            webBuilder.ConfigureKestrel(kestrel =>
            {
                kestrel.ConfigureHttpsDefaults(https =>
                {
                    https.ServerCertificate = new X509Certificate2("mycert.pfx", "password");
                });
            });
        });
```

<span data-ttu-id="ec79f-166">Пароль для файла `.pfx` должен храниться и извлекаться из безопасного источника конфигурации.</span><span class="sxs-lookup"><span data-stu-id="ec79f-166">Again, the password for the `.pfx` file should be stored in and retrieved from a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="ec79f-167">[Назад](grpc-in-production.md)
>[Вперед](docker.md)</span><span class="sxs-lookup"><span data-stu-id="ec79f-167">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
