---
title: Самохозня gRPC приложений - gRPC для разработчиков WCF
description: Развертывание ASP.NET приложений Core gRPC в качестве самостоятельных сервисов.
ms.date: 09/02/2019
ms.openlocfilehash: 00fb1453e19a02469f80af79672e0c1f72c7280f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79147806"
---
# <a name="self-hosted-grpc-applications"></a>Самохлажен gRPC приложений

Хотя ASP.NET приложения Core 3.0 могут быть размещены в IIS на Windows Server, в настоящее время невозможно разместить приложение gRPC в IIS, потому что некоторые функции HTTP/2 не поддерживаются. Эта функциональность является целью для будущего обновления Windows Server.

Вы можете запустить приложение как службу Windows. Или вы можете запустить его как сервис Linux, управляемый [системным,](https://en.wikipedia.org/wiki/Systemd)из-за новых функций в расширениях хостинга .NET Core 3.0.

## <a name="run-your-app-as-a-windows-service"></a>Запустите приложение в качестве службы Windows

Чтобы настроить приложение ASP.NET Core для запуска в качестве службы Windows, установите пакет [Microsoft.Extensions.Hosting.WindowsServices](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) от NuGet. Затем добавьте `UseWindowsService` вызов `CreateHostBuilder` к `Program.cs`методу в .

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
> Если приложение не работает как служба Windows, `UseWindowsService` метод ничего не делает.

Теперь опубликуйте приложение с помощью одного из этих методов:

* От Visual Studio, нажав на проект вправо и выбрав **Publish** в меню ярлыка.
* Из .NET Core CLI.

При публикации приложения .NET Core можно создать *развертывание, зависящий от инфраструктуры,* или *автономное* развертывание. Развертывание, зависяе от рамок, требует установки общего времени выполнения .NET Core на унитаз, где они запущены. Автономные развертывания публикуются с полной копией времени выполнения и фреймворка .NET Core и могут выполняться на любом узлах. Для получения дополнительной информации, включая преимущества и [.NET Core application deployment](../../core/deploying/index.md) недостатки каждого подхода, см.

Чтобы опубликовать автономную сборку приложения, которая не требует установки времени выполнения .NET Core 3.0 на узел, укажите время выполнения, которое будет включено в приложение. Используйте `-r` (или) `--runtime`флаг.

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

Чтобы опубликовать построение, зависящий `-r` от фреймворка, опустите флаг.

```dotnetcli
dotnet publish -c Release -o ./publish
```

Копируйте полное `publish` содержимое каталога в папку установки. Затем используйте [инструмент sc](/windows/desktop/services/controlling-a-service-using-sc) для создания службы Windows для исполняемого файла.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a>Войти в журнал событий Windows

Метод `UseWindowsService` автоматически добавляет поставщика [журналов,](/aspnet/core/fundamentals/logging/) который записывает сообщения журнала в журнал событий Windows. Вы можете настроить журнал для этого `EventLog` поставщика, `Logging` добавив `appsettings.json` запись в раздел или другой источник конфигурации.

Вы можете переопределить имя источника, используемое `SourceName` в журнале событий, установив свойство в этих настройках. Если вы не укажете имя, будет использовано имя приложения по умолчанию (обычно иное имя сборки).

Более подробная информация о лесозаготовках находится в конце этой главы.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>Запустите приложение как сервис Linux с системой

Чтобы настроить приложение ASP.NET Core для запуска в качестве службы Linux (или *daemon* на языке Linux), установите пакет [Microsoft.Extensions.Hosting.Systemd](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) от NuGet. Затем добавьте `UseSystemd` вызов `CreateHostBuilder` к `Program.cs`методу в .

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
> Если приложение не работает как служба Linux, `UseSystemd` метод ничего не делает.

Теперь опубликуйте свое заявление. Приложение может быть либо зависимым от фреймворка, либо `linux-x64`автономным для соответствующего времени выполнения Linux (например, ). Вы можете опубликовать с помощью одного из этих методов:

* От Visual Studio, нажав на проект вправо и выбрав **Publish** в меню ярлыка.
* Из .NET Core CLI, используя следующую команду:

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
  
Копируйте полное `publish` содержимое каталога в папку установки на хосте Linux. Для регистрации службы требуется специальный файл, называемый `/etc/systemd/system` *файлом единицы,* который должен быть добавлен в каталог. Для создания файла в этой папке потребуется разрешение root. Назовите файл идентификатором, который вы хотите `systemd` использовать, и расширением. `.service` Например, воспользуйтесь `/etc/systemd/system/myapp.service`.

Файл службы использует формат INI, как показано в этом примере:

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

Свойство `Type=notify` `systemd` сообщает, что приложение уведомит его о запуске и остановке. Настройка `WantedBy=multi-user.target` приведет к запуску службы, когда система Linux достигнет "уровня 2", что означает активную неграфическую многопользовательскую оболочку.

Прежде `systemd` чем распознать службу, ей необходимо перезагрузить конфигурацию. Вы `systemd` управляете `systemctl` с помощью команды. После перезагрузки `status` используйте подкоманду, чтобы подтвердить, что приложение успешно зарегистрировано.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

Если вы правильно настроили службу, вы получите следующий вывод:

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

Используйте `start` команду, чтобы запустить службу.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> Расширение `.service` не является обязательным при `systemctl start`использовании.

Чтобы `systemd` сказать, чтобы запустить службу автоматически `enable` на запуск системы, используйте команду.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>Войти в журнал

Linux эквивалент журнала событий Windows `journald`является , структурированная система регистрации `systemd`системы, которая является частью . Сообщения журнала, написанные на стандартный выход Linux daemon, автоматически записываются. `journald` Для настройки уровней `Console` регистрации используйте раздел конфигурации регистрации. Метод `UseSystemd` разработчика хоста автоматически настраивает формат вывода консоли в соответствии с журналом.

Поскольку `journald` это стандарт для журналов Linux, различные инструменты интегрируются с ним. Вы можете легко маршрутировать журналы из `journald` внешней системы регистрации. Работая локально на усе, `journalctl` можно использовать команду для просмотра журналов из командной строки.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Если у вас есть среда GUI, доступная на вашем хосте, несколько графических журналов зрителей доступны для Linux, таких как *«Journalctl»* и *гном-журналы.*

Чтобы узнать больше о `systemd` запросе журнала из `journalctl`командной строки с помощью, см. [the man pages](https://manpages.debian.org/buster/systemd/journalctl.1)

## <a name="https-certificates-for-self-hosted-applications"></a>Сертификаты HTTPS для самоходного размещения приложений

При запуске приложения gRPC в производстве следует использовать сертификат TLS от доверенного органа сертификата (CA). Этот CA может быть общедоступным Ca или внутренним для вашей организации.

На устройствах Windows можно загрузить сертификат из защищенного <xref:System.Security.Cryptography.X509Certificates.X509Store> [хранилища сертификатов,](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) используя класс. Вы также можете `X509Store` использовать класс с ключевым магазином OpenSSL на некоторых хостах Linux.

Вы также можете создать сертификаты, используя один из [конструкторов X509Certificate2,](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A)от любого из:

* Файл, например `.pfx` файл, защищенный сильным паролем
* Двоичные данные, извлеченные из службы безопасного хранения, такой как [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)

Можно настроить Kestrel для использования сертификата двумя способами: от конфигурации или в коде.

### <a name="set-https-certificates-by-using-configuration"></a>Установите сертификаты HTTPS с помощью конфигурации

Подход конфигурации требует настройки `.pfx` пути к файлу сертификата и паролю в разделе конфигурации Kestrel. В `appsettings.json`, что будет выглядеть следующим образом:

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

Предоставьте пароль с помощью безопасного источника конфигурации, такого как Azure Key Vault или Hashicorp Vault.

> [!IMPORTANT]
> Не храните незашифрованные пароли в файлах конфигурации.

### <a name="set-https-certificates-in-code"></a>Установка сертификатов HTTPS в коде

Чтобы настроить HTTPS на Kestrel в `ConfigureKestrel` `IWebHostBuilder` коде, `Program` используйте метод в классе.

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

Опять же, не забудьте `.pfx` сохранить пароль для файла, и получить его из безопасного источника конфигурации.

>[!div class="step-by-step"]
>[Предыдущий](grpc-in-production.md)
>[Следующий](docker.md)
