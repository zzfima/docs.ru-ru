---
title: Самохозня gRPC приложений - gRPC для разработчиков WCF
description: Развертывание ASP.NET приложений Core gRPC в качестве самостоятельных сервисов.
ms.date: 09/02/2019
ms.openlocfilehash: 69f70e4077247fd07eba7abeee82f257dd1f4f90
ms.sourcegitcommit: 267d092663aba36b6b2ea853034470aea493bfae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/21/2020
ms.locfileid: "80110910"
---
# <a name="self-hosted-grpc-applications"></a><span data-ttu-id="988db-103">Самохлажен gRPC приложений</span><span class="sxs-lookup"><span data-stu-id="988db-103">Self-hosted gRPC applications</span></span>

<span data-ttu-id="988db-104">Хотя ASP.NET приложения Core 3.0 могут быть размещены в IIS на Windows Server, в настоящее время невозможно разместить приложение gRPC в IIS, потому что некоторые функции HTTP/2 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="988db-104">Although ASP.NET Core 3.0 applications can be hosted in IIS on Windows Server, currently it isn't possible to host a gRPC application in IIS because some of the HTTP/2 functionality isn't supported.</span></span> <span data-ttu-id="988db-105">Эта функциональность является целью для будущего обновления Windows Server.</span><span class="sxs-lookup"><span data-stu-id="988db-105">This functionality is a goal for a future update to Windows Server.</span></span>

