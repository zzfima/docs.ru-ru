---
title: Самостоятельные приложения gRPC — gRPC для разработчиков WCF
description: Развертывание ASP.NET Core gRPC приложений как самостоятельных служб.
ms.date: 09/02/2019
ms.openlocfilehash: 2244f161ad4b5d60138ae0f7b4d6a9c8c8829aa8
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503398"
---
# <a name="self-hosted-grpc-applications"></a>Приложения gRPC с самостоятельным размещением

Несмотря на то, что приложения ASP.NET Core 3,0 могут размещаться в IIS в Windows Server, в настоящее время невозможно разместить приложение gRPC в IIS, так как некоторые функции HTTP/2 не поддерживаются. Эта функция является целью для будущего обновления Windows Server.

Приложение можно запустить как службу Windows. Вы также можете запустить его как службу Linux, управляемую [системой](https://en.wikipedia.org/wiki/Systemd), из-за новых возможностей в расширениях размещения .net Core 3,0.

## <a name="run-your-app-as-a-windows-service"></a>Запуск приложения как службы Windows

Чтобы настроить приложение ASP.NET Core для работы в качестве службы Windows, установите пакет [Microsoft. Extensions. Hosting. службы Windows](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.WindowsServices) из NuGet. Затем добавьте вызов `UseWindowsService` в метод `CreateHostBuilder` в `Program.cs`.

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
> Если приложение не работает как служба Windows, метод `UseWindowsService` не выполняет никаких действий.

Теперь опубликуйте приложение с помощью одного из следующих методов:

* В Visual Studio, щелкнув проект правой кнопкой мыши и выбрав пункт **опубликовать** в контекстном меню.
* Из .NET Core CLI.

При публикации приложения .NET Core можно создать *зависимое от платформы* развертывание или *автономное* развертывание. Для развертываний, зависящих от платформы, требуется, чтобы общая среда выполнения .NET Core была установлена на узле, где они выполняются. Автономные развертывания публикуются с полной копией среды выполнения и платформы .NET Core и могут выполняться на любом узле. Дополнительные сведения, включая преимущества и недостатки каждого подхода, см. в документации по [развертыванию приложений .NET Core](../../core/deploying/index.md) .

Чтобы опубликовать автономную сборку приложения, которое не требует установки среды выполнения .NET Core 3,0 на узле, укажите среду выполнения, которая должна быть включена в приложение. Используйте флаг `-r` (или `--runtime`).

```dotnetcli
dotnet publish -c Release -r win-x64 -o ./publish
```

Чтобы опубликовать сборку, зависящую от платформы, опустите флаг `-r`.

```dotnetcli
dotnet publish -c Release -o ./publish
```

Скопируйте полное содержимое каталога `publish` в папку установки. Затем с помощью [средства SC](/windows/desktop/services/controlling-a-service-using-sc) Создайте службу Windows для исполняемого файла.

```console
sc create MyService binPath=C:\MyService\MyService.exe
```

### <a name="log-to-the-windows-event-log"></a>Регистрация в журнале событий Windows

Метод `UseWindowsService` автоматически добавляет поставщик [ведения журнала](/aspnet/core/fundamentals/logging/) , записывающий сообщения журнала в журнал событий Windows. Вы можете настроить ведение журнала для этого поставщика, добавив запись `EventLog` в раздел `Logging` `appsettings.json` или другой источник конфигурации. 

Имя источника, используемое в журнале событий, можно переопределить, задав свойство `SourceName` в этих параметрах. Если не указать имя, будет использоваться имя приложения по умолчанию (обычно имя исполняемой сборки).

Дополнительные сведения о ведении журнала приведены в конце этой главы.

## <a name="run-your-app-as-a-linux-service-with-systemd"></a>Запуск приложения как службы Linux с помощью системы

Чтобы настроить приложение ASP.NET Core для работы в качестве службы Linux (или *управляющей* программы в Linux терминах), установите пакет [Microsoft. Extensions. Hosting. System](https://www.nuget.org/packages/Microsoft.Extensions.Hosting.Systemd) из NuGet. Затем добавьте вызов `UseSystemd` в метод `CreateHostBuilder` в `Program.cs`.

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
> Если приложение не работает как служба Linux, метод `UseSystemd` не выполняет никаких действий.

Теперь опубликуйте приложение. Приложение может быть либо зависимым от платформы, либо самодостаточным для соответствующей среды выполнения Linux (например, `linux-x64`). Опубликовать можно с помощью одного из следующих методов:

* В Visual Studio, щелкнув проект правой кнопкой мыши и выбрав пункт **опубликовать** в контекстном меню. 
* Из .NET Core CLI с помощью следующей команды:

  ```dotnetcli
  dotnet publish -c Release -r linux-x64 -o ./publish
  ```
Скопируйте полное содержимое каталога `publish` в папку установки на узле Linux. Для регистрации службы требуется специальный файл, называемый *файлом единицы*, который будет добавлен в каталог `/etc/systemd/system`. Для создания файла в этой папке необходимо разрешение root. Присвойте файлу имя, которое будет использоваться `systemd` и расширением `.service`. Например, воспользуйтесь `/etc/systemd/system/myapp.service`.

Файл службы использует формат INI, как показано в следующем примере:

```ini
[Unit]
Description=My gRPC Application

[Service]
Type=notify
ExecStart=/usr/sbin/myapp

[Install]
WantedBy=multi-user.target
```

Свойство `Type=notify` указывает `systemd`, что приложение будет уведомлять его при запуске и завершении работы. Параметр `WantedBy=multi-user.target` приведет к запуску службы при достижении системой Linux "runlevel 2", что означает, что активна неграфическая оболочка с несколькими пользователями.

Прежде чем `systemd` распознает службу, необходимо перезагрузить ее конфигурацию. Управление `systemd` осуществляется с помощью команды `systemctl`. После перезагрузки используйте подкоманду `status`, чтобы убедиться, что приложение успешно зарегистрировано.

```console
sudo systemctl daemon-reload
sudo systemctl status myapp
```

Если служба настроена правильно, вы получите следующие выходные данные:

```text
myapp.service - My gRPC Application
 Loaded: loaded (/etc/systemd/system/myapp.service; disabled; vendor preset: enabled)
 Active: inactive (dead)
```

Для запуска службы используйте команду `start`.

```console
sudo systemctl start myapp.service
```

> [!TIP]
> Расширение `.service` не является обязательным, если вы используете `systemctl start`.

Чтобы указать `systemd` запускать службу автоматически при запуске системы, используйте команду `enable`.

```console
sudo systemctl enable myapp
```

### <a name="log-to-journald"></a>Регистрация в журнале

Аналогом журнала событий Windows в Linux является `journald`, структурированная системная служба ведения журналов, входящая в `systemd`. Сообщения журнала, записанные в стандартный вывод управляющей программой Linux, автоматически записываются в `journald`. Чтобы настроить уровни ведения журнала, используйте раздел `Console` конфигурации ведения журнала. Метод построителя `UseSystemd` узла автоматически настраивает формат вывода консоли в соответствии с журналом.

Поскольку `journald` является стандартом для журналов Linux, с ним интегрируется множество средств. Можно легко маршрутизировать журналы из `journald` во внешнюю систему ведения журнала. Работая локально на узле, можно использовать команду `journalctl` для просмотра журналов из командной строки.

```console
sudo journalctl -u myapp
```

> [!TIP]
> Если на вашем узле доступна среда графического пользовательского интерфейса, для Linux доступны несколько графических средств просмотра журналов, таких как *кжаурналктл* и *GNOME-Logs*.

Дополнительные сведения о запросах журнала `systemd` из командной строки с помощью `journalctl`см. [на страницах с Man](https://manpages.debian.org/buster/systemd/journalctl.1).

## <a name="https-certificates-for-self-hosted-applications"></a>HTTPS-сертификаты для приложений, размещаемых в собственном размещении

При запуске приложения gRPC в рабочей среде следует использовать сертификат TLS из доверенного центра сертификации (ЦС). Это может быть общедоступный ЦС или внутренний центр для вашей организации.

На узлах Windows можно загрузить сертификат из безопасного [хранилища сертификатов](/windows/win32/seccrypto/managing-certificates-with-certificate-stores) с помощью класса <xref:System.Security.Cryptography.X509Certificates.X509Store>. Вы также можете использовать класс `X509Store` с хранилищем ключей OpenSSL на некоторых узлах Linux.

Сертификаты также можно создавать с помощью одного из [конструкторов X509Certificate2](xref:System.Security.Cryptography.X509Certificates.X509Certificate2.%23ctor%2A):

* Файл, например файл `.pfx`, защищенный надежным паролем
* Двоичные данные, полученные из службы безопасного хранения, например [Azure Key Vault](https://azure.microsoft.com/services/key-vault/)

Настроить Kestrel для использования сертификата можно двумя способами: из конфигурации или в коде.

### <a name="set-https-certificates-by-using-configuration"></a>Настройка сертификатов HTTPS с помощью конфигурации

Подход к настройке требует установки пути к сертификату `.pfx` файл и пароль в разделе конфигурации Kestrel. В `appsettings.json`это будет выглядеть следующим образом:

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

Укажите пароль с помощью безопасного источника конфигурации, например Azure Key Vault или хранилища Hashicorp.

> [!IMPORTANT]
> Не храните незашифрованные пароли в файлах конфигурации.

### <a name="set-https-certificates-in-code"></a>Настройка сертификатов HTTPS в коде

Чтобы настроить HTTPS для Kestrel в коде, используйте метод `ConfigureKestrel` для `IWebHostBuilder` в классе `Program`.

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

Опять же, обязательно сохраните пароль для файла `.pfx` в и извлеките его из защищенного источника конфигурации.

>[!div class="step-by-step"]
>[Назад](grpc-in-production.md)
>[Вперед](docker.md)
