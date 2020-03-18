---
title: Рекомендации по использованию протокола TLS с .NET Framework
description: В этой статье приводятся рекомендации по использованию протокола TLS с .NET Framework
ms.date: 10/22/2018
helpviewer_keywords:
- sending data, Internet security
- protocols, Internet security
- Network security
- network resources, Internet security
- receiving data, Internet security
- authentication [.NET Framework], Internet security
- Internet, security
- security [.NET Framework], Internet
- permissions [.NET Framework], Internet
ms.openlocfilehash: 49beb8aa7d488bb6f0649cfb66ce7e78695840b4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "78848214"
---
# <a name="transport-layer-security-tls-best-practices-with-the-net-framework"></a>Рекомендации по использованию протокола TLS с .NET Framework

Протокол TLS — это отраслевой стандарт, предназначенный для защиты конфиденциальности информации, передаваемой через Интернет. [TLS 1.2](https://tools.ietf.org/html/rfc5246) — это стандарт, в котором предоставлены улучшенные функции безопасности по сравнению с предыдущими версиями. В будущем TLS 1.2 будет заменен новой версией стандарта [TLS 1.3](https://tools.ietf.org/html/rfc8446) с более высокой скоростью и улучшенными возможностями безопасности. В этой статье приводятся рекомендации по защите приложений .NET Framework, в которых используется протокол TLS.

Чтобы обеспечить безопасность приложений .NET Framework, **не** указывайте версию TLS в коде. Приложения .NET Framework должны использовать ту версию TLS, которую поддерживает операционная система.

Этот документ предназначен для следующих разработчиков:

- использующих API-интерфейсы <xref:System.Net> напрямую (например, <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> и <xref:System.Net.Security.SslStream?displayProperty=nameWithType>);
- использующих клиенты и службы WCF с пространством имен <xref:System.ServiceModel?displayProperty=nameWithType> напрямую;

Мы рекомендуем следующее:

- Использовать целевую версию .NET Framework 4.7 или более поздние версии в приложениях. Использовать целевую версию .NET Framework 4.7.1 или более поздние версии в приложениях WCF.
- Не указывать версию TLS. Настройте в коде возможность использовать версию TLS, поддерживаемую операционной системой.
- Проведите тщательный аудит кода и убедитесь, что версия TLS или SSL не задана.

Если приложение разрешает операционной системе выбрать версию TLS:

- в приложении автоматически будут использоваться новые протоколы, которые появятся в будущем (например, TLS 1.3.);
- операционная система будет блокировать протоколы, которые считаются небезопасными.

Сведения об обновлении и проведении аудита кода см. в разделе [Аудит и изменение кода](#audit-your-code-and-make-code-changes).

В этой статье объясняется, как обеспечить наиболее высокий уровень безопасности, доступный для версии .NET Framework, на которой запущено приложение и для которой оно предназначено. Если в приложении явно задан протокол безопасности и его версия, это означает отказ от альтернативных вариантов и стандартного поведения .NET Framework и операционной системы. Если требуется, чтобы приложение могло согласовать подключение TLS 1.2, явное указание более ранней версии будет препятствовать такому подключению.

Если невозможно обойти указание версии протокола в коде, настоятельно рекомендуем указать TLS 1.2. Чтобы получить рекомендации по определению и удалению зависимостей TLS 1.0, скачайте технический документ [Solving the TLS 1.0 Problem](https://www.microsoft.com/download/details.aspx?id=55266) (Устранение проблем с TLS 1.0).

По умолчанию WCF поддерживает на платформе .NET Framework 4.7 версии TLS 1.0, 1.1 и 1.2. Начиная с .NET Framework 4.7.1, WCF использует версию, поддерживаемую операционной системой по умолчанию. Если в приложении явно задан параметр `SslProtocols.None`, для протокола транспортировки NetTCP в службе WCF используются настройки операционной системы по умолчанию.

Вопросы по этому документу можно задать на странице версии документа, [опубликованной на GitHub](https://github.com/dotnet/docs/issues/4675).

## <a name="audit-your-code-and-make-code-changes"></a>Аудит и изменение кода

Для приложений ASP.NET проверьте элемент `<system.web><httpRuntime targetFramework>` в файле _web.config_ и убедитесь, что используется нужная версия .NET Framework.

Для приложений Windows Forms и других приложений см. статью [Практическое руководство. Определение целевой версии .NET Framework](/visualstudio/ide/visual-studio-multi-targeting-overview).

Ознакомьтесь со следующими разделами, чтобы проверить, не используются ли определенные версии TLS или SSL.

## <a name="if-your-app-targets-net-framework-47-or-later-versions"></a>Приложение предназначено для .NET Framework 4.7 или более поздней версии

В следующих разделах объясняется, как проверить, не используются ли определенные версии TLS или SSL.

### <a name="for-http-networking"></a>Для сетевых подключений по протоколу HTTP

<xref:System.Net.ServicePointManager>, используя .NET Framework 4.7 и более поздних версий, будет использоваться протокол безопасности по умолчанию, настроенный в ОС. Чтобы получить выбор ОС по умолчанию, если это возможно, не устанавливайте значение для свойства <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>, которое по умолчанию равно <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>.

Поскольку параметр <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType> предполагает <xref:System.Net.ServicePointManager> использование протокола безопасности по умолчанию, настроенного операционной системой, ваше приложение может работать по-разному в зависимости от ОС, в которой оно запущено. Например, Windows 7 SP1 использует протокол TLS 1.0, а Windows 8 и Windows 10 используют протокол TLS 1.2.

Остальная часть этой статьи не актуальна, если для сетевых подключений по протоколу HTTP используется целевая версия .NET Framework 4.7 или более поздняя версия.

### <a name="for-tcp-sockets-networking"></a>Для сетевого подключения через сокеты TCP

<xref:System.Net.Security.SslStream> (для .NET Framework 4.7 и более поздних версий): по умолчанию операционная система выбирает подходящий протокол безопасности и его версию. Чтобы получить подходящую для ОС версию, по возможности не используйте перегрузки метода <xref:System.Net.Security.SslStream>, который явно задает параметр <xref:System.Security.Authentication.SslProtocols>. В противном случае передайте значение <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Мы не рекомендуем устанавливать значение <xref:System.Security.Authentication.SslProtocols.Default>. Заданный параметр `SslProtocols.Default` принудительно применяет SSL 3.0 или TLS 1.0 и препятствует использованию TLS 1.2.

Не устанавливайте значение для свойства <xref:System.Net.ServicePointManager.SecurityProtocol> (при сетевом подключении по протоколу HTTP).

Не используйте перегрузки метода <xref:System.Net.Security.SslStream>, который явно задает параметр <xref:System.Security.Authentication.SslProtocols> (при сетевом подключении через сокеты TCP). Если для приложения нужно изменить целевую версию на .NET Framework 4.7 или более позднюю версию, ознакомьтесь со следующими рекомендациями.

Остальная часть этой статьи не актуальна, если для подключений через сокеты TCP используется целевая версия .NET Framework 4.7 или более поздняя версия.

<a name="wcf-tcp-cert"></a>

### <a name="for-wcf-tcp-transport-using-transport-security-with-certificate-credentials"></a>Для TCP-транспорта WCF с использованием защиты транспорта с помощью учетных данных сертификата

WCF использует тот же сетевой стек, что вся платформа .NET Framework.

Если приложение предназначено для версии 4.7.1, WCF позволяет операционной системе выбрать по умолчанию подходящий протокол безопасности, если он не задан явно:

- в файле конфигурации приложения;
- **или** в исходном коде приложения.

По умолчанию .NET Framework 4.7 и более поздние версии настроены на использование TLS 1.2 и разрешают подключения с использованием TLS 1.1 или TLS 1.0. Настройте в WCF выбор подходящего протокола безопасности операционной системой, настроив привязку на использование <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Это можно задать для <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>. `SslProtocols.None` можно получить из <xref:System.ServiceModel.NetTcpSecurity.Transport>. `NetTcpSecurity.Transport` можно получить из <xref:System.ServiceModel.NetTcpBinding.Security>.

При использовании пользовательской привязки сделайте следующее:

- Настройте в WCF выбор подходящего протокола безопасности операционной системой, указав <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols> использовать <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>.
- **Или** настройте протокол, используемый с путем конфигурации `system.serviceModel/bindings/customBinding/binding/sslStreamSecurity:sslProtocols`.

Если вы **не** применяете пользовательскую привязку, **но** устанавливаете привязку WCF с помощью конфигурации, задайте протокол, используемый с путем конфигурации `system.serviceModel/bindings/netTcpBinding/binding/security/transport:sslProtocols`.

### <a name="for-wcf-message-security-with-certificate-credentials"></a>Для защиты сообщений WCF с использованием учетных данных сертификата

По умолчанию для .NET Framework 4.7 и более поздних версий используется протокол, заданный в свойстве <xref:System.Net.ServicePointManager.SecurityProtocol>. Если для [AppContextSwitch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` задано значение `true`, WCF выбирает подходящий протокол до TLS 1.0.

## <a name="if-your-app-targets-a-net-framework-version-earlier-than-47"></a>Приложение предназначено для более ранней версии, чем.NET Framework 4.7

Проведите аудит кода, чтобы проверить, не задана ли определенная версия TLS или SSL, выполнив инструкции в следующих разделах:

### <a name="for-net-framework-46---462-and-not-wcf"></a>Для .NET Framework 4.6–4.6.2 (не для WFC)

Задайте для параметра `DontEnableSystemDefaultTlsVersions` `AppContext` значение `false`. Дополнительные сведения см. в разделе [Настройка безопасности с помощью параметров AppContext](#configuring-security-via-appcontext-switches).

### <a name="for-wcf-using-net-framework-46---462-using-tcp-transport-security-with-certificate-credentials"></a>Для WCF на .NET Framework 4.6–4.6.2 с использованием защиты транспорта TCP с помощью учетных данных сертификата

Нужно установить последние пакеты обновления операционной системы. Дополнительные сведения см. в разделе [Обновление системы безопасности](#security-updates).

Платформа WCF автоматически выбирает протокол последней версии до TLS 1.2, если версия протокола не указана явно. Дополнительные сведения см. в предыдущем разделе [Для TCP-транспорта WCF с использованием защиты транспорта с помощью учетных данных сертификата](#wcf-tcp-cert).

### <a name="for-net-framework-35---452-and-not-wcf"></a>Для .NET Framework 3.5–4.5.2 (не для WFC)

Мы рекомендуем обновить приложение до .NET Framework 4.7 или более поздней версии. Если это невозможно, выполните приведенные ниже действия. Если не выполнить обновление до .NET Framework 4.7 или более поздней версии, в будущем работа приложения может завершаться сбоем.

В разделах реестра [SchUseStrongCrypto](#schusestrongcrypto) и [SystemDefaultTlsVersions](#systemdefaulttlsversions) задайте значение 1. Сведения см. в разделе [Настройка безопасности в реестре Windows](#configuring-security-via-the-windows-registry). Платформа .NET Framework версии 3.5 поддерживает флаг `SchUseStrongCrypto`, только если значение TLS передается явно.

Если приложение запущено на .NET Framework 3.5, установите пакет обновлений, чтобы программа могла указать версию TLS 1.2.

| [KB3154518](https://support.microsoft.com/kb/3154518) | Пакет исправлений HR-1605 для повышения надежности —добавлена поддержка версий TLS по умолчанию для .NET Framework 3.5.1 в системе Windows 7 с пакетом обновления 1 (SP1) и Server 2008 R2 с пакетом обновления 1 (SP1). |
| --- | --- |
| [KB3154519](https://support.microsoft.com/kb/3154519) | Пакет исправлений HR-1605 для повышения надежности — добавлена поддержка версий TLS по умолчанию для .NET Framework 3.5 в системе Windows Server 2012. |
| [KB3154520](https://support.microsoft.com/kb/3154520) | Пакет исправлений HR-1605 для повышения надежности — добавлена поддержка версий TLS по умолчанию для .NET Framework 3.5 в системе Windows 8.1 и Windows Server 2012 R2. |
| [KB3156421](https://support.microsoft.com/kb/3156421) | Пакет исправлений 1605 (3154521) для .NET Framework 4.5.2 и 4.5.1 в Windows |

### <a name="for-wcf-using-net-framework-35---452-using-tcp-transport-security-with-certificate-credentials"></a>Для WCF на платформе .NET Framework 3.5–4.5.2 с использованием защиты транспорта TCP с помощью учетных данных сертификата

В этих версиях платформы WCF явно задано использование SSL 3.0 и TLS 1.0. Эти значения невозможно изменить. Чтобы использовать TLS 1.1 и 1.2, необходимо выполнить обновление и переопределение для .NET Framework 4.6 или более поздних версий.

## <a name="if-your-app-targets-net-framework-35"></a>Приложение предназначено для .NET Framework 3.5

Если нужно явно указать протокол безопасности вместо того, чтобы разрешить .NET или операционной системе выбирать его, добавьте перечисления `SecurityProtocolTypeExtensions` и `SslProtocolsExtension` в код. Перечисления `SecurityProtocolTypeExtensions` и `SslProtocolsExtension` включают значения для `Tls12`, `Tls11` и значение `SystemDefault`. Дополнительные сведения см. в статье [Support for TLS System Default Versions included in .NET Framework 3.5 on Windows 8.1 and Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework) (Добавлена поддержка версий TLS по умолчанию для .NET Framework 3.5 в системе Windows 8.1 и Windows Server 2012 R2)

<a name="configuring-security-via-appcontext-switches"></a>

## <a name="configuring-security-via-appcontext-switches-for-net-framework-46-or-later-versions"></a>Настройка безопасности с помощью параметров AppContext (для .NET Framework 4.6 или более поздней версии)

Описанные в этом разделе параметры [AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) нужно использовать, если приложение запущено на платформе .NET Framework 4.6 или более поздних версий либо предназначено для нее. По возможности явно укажите для параметров значение `false` или оно должно быть задано по умолчанию. Чтобы настроить безопасность с помощью одного или обоих параметров, не указывайте значение протокола безопасности в коде, так как это переопределит значения параметров.

Функции этих параметров одинаковы как для сетевых подключений по протоколу HTTP (<xref:System.Net.ServicePointManager>), так и через сокеты TCP (<xref:System.Net.Security.SslStream>).

### <a name="switchsystemnetdontenableschusestrongcrypto"></a>Switch.System.Net.DontEnableSchUseStrongCrypto

Задайте для `false` значение `Switch.System.Net.DontEnableSchUseStrongCrypto`, чтобы в приложении использовалось устойчивое шифрование. Задайте для `false` значение `DontEnableSchUseStrongCrypto`, чтобы использовать безопасные сетевые протоколы (TLS 1.2, TLS 1.1 и TLS 1.0) и блокировать небезопасные. Дополнительные сведения см. в разделе о флаге [SCH_USE_STRONG_CRYPTO](#the-sch_use_strong_crypto-flag). Значение `true` позволяет отключить устойчивое шифрование для приложения.

Если приложение предназначено для .NET Framework 4.6 или более поздней версии, по умолчанию для параметра задано значение `false`. Мы рекомендуем использовать эти безопасные настройки по умолчанию. Если приложение запускается на .NET Framework 4.6, но предназначено для более ранней версии, значение параметра по умолчанию — `true`. В этом случае нужно явно задать значение `false`.

Если нужно установить подключение к устаревшим службам без поддержки устойчивого шифрования и возможности обновления, для параметра `DontEnableSchUseStrongCrypto` нужно задать только значение `true`.

### <a name="switchsystemnetdontenablesystemdefaulttlsversions"></a>Switch.System.Net.DontEnableSystemDefaultTlsVersions

Если для `false` задать значение `Switch.System.Net.DontEnableSystemDefaultTlsVersions`, приложение разрешит операционной системе выбирать протокол. Если задать значение `true`, приложение будет использовать протоколы, выбранные платформой .NET Framework.

Если приложение предназначено для .NET Framework 4.7 или более поздних версий, по умолчанию для параметра задано значение `false`. Мы рекомендуем использовать эти безопасные настройки по умолчанию. Если приложение запускается на .NET Framework 4.7 или более поздних версиях, но предназначено для более ранней версии, по умолчанию для параметра задано значение `true`. В этом случае нужно явно задать значение `false`.

### <a name="switchsystemservicemodeldisableusingservicepointmanagersecurityprotocols"></a>Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols

Задайте для `false` значение `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols`, чтобы приложение использовало значение, определенное в свойстве `ServicePointManager.SecurityProtocols`, для защиты передаваемых сообщений с помощью учетных данных сертификата. Если задать значение `true`, будет использоваться последняя доступная версия протокола до TLS 1.0.

Если приложение предназначено для .NET Framework 4.7 или более поздних версий, по умолчанию для параметра задано значение `false`. Если приложение предназначено для .NET Framework 4.6.2 и более ранних версий, по умолчанию для параметра задано значение `true`.

### <a name="switchsystemservicemodeldontenablesystemdefaulttlsversions"></a>Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions

Если задать для `false` значение `Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions`, в конфигурации по умолчанию операционной системе разрешается выбирать протокол. Если задать значение `true`, по умолчанию будет использоваться последняя доступная версия протокола до TLS 1.2.

Если приложение предназначено для .NET Framework 4.7.1 или более поздних версий, по умолчанию для параметра задано значение `false`. Если приложение предназначено для .NET Framework 4.7 и более ранних версий, по умолчанию для параметра задано значение `true`.

Дополнительные сведения о протоколах TLS см. в статье [Устранение рисков. Протоколы TLS](../migration-guide/mitigation-tls-protocols.md). Дополнительные сведения о параметрах `AppContext` см. в статье об элементе [`<AppContextSwitchOverrides> Element`](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

## <a name="configuring-security-via-the-windows-registry"></a>Настройка безопасности в реестре Windows

> [!WARNING]
> Настройка раздела реестра влияет на все приложения в системе. Используйте этот вариант только в том случае, если компьютер находится полностью под вашим управлением и вы контролируете изменения в реестре.

Если невозможно задать один или оба параметра `AppContext`, вы можете управлять протоколами безопасности, которые использует приложение, с помощью разделов реестра Windows, описанных в этом разделе. Использование одного или двух параметров `AppContext` может оказаться невозможным, если приложение выполняется в .NET Framework 4.5.2 либо более ранних версиях или если невозможно изменить файл конфигурации. Чтобы настроить безопасность с помощью реестра, не указывайте значение протокола безопасности в коде, так как это переопределит параметры в реестре.

Имена разделов реестра схожи с соответствующими именами параметров `AppContext`, но не содержат `DontEnable` в начале имени. Например, параметру `AppContext``DontEnableSchUseStrongCrypto` соответствует раздел реестра [SchUseStrongCrypto](#schusestrongcrypto).

Эти разделы доступны во всех версиях .NET Framework с последними обновлениями для системы безопасности. Дополнительные сведения см. в разделе [Обновление системы безопасности](#security-updates).

Функции описанных здесь разделов реестра одинаковы как для сетевых подключений по протоколу HTTP (<xref:System.Net.ServicePointManager>), так и через сокеты TCP (<xref:System.Net.Security.SslStream>).

### <a name="schusestrongcrypto"></a>SchUseStrongCrypto

Значение в разделе реестра `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SchUseStrongCrypto` имеет тип DWORD. Задайте значение 1, чтобы в приложении использовалось устойчивое шифрование. При устойчивом шифровании используются более безопасные сетевые протоколы (TLS 1.2, TLS 1.1 и TLS 1.0) и блокируются небезопасные. Если задать значение 0, устойчивое шифрование будет отключено. Дополнительные сведения см. в разделе о флаге [SCH_USE_STRONG_CRYPTO](#the-sch_use_strong_crypto-flag).

Если приложение предназначено для .NET Framework 4.6 или более поздних версий, по умолчанию в реестре задано значение 1. Мы рекомендуем использовать эти безопасные настройки по умолчанию. Если приложение запускается на .NET Framework 4.6, но предназначено для более ранней версии, по умолчанию в разделе задано значение 0. В этом случае нужно явно задать значение 1.

Если нужно установить подключение к устаревшим службам без поддержки устойчивого шифрования и возможности обновления, в реестре нужно задать только значение 0.

### <a name="systemdefaulttlsversions"></a>SystemDefaultTlsVersions

Значение в разделе реестра `HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SystemDefaultTlsVersions` имеет тип DWORD. Если задать значение 1, приложение разрешит операционной системе выбирать протокол. Если задать значение 0, приложение будет использовать протоколы, выбранные платформой .NET Framework.

Вместо `<VERSION>` нужно указать значение v4.0.30319 (для .NET Framework 4 и более поздних версий) или v2.0.50727 (для .NET Framework 3.5).

Если приложение предназначено для .NET Framework 4.7 или более поздних версий, по умолчанию в разделе задано значение 1. Мы рекомендуем использовать эти безопасные настройки по умолчанию. Если приложение запускается на .NET Framework 4.7 или более поздних версиях, но предназначено для более ранней версии, по умолчанию в разделе задано значение 0. В этом случае нужно явно задать значение 1.

Дополнительные сведения см. в статье [Cumulative Update for Windows 10 Version 1511 and Windows Server 2016 Technical Preview 4: May 10, 2016](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016) (Накопительный пакет обновления для Windows 10 версии 1511 и Windows Server 2016 Technical Preview 4 за 10 мая 2016 г.)

Дополнительные сведения о .NET Framework 3.5.1 см. в статье [Support for TLS System Default Versions included in .NET Framework 3.5.1 on Windows 7 SP1 and Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework) (Добавлена поддержка версий TLS по умолчанию для .NET Framework 3.5.1 в системе Windows 7 с пакетом обновления 1 (SP1) и Server 2008 R2 с пакетом обновления 1 (SP1).)

В следующем файле _.REG_ для разделов реестра и их вариантов задаются наиболее безопасные значения:

```text
Windows Registry Editor Version 5.00

[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v2.0.50727]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\.NETFramework\v4.0.30319]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v2.0.50727]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001

[HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\.NETFramework\v4.0.30319]
"SystemDefaultTlsVersions"=dword:00000001
"SchUseStrongCrypto"=dword:00000001
```

## <a name="configuring-schannel-protocols-in-the-windows-registry"></a>Настройка протоколов Schannel в реестре Windows

Вы можете использовать реестр для точного управления протоколами, которые согласовывает клиент или серверное приложение. Приложение подключается к сети по протоколу Schannel, который также называют [Secure Channel](/windows/desktop/SecAuthN/secure-channel). Используя `Schannel`, вы можете настроить поведение приложения.

Для начала перейдите в раздел реестра `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols`. В нем вы можете создать любые подразделы из набора `SSL 2.0`, `SSL 3.0`, `TLS 1.0`, `TLS 1.1` и `TLS 1.2`. В каждом подразделе можно создать подраздел `Client` и (или) `Server`. В подразделах `Client` и `Server` вы можете создать значения DWORD для `DisabledByDefault` (0 или 1) и для `Enabled` (0 или 0xFFFFFFFF).

## <a name="the-sch_use_strong_crypto-flag"></a>Флаг SCH_USE_STRONG_CRYPTO

Если флаг `AppContext` включен (по умолчанию с помощью параметра `SCH_USE_STRONG_CRYPTO` или в реестре Windows), .NET Framework использует его, когда приложение запрашивает протокол безопасности TLS. Флаг `SCH_USE_STRONG_CRYPTO` может быть включен по умолчанию с помощью параметра `AppContext` или реестра. Операционная система передает флаг `Schannel`, чтобы отключать известные ненадежные алгоритмы шифрования, наборы шифров, версии протоколов TLS и SSL, которые могут быть включены для улучшения взаимодействия. Дополнительные сведения можно найти в разделе

- [Secure Channel](/windows/desktop/SecAuthN/secure-channel)
- [SCHANNEL_CRED structure](/windows/win32/api/schannel/ns-schannel-schannel_cred) (Структура SCHANNEL_CRED)

Флаг `SCH_USE_STRONG_CRYPTO` также передается `Schannel`, если для `Tls` или `Tls11` явно используются перечисляемые значения `Tls12` (TLS 1.0), <xref:System.Net.SecurityProtocolType> или <xref:System.Security.Authentication.SslProtocols>.

## <a name="security-updates"></a>Обновления для системы безопасности

Рекомендации в этой статье зависят от последних обновлений системы безопасности, которые вы установили. Эти обновления позволяют использовать дополнительные функции .NET Framework 4.7 и более поздних версий. Последние обновления системы безопасности особенно важны для приложений, запущенных на .NET Framework 4.7 и более поздних версиях (даже если приложения предназначены для более ранних версий).

Если нужно обновить .NET Framework, чтобы разрешить операционной системе выбирать подходящую версию TLS, установите как минимум следующее:

- [пакет исправлений для .NET Framework за август 2017 г. (предварительная версия) для повышения качества](https://devblogs.microsoft.com/dotnet/net-framework-august-2017-preview-of-quality-rollup/);
- **или**[пакет исправлений для .NET Framework за сентябрь 2017 г. для повышения качества](https://devblogs.microsoft.com/dotnet/net-framework-september-2017-security-and-quality-rollup/).

См. также:

- [Версии и зависимости платформы .NET Framework](../migration-guide/versions-and-dependencies.md)
- [Практическое руководство. Определение установленных версий платформы .NET Framework](../migration-guide/how-to-determine-which-versions-are-installed.md)

## <a name="support-for-tls-12"></a>Поддержка TLS 1.2

Чтобы приложение могло согласовать протокол TLS 1.2, операционная система и версия платформы .NET Framework должны поддерживать этот протокол.

**Требования к операционной системе для включения поддержки TLS 1.2**

Чтобы включить или повторно включить протокол TLS 1.2 и (или) TLS 1.1, в системе, которая их поддерживает, ознакомьтесь со статьей [Transport Layer Security (TLS) registry settings](/windows-server/security/tls/tls-registry-settings) (Параметры реестра для протокола TLS).

| **ОС** | **Поддержка TLS 1.2** |
| --- | --- |
| Windows 10<br>Windows Server 2016 | Поддерживается и включена по умолчанию. |
| Windows 8.1<br>Windows Server 2012 R2 | Поддерживается и включена по умолчанию. |
| Windows 8.0<br>Windows Server 2012 | Поддерживается и включена по умолчанию. |
| Windows 7 SP1<br>Windows Server 2008 R2 с пакетом обновления 1 (SP1) | Поддерживается, но не включена по умолчанию. Сведения о том, как включить TLS 1.2 см. на веб- странице [Transport Layer Security (TLS) registry settings](/windows-server/security/tls/tls-registry-settings) (Параметры реестра для протокола TLS). |
| Windows Server 2008 | Для поддержки TLS 1.2 и TLS 1.1 требуется обновить систему. Дополнительные сведения см. в статье [Update to add support for TLS 1.1 and TLS 1.2 in Windows Server 2008 SP2](https://support.microsoft.com/help/4019276/update-to-add-support-for-tls-1-1-and-tls-1-2-in-windows-server-2008-s) (Обновление для добавления поддержки TLS 1.1 и TLS 1.2 в Windows Server 2008 с пакетом обновления 2 (SP2)). |
| Windows Vista | Не поддерживается. |

Сведения о том, какие версии протоколов TLS или SSL включены в версиях Windows, см. в статье [Protocols in TLS/SSL (Schannel SSP)](/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-) (Протоколы TLS и SSL (поставщик службы безопасности Schannel))

**Требования для поддержки TLS 1.2 на платформе .NET Framework 3.5**

В этой таблице указаны обновления операционной системы, которые требуются для включения поддержки TLS 1.2 для .NET Framework 3.5. Мы рекомендуем применить все обновления операционной системы.

| **ОС** | **Минимальные обновления, необходимые для включения поддержки TLS 1.2 для .NET Framework 3.5** |
| --- | --- |
| Windows 10<br>Windows Server 2016 | [Накопительный пакет обновления для Windows 10 версии 1511 и Windows Server 2016 Technical Preview 4 за 10 мая 2016 г.](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016) |
| Windows 8.1<br>Windows Server 2012 R2 | [Включенная поддержка версий TLS по умолчанию для .NET Framework 3.5 в Windows 8.1 и Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 8.0<br>Windows Server 2012 | [Включенная поддержка версий TLS по умолчанию для .NET Framework 3.5 в Windows Server 2012](https://support.microsoft.com/help/3154519/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 7 SP1<br>Windows Server 2008 R2 с пакетом обновления 1 (SP1) | [Включенная поддержка версий TLS по умолчанию для .NET Framework 3.5.1 в Windows 7 с пакетом обновления 1(SP1) и Server 2008 R2 с пакетом обновления 1(SP1)](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Server 2008 | [Включенная поддержка версий TLS по умолчанию для .NET Framework 2.0 с пакетом обновления SP2 в Windows Vista SP2 и Server 2008 SP2](https://support.microsoft.com/help/3154517/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Vista | Не поддерживается |