<span data-ttu-id="988db-106">Вы можете запустить приложение как службу Windows.</span><span class="sxs-lookup"><span data-stu-id="988db-106">You can run your application as a Windows service.</span></span> <span data-ttu-id="988db-107">Или вы можете запустить его как сервис Linux, управляемый [системным,](https://en.wikipedia.org/wiki/Systemd)из-за новых функций в расширениях хостинга .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="988db-107">Or you can run it as a Linux service controlled by [systemd](https://en.wikipedia.org/wiki/Systemd), because of new features in the .NET Core 3.0 hosting extensions.</span></span>

## <a name="run-your-app-as-a-windows-service"></a><span data-ttu-id="988db-108">Запустите приложение в качестве службы Windows</span><span class="sxs-lookup"><span data-stu-id="988db-108">Run your app as a Windows service</span></span>

<span data-ttu-id="988db-109">Чтобы настроить приложение ASP.NET Core для запуска в качестве службы Windows, установите пакет [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) от NuGet.</span><span class="sxs-lookup"><span data-stu-id="988db-109">To configure your ASP.NET Core application to run as a Windows service, install the [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) package from NuGet.</span></span> <span data-ttu-id="988db-110">Затем добавьте `UseWindowsService` вызов `CreateHostBuilder` к `Program.cs`методу в .</span><span class="sxs-lookup"><span data-stu-id="988db-110">Then add a call to `UseWindowsService` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="988db-111">Если приложение не работает как служба Windows, `UseWindowsService` метод ничего не делает.</span><span class="sxs-lookup"><span data-stu-id="988db-111">If the application isn't running as a Windows service, the `UseWindowsService` method doesn't do anything.</span></span>

<span data-ttu-id="988db-112">Теперь опубликуйте приложение с помощью одного из этих методов:</span><span class="sxs-lookup"><span data-stu-id="988db-112">Now publish your application by using one of these methods:</span></span>

* <span data-ttu-id="988db-113">От Visual Studio, нажав на проект вправо и выбрав **Publish** в меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="988db-113">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="988db-114">Из .NET Core CLI.</span><span class="sxs-lookup"><span data-stu-id="988db-114">From the .NET Core CLI.</span></span>

<span data-ttu-id="988db-115">При публикации приложения .NET Core можно создать *развертывание, зависящий от инфраструктуры,* или *автономное* развертывание.</span><span class="sxs-lookup"><span data-stu-id="988db-115">When you publish a .NET Core application, you can choose to create a *framework-dependent* deployment or a *self-contained* deployment.</span></span> <span data-ttu-id="988db-116">Развертывание, зависяе от рамок, требует установки общего времени выполнения .NET Core на унитаз, где они запущены.</span><span class="sxs-lookup"><span data-stu-id="988db-116">Framework-dependent deployments require the .NET Core Shared Runtime to be installed on the host where they are run.</span></span> <span data-ttu-id="988db-117">Автономные развертывания публикуются с полной копией времени выполнения и фреймворка .NET Core и могут выполняться на любом узлах.</span><span class="sxs-lookup"><span data-stu-id="988db-117">Self-contained deployments are published with a complete copy of the .NET Core runtime and framework and can be run on any host.</span></span> <span data-ttu-id="988db-118">Для получения дополнительной информации, включая преимущества и [.NET Core application deployment](../../core/deploying/index.md) недостатки каждого подхода, см.</span><span class="sxs-lookup"><span data-stu-id="988db-118">For more information, including the advantages and disadvantages of each approach, see the [.NET Core application deployment](../../core/deploying/index.md) documentation.</span></span>

<span data-ttu-id="988db-119">Чтобы опубликовать автономную сборку приложения, которая не требует установки времени выполнения .NET Core 3.0 на узел, укажите время выполнения, которое будет включено в приложение.</span><span class="sxs-lookup"><span data-stu-id="988db-119">To publish a self-contained build of the application that does not require the .NET Core 3.0 runtime to be installed on the host, specify the runtime to be included with the application.</span></span> <span data-ttu-id="988db-120">Используйте `-r` (или) `--runtime`флаг.</span><span class="sxs-lookup"><span data-stu-id="988db-120">Use the `-r` (or `--runtime`) flag.</span></span>

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

<span data-ttu-id="988db-121">Чтобы опубликовать построение, зависящий `-r` от фреймворка, опустите флаг.</span><span class="sxs-lookup"><span data-stu-id="988db-121">To publish a framework-dependent build, omit the `-r` flag.</span></span>

```dotnetcli
dotnet publish -c Release -o ./publish
```

<span data-ttu-id="988db-122">Копируйте полное `publish` содержимое каталога в папку установки.</span><span class="sxs-lookup"><span data-stu-id="988db-122">Copy the complete contents of the `publish` directory to an installation folder.</span></span> <span data-ttu-id="988db-123">Затем используйте [инструмент sc](/windows/desktop/services/controlling-a-service-using-sc) для создания службы Windows для исполняемого файла.</span><span class="sxs-lookup"><span data-stu-id="988db-123">Then, use the [sc tool](/windows/desktop/services/controlling-a-service-using-sc) to create a Windows service for the executable file.</span></span>

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a><span data-ttu-id="988db-124">Войти в журнал событий Windows</span><span class="sxs-lookup"><span data-stu-id="988db-124">Log to the Windows event log</span></span>

<span data-ttu-id="988db-125">Метод `UseWindowsService` автоматически добавляет поставщика [журналов,](/aspnet/core/fundamentals/logging/) который записывает сообщения журнала в журнал событий Windows.</span><span class="sxs-lookup"><span data-stu-id="988db-125">The `UseWindowsService` method automatically adds a [logging](/aspnet/core/fundamentals/logging/) provider that writes log messages to the Windows event log.</span></span> <span data-ttu-id="988db-126">Вы можете настроить журнал для этого `EventLog` поставщика, `Logging` добавив `appsettings.json` запись в раздел или другой источник конфигурации.</span><span class="sxs-lookup"><span data-stu-id="988db-126">You can configure logging for this provider by adding an `EventLog` entry to the `Logging` section of `appsettings.json` or another configuration source.</span></span>

<span data-ttu-id="988db-127">Вы можете переопределить имя источника, используемое `SourceName` в журнале событий, установив свойство в этих настройках.</span><span class="sxs-lookup"><span data-stu-id="988db-127">You can override the source name used in the event log by setting a `SourceName` property in these settings.</span></span> <span data-ttu-id="988db-128">Если вы не укажете имя, будет использовано имя приложения по умолчанию (обычно иное имя сборки).</span><span class="sxs-lookup"><span data-stu-id="988db-128">If you don't specify a name, the default application name (normally the executable assembly name) will be used.</span></span>

<span data-ttu-id="988db-129">Более подробная информация о лесозаготовках находится в конце этой главы.</span><span class="sxs-lookup"><span data-stu-id="988db-129">More information on logging is at the end of this chapter.</span></span>

## <a name="run-your-app-as-a-linux-service-with-systemd"></a><span data-ttu-id="988db-130">Запустите приложение как сервис Linux с системой</span><span class="sxs-lookup"><span data-stu-id="988db-130">Run your app as a Linux service with systemd</span></span>

<span data-ttu-id="988db-131">Чтобы настроить приложение ASP.NET Core для запуска в качестве службы Linux (или *daemon* на языке Linux), установите пакет [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) от NuGet.</span><span class="sxs-lookup"><span data-stu-id="988db-131">To configure your ASP.NET Core application to run as a Linux service (or *daemon* in Linux parlance), install the [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) package from NuGet.</span></span> <span data-ttu-id="988db-132">Затем добавьте `UseSystemd` вызов `CreateHostBuilder` к `Program.cs`методу в .</span><span class="sxs-lookup"><span data-stu-id="988db-132">Then add a call to `UseSystemd` to the `CreateHostBuilder` method in `Program.cs`.</span></span>

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
> <span data-ttu-id="988db-133">Если приложение не работает как служба Linux, `UseSystemd` метод ничего не делает.</span><span class="sxs-lookup"><span data-stu-id="988db-133">If the application isn't running as a Linux service, the `UseSystemd` method doesn't do anything.</span></span>

<span data-ttu-id="988db-134">Теперь опубликуйте свое заявление.</span><span class="sxs-lookup"><span data-stu-id="988db-134">Now publish your application.</span></span> <span data-ttu-id="988db-135">Приложение может быть либо зависимым от фреймворка, либо `linux-x64`автономным для соответствующего времени выполнения Linux (например, ).</span><span class="sxs-lookup"><span data-stu-id="988db-135">The application can be either framework dependent or self-contained for the relevant Linux runtime (for example, `linux-x64`).</span></span> <span data-ttu-id="988db-136">Вы можете опубликовать с помощью одного из этих методов:</span><span class="sxs-lookup"><span data-stu-id="988db-136">You can publish by using one of these methods:</span></span>

* <span data-ttu-id="988db-137">От Visual Studio, нажав на проект вправо и выбрав **Publish** в меню ярлыка.</span><span class="sxs-lookup"><span data-stu-id="988db-137">From Visual Studio by right-clicking the project and selecting **Publish** on the shortcut menu.</span></span>
* <span data-ttu-id="988db-138">Из .NET Core CLI, используя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="988db-138">From the .NET Core CLI, by using the following command:</span></span>

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
<span data-ttu-id="988db-139">Копируйте полное `publish` содержимое каталога в папку установки на хосте Linux.</span><span class="sxs-lookup"><span data-stu-id="988db-139">Copy the complete contents of the `publish` directory to an installation folder on the Linux host.</span></span> <span data-ttu-id="988db-140">Для регистрации службы требуется специальный файл, называемый `/etc/systemd/system` *файлом единицы,* который должен быть добавлен в каталог.</span><span class="sxs-lookup"><span data-stu-id="988db-140">Registering the service requires a special file, called a *unit file*, to be added to the `/etc/systemd/system` directory.</span></span> <span data-ttu-id="988db-141">Для создания файла в этой папке потребуется разрешение root.</span><span class="sxs-lookup"><span data-stu-id="988db-141">You'll need root permission to create a file in this folder.</span></span> <span data-ttu-id="988db-142">Назовите файл идентификатором, который вы хотите `systemd` использовать, и расширением. `.service`</span><span class="sxs-lookup"><span data-stu-id="988db-142">Name the file with the identifier that you want `systemd` to use and the `.service` extension.</span></span> <span data-ttu-id="988db-143">Например, воспользуйтесь `/etc/systemd/system/myapp.service`.</span><span class="sxs-lookup"><span data-stu-id="988db-143">For example, use `/etc/systemd/system/myapp.service`.</span></span>

<span data-ttu-id="988db-144">Файл службы использует формат INI, как показано в этом примере:</span><span class="sxs-lookup"><span data-stu-id="988db-144">The service file uses INI format, as shown in this example:</span></span>

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

<span data-ttu-id="988db-145">Свойство `Type=notify` `systemd` сообщает, что приложение уведомит его о запуске и остановке.</span><span class="sxs-lookup"><span data-stu-id="988db-145">The `Type=notify` property tells `systemd` that the application will notify it on startup and shutdown.</span></span> <span data-ttu-id="988db-146">Настройка `WantedBy=multi-user.target` приведет к запуску службы, когда система Linux достигнет "уровня 2", что означает активную неграфическую, многопользовательскую оболочку.</span><span class="sxs-lookup"><span data-stu-id="988db-146">The `WantedBy=multi-user.target` setting will cause the service to start when the Linux system reaches "runlevel 2," which means a non-graphical, multi-user shell is active.</span></span>

<span data-ttu-id="988db-147">Прежде `systemd` чем распознать службу, ей необходимо перезагрузить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="988db-147">Before `systemd` will recognize the service, it needs to reload its configuration.</span></span> <span data-ttu-id="988db-148">Вы `systemd` управляете `systemctl` с помощью команды.</span><span class="sxs-lookup"><span data-stu-id="988db-148">You control `systemd` by using the `systemctl` command.</span></span> <span data-ttu-id="988db-149">После перезагрузки `status` используйте подкоманду, чтобы подтвердить, что приложение успешно зарегистрировано.</span><span class="sxs-lookup"><span data-stu-id="988db-149">After reloading, use the `status` subcommand to confirm that the application has registered successfully.</span></span>

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

<span data-ttu-id="988db-150">Если вы правильно настроили службу, вы получите следующий вывод:</span><span class="sxs-lookup"><span data-stu-id="988db-150">If you've configured the service correctly, you'll get the following output:</span></span>

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

<span data-ttu-id="988db-151">Используйте `start` команду, чтобы запустить службу.</span><span class="sxs-lookup"><span data-stu-id="988db-151">Use the `start` command to start the service.</span></span>

```console
sudo systemctl start myapp.service
```

> [!TIP]
> <span data-ttu-id="988db-152">Расширение `.service` не является обязательным при `systemctl start`использовании.</span><span class="sxs-lookup"><span data-stu-id="988db-152">The `.service` extension is optional when you're using `systemctl start`.</span></span>

<span data-ttu-id="988db-153">Чтобы `systemd` сказать, чтобы запустить службу автоматически `enable` на запуск системы, используйте команду.</span><span class="sxs-lookup"><span data-stu-id="988db-153">To tell `systemd` to start the service automatically on system startup, use the `enable` command.</span></span>

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a><span data-ttu-id="988db-154">Войти в журнал</span><span class="sxs-lookup"><span data-stu-id="988db-154">Log to journald</span></span>

<span data-ttu-id="988db-155">Linux эквивалент журнала событий Windows `journald`является , структурированная система регистрации `systemd`системы, которая является частью .</span><span class="sxs-lookup"><span data-stu-id="988db-155">The Linux equivalent of the Windows event log is `journald`, a structured logging system service that's part of `systemd`.</span></span> <span data-ttu-id="988db-156">Сообщения журнала, написанные на стандартный выход Linux daemon, автоматически записываются. `journald`</span><span class="sxs-lookup"><span data-stu-id="988db-156">Log messages written to the standard output by a Linux daemon are automatically written to `journald`.</span></span> <span data-ttu-id="988db-157">Для настройки уровней `Console` регистрации используйте раздел конфигурации регистрации.</span><span class="sxs-lookup"><span data-stu-id="988db-157">To configure logging levels, use the `Console` section of the logging configuration.</span></span> <span data-ttu-id="988db-158">Метод `UseSystemd` разработчика хоста автоматически настраивает формат вывода консоли в соответствии с журналом.</span><span class="sxs-lookup"><span data-stu-id="988db-158">The `UseSystemd` host builder method automatically configures the console output format to suit the journal.</span></span>

<span data-ttu-id="988db-159">Поскольку `journald` это стандарт для журналов Linux, различные инструменты интегрируются с ним.</span><span class="sxs-lookup"><span data-stu-id="988db-159">Because `journald` is the standard for Linux logs, a variety of tools integrate with it.</span></span> <span data-ttu-id="988db-160">Вы можете легко маршрутировать журналы из `journald` внешней системы регистрации.</span><span class="sxs-lookup"><span data-stu-id="988db-160">You can easily route logs from `journald` to an external logging system.</span></span> <span data-ttu-id="988db-161">Работая локально на усе, `journalctl` можно использовать команду для просмотра журналов из командной строки.</span><span class="sxs-lookup"><span data-stu-id="988db-161">Working locally on the host, you can use the `journalctl` command to view logs from the command line.</span></span>

```console
sudo journalctl -u myapp
```

> [!TIP]
> <span data-ttu-id="988db-162">Если у вас есть среда GUI, доступная на вашем хосте, несколько графических журналов зрителей доступны для Linux, таких как *«Journalctl»* и *гном-журналы.*</span><span class="sxs-lookup"><span data-stu-id="988db-162">If you have a GUI environment available on your host, a few graphical log viewers are available for Linux, such as *QJournalctl* and *gnome-logs*.</span></span>

<span data-ttu-id="988db-163">Чтобы узнать больше о `systemd` запросе журнала из `journalctl`командной строки с помощью, см. [the manpages](https://manpages.debian.org/buster/systemd/journalctl.1)</span><span class="sxs-lookup"><span data-stu-id="988db-163">To learn more about querying the `systemd` journal from the command line by using `journalctl`, see [the manpages](https://manpages.debian.org/buster/systemd/journalctl.1).</span></span>

## <a name="https-certificates-for-self-hosted-applications"></a><span data-ttu-id="988db-164">Сертификаты HTTPS для самоходного размещения приложений</span><span class="sxs-lookup"><span data-stu-id="988db-164">HTTPS certificates for self-hosted applications</span></span>

<span data-ttu-id="988db-165">При запуске приложения gRPC в производстве следует использовать сертификат TLS от доверенного органа сертификата (CA).</span><span class="sxs-lookup"><span data-stu-id="988db-165">When you're running a gRPC application in production, you should use a TLS certificate from a trusted certificate authority (CA).</span></span> <span data-ttu-id="988db-166">Этот CA может быть общедоступным Ca или внутренним для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="988db-166">This CA might be a public CA, or an internal one for your organization.</span></span>

<span data-ttu-id="988db-167">На устройствах Windows можно загрузить сертификат из защищенного <xref:System.Security.Cryptography.X509Certificates.X509Store> [хранилища сертификатов,](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) используя класс.</span><span class="sxs-lookup"><span data-stu-id="988db-167">On Windows hosts, you can load the certificate from a secure [certificate store](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) by using the <xref:System.Security.Cryptography.X509Certificates.X509Store> class.</span></span> <span data-ttu-id="988db-168">Вы также можете `X509Store` использовать класс с ключевым магазином OpenSSL на некоторых хостах Linux.</span><span class="sxs-lookup"><span data-stu-id="988db-168">You can also use the `X509Store` class with the OpenSSL key store on some Linux hosts.</span></span>

<span data-ttu-id="988db-169">Вы также можете создать сертификаты, используя один из [конструкторов X509Certificate2,](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)от любого из:</span><span class="sxs-lookup"><span data-stu-id="988db-169">You can also create certificates by using one of the [X509Certificate2 constructors](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A), from either:</span></span>

* <span data-ttu-id="988db-170">Файл, например `.pfx` файл, защищенный сильным паролем</span><span class="sxs-lookup"><span data-stu-id="988db-170">A file, such as a `.pfx` file protected by a strong password</span></span>
* <span data-ttu-id="988db-171">Двоичные данные, извлеченные из службы безопасного хранения, такой как [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="988db-171">Binary data retrieved from a secure storage service such as [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)</span></span>

<span data-ttu-id="988db-172">Можно настроить Kestrel для использования сертификата двумя способами: от конфигурации или в коде.</span><span class="sxs-lookup"><span data-stu-id="988db-172">You can configure Kestrel to use a certificate in two ways: from configuration or in code.</span></span>

### <a name="set-https-certificates-by-using-configuration"></a><span data-ttu-id="988db-173">Установите сертификаты HTTPS с помощью конфигурации</span><span class="sxs-lookup"><span data-stu-id="988db-173">Set HTTPS certificates by using configuration</span></span>

<span data-ttu-id="988db-174">Подход конфигурации требует настройки `.pfx` пути к файлу сертификата и паролю в разделе конфигурации Kestrel.</span><span class="sxs-lookup"><span data-stu-id="988db-174">The configuration approach requires setting the path to the certificate `.pfx` file and the password in the Kestrel configuration section.</span></span> <span data-ttu-id="988db-175">В `appsettings.json`, что будет выглядеть следующим образом:</span><span class="sxs-lookup"><span data-stu-id="988db-175">In `appsettings.json`, that would look like this:</span></span>

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

<span data-ttu-id="988db-176">Предоставьте пароль с помощью безопасного источника конфигурации, такого как Azure Key Vault или Hashicorp Vault.</span><span class="sxs-lookup"><span data-stu-id="988db-176">Provide the password by using a secure configuration source such as Azure Key Vault or Hashicorp Vault.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="988db-177">Не храните незашифрованные пароли в файлах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="988db-177">Don't store unencrypted passwords in configuration files.</span></span>

### <a name="set-https-certificates-in-code"></a><span data-ttu-id="988db-178">Установка сертификатов HTTPS в коде</span><span class="sxs-lookup"><span data-stu-id="988db-178">Set HTTPS certificates in code</span></span>

<span data-ttu-id="988db-179">Чтобы настроить HTTPS на Kestrel в `ConfigureKestrel` `IWebHostBuilder` коде, `Program` используйте метод в классе.</span><span class="sxs-lookup"><span data-stu-id="988db-179">To configure HTTPS on Kestrel in code, use the `ConfigureKestrel` method on `IWebHostBuilder` in the `Program` class.</span></span>

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

<span data-ttu-id="988db-180">Опять же, не забудьте `.pfx` сохранить пароль для файла, и получить его из безопасного источника конфигурации.</span><span class="sxs-lookup"><span data-stu-id="988db-180">Again, be sure to store the password for the `.pfx` file in, and retrieve it from, a secure configuration source.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="988db-181">[Предыдущий](grpc-in-production.md)
>[Следующий](docker.md)</span><span class="sxs-lookup"><span data-stu-id="988db-181">[Previous](grpc-in-production.md)
[Next](docker.md)</span></span>
