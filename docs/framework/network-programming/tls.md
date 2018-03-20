---
title: "Рекомендации Transport Layer Security (TLS) с помощью .NET Framework"
description: "Описывает рекомендации, с помощью Transport Layer Security (TLS) с помощью .NET Framework"
ms.date: 03/15/2018
ms.prod: .net-framework
ms.topic: article
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
author: blowdart
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 64829eee5b21a44acb18cbec9b901d77d49cab90
ms.sourcegitcommit: 32172ca05d5dcce7ef3d327b9c8639c736e0fe2b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/20/2018
---
# <a name="transport-layer-security-tls-best-practices-with-the-net-framework"></a>Рекомендации Transport Layer Security (TLS) с помощью .NET Framework

Протокол Transport Layer Security (TLS) — это стандартный предназначены для обеспечения защиты конфиденциальности информации, проходящей через Интернет. [TLS 1.2](https://tools.ietf.org/html/rfc5246) является стандартом последней выпущенной и предоставляет улучшения безопасности сравнению с предыдущими версиями. TLS 1.2 будет заменен на [TLS 1.3](https://tools.ietf.org/html/draft-ietf-tls-tls13-22). В этой статье даются рекомендации для защиты приложений .NET Framework, которые используют протокол TLS.

Чтобы повысить безопасность приложений .NET Framework, версия TLS должна **не** жестко задано. Приложения .NET framework следует использовать версию TLS, поддерживаемой операционной системы (ОС).

Этот документ предназначен для разработчиков, которые являются:

- Непосредственно с помощью <xref:System.Net> API-интерфейсы (например, <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> и <xref:System.Net.Security.SslStream?displayProperty=nameWithType>).
- Непосредственно с помощью клиентов и служб с помощью WCF <xref:System.ServiceModel?displayProperty=nameWithType> пространства имен.
- С помощью [облачных служб Azure](https://azure.microsoft.com/services/cloud-services/) рабочих и веб-роли для размещения и запустите приложение. В разделе [облачных служб Azure](#azure-cloud-services) раздела.

Мы рекомендуем вам:

- Целевая платформа .NET Framework 4.7 или более поздних версий в приложениях. Целевая версия .NET Framework 4.7.1 или более поздних версий в приложениях WCF.
- Не указывайте версию TLS. Настройте программный код, чтобы решить, TLS версии операционной системы.
- Выполните аудит кода тщательна, чтобы убедиться, что версии TLS или SSL не указано.

Когда приложения позволяет выбрать TLS версии операционной системы:

- Он автоматически использует преимущества новых протоколов добавлена в будущем, таких как TLS 1.3.
- Операционная система блокирует протоколы, которые обнаруживаются не для обеспечения безопасности.

Раздел [аудита код и внесите изменения в код](#audit-your-code-and-make-code-changes) охватывает аудита и обновление вашего кода.

В этой статье объясняется, как включить для установленной версии платформы .NET Framework, приложение, предназначенное и работает на самый высокий уровень безопасности. Когда приложение явно задает протокол безопасности и версии, отказ любые другие возможности и отказ .NET Framework и операционной системы по умолчанию. Если требуется, чтобы приложения могли осуществлять согласовать подключение TLS 1.2, явного задания до более ранней версии TLS предотвращает соединения TLS 1.2.

Если не удается избежать жесткого задания версию протокола, настоятельно рекомендуется указывать TLS 1.2. Руководство по идентификации и удаление зависимостей TLS 1.0, загрузите [решения проблемы TLS 1.0](https://www.microsoft.com/download/details.aspx?id=55266) Технический документ.

WCF поддерживает TLS1.0, 1.1 и 1.2 по умолчанию в .NET Framework 4.7. Начиная с .NET Framework 4.7.1, WCF, по умолчанию используется операционная система настроена версии. Если приложение явно настроен с `SslProtocols.None`, WCF использует операционной системы по умолчанию при использовании транспорта NetTcp.

Можно задать вопросы об этом документе в выпуске GitHub [Transport Layer Security (TLS) рекомендации с платформой .NET Framework](https://github.com/dotnet/docs/issues/4675).

## <a name="audit-your-code-and-make-code-changes"></a>Аудит код и внесите изменения в код

Для приложений ASP.NET, проверить `<system.web><httpRuntime targetFramework>` элемент _web.config_ для проверки используется предполагаемого версия платформы .NET Framework.

Windows Forms и других приложений см. в разделе [как: целевой версии платформы .NET Framework](/visualstudio/ide/how-to-target-a-version-of-the-dotnet-framework).

Используйте следующие разделы, чтобы убедиться, что вы не используете определенной версии TLS или SSL.

## <a name="if-your-app-targets-net-framework-47-or-later-versions"></a>Если приложение предназначено для .NET Framework 4.7 или более поздней версии

В следующих разделах показаны способы проверки, вы не используете определенной версии TLS или SSL.

### <a name="for-http-networking"></a>Для работы в сети HTTP

<xref:System.Net.ServicePointManager>, с помощью .NET Framework 4.7 и более поздних версиях по умолчанию — выбрать наилучший протокол безопасности и версии операционной системы. Для получения лучшим вариантом ОС по умолчанию, если это возможно, не задать значение для <xref:System.Net.ServicePointManager.SecurityProtocol> свойства. В противном случае задайте <xref:System.Net.SecurityProtocolType.SystemDefault>.

В оставшейся части этой статьи не применимо, при разработке для .NET Framework 4.7 или более поздней версии для работы в сети HTTP.

### <a name="for-tcp-sockets-networking"></a>Для сокетов TCP к сети

<xref:System.Net.Security.SslStream>, с помощью .NET Framework 4.7 и более поздних версиях по умолчанию — выбрать наилучший протокол безопасности и версии операционной системы. Чтобы получить лучший выбор операционной системы по умолчанию, по возможности не используйте перегрузки метода <xref:System.Net.Security.SslStream> , принимающие явно <xref:System.Security.Authentication.SslProtocols> параметра. В противном случае передайте <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Рекомендуется не использовать <xref:System.Security.Authentication.SslProtocols.Default>; при установке `SslProtocols.Default` принудительное использование SSL 3.0 /TLS 1.0 и предотвратить TLS 1.2.

Не задано значение для <xref:System.Net.ServicePointManager.SecurityProtocol> свойство (для HTTP сеть).

Не используйте перегрузки метода <xref:System.Net.Security.SslStream> , принимающие явно <xref:System.Security.Authentication.SslProtocols> параметр (для протокола TCP к сети). При изменении целевой платформы приложения для .NET Framework 4.7 или более поздней версии, будет следующие рекомендации по рекомендациям.

В оставшейся части этой статьи не применимо при для различных версий .NET Framework 4.7 или более поздней версии для TCP сокеты сети.

<a name="wcf-tcp-cert"></a>

### <a name="for-wcf-tcp-transport-using-transport-security-with-certificate-credentials"></a>WCF TCP-транспорта с использованием безопасности транспорта с учетными данными сертификата

WCF использует один сетевой стек как остальная часть .NET Framework.

Если вы используете 4.7.1, операционной системой выбрать наилучший протокол безопасности по умолчанию, если не задано явно настроен WCF:

- В файле конфигурации приложения.
- **Или**, в приложении в исходном коде.

По умолчанию .NET Framework 4.7 и более поздних версиях настроен для использования TLS 1.2 и разрешены соединения с использованием TLS 1.1 или TLS 1.0. Настроить WCF выбрать наилучший протокол безопасности, настроив привязки, используемой операционной системой <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>. Может устанавливаться на <xref:System.ServiceModel.TcpTransportSecurity.SslProtocols>. `SslProtocols.None` можно получить доступ из <xref:System.ServiceModel.NetTcpSecurity.Transport>. `NetTcpSecurity.Transport` можно получить доступ из <xref:System.ServiceModel.NetTcpBinding.Security>.

При использовании пользовательской привязки:

- Настроить WCF операционной системой выбрать наилучший протокол безопасности, задав <xref:System.ServiceModel.Channels.SslStreamSecurityBindingElement.SslProtocols> использовать <xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType>.
- **Или** настроить протокол, используемый с путем конфигурации `system.serviceModel/bindings/customBinding/binding/sslStreamSecurity:sslProtocols`.

Если вы **не** с помощью пользовательской привязки **и** задается привязка WCF с помощью конфигурации, установите протокол, используемый с путем конфигурации `system.serviceModel/bindings/netTcpBinding/binding/security/transport:sslProtocols`.

### <a name="for-wcf-message-security-with-certificate-credentials"></a>Для обеспечения безопасности сообщений WCF с учетными данными сертификата

.NET framework 4.7 и более поздних версиях по умолчанию использует протокол, задаваемый в <xref:System.Net.ServicePointManager.SecurityProtocol> свойство. Когда [AppContextSwitch](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` равно `true`, WCF выбирает наилучший протокол до TLS 1.0.

## <a name="if-your-app-targets-a-net-framework-version-earlier-than-47"></a>Если приложение предназначено для версии платформы .NET Framework более ранней, чем 4.7

Аудит коде, чтобы убедиться, что не задаются значения определенной версии TLS или SSL с использованием в следующих разделах:

### <a name="for-net-framework-46---462-and-not-wfc"></a>Для .NET Framework 4.6 — 4.6.2 и не WFC

Задать `DontEnableSystemDefaultTlsVersions` `AppContext` переключитесь `false`. В разделе [настройки безопасности по коммутаторам параметров AppContext](#configuring-security-via-appcontext-switches).

### <a name="for-wcf-using-net-framework-46---462-using-tcp-transport-security-with-certificate-credentials"></a>Для WCF с помощью .NET Framework 4.6 - 4.6.2 Использование безопасности транспорта TCP с учетными данными сертификата

Необходимо установить последние пакеты обновления операционной системы. В разделе [обновления для системы безопасности](#security-updates).

Платформа WCF автоматически выбираются наибольший протокол такого TLS 1.2, если явным образом настраивать версия протокола. Дополнительные сведения см. предыдущий раздел [транспорта для TCP WCF, с использованием безопасности транспорта с учетными данными сертификата](#wcf-tcp-cert).

### <a name="for-net-framework-35---451-and-not-wcf"></a>Для .NET Framework 3.5 — 4.5.1 и не WCF

Рекомендуется обновить приложения для .NET Framework 4.7 или более поздней версии. Если нельзя обновить, выполните следующие действия. В некоторый момент в будущем, ваше приложение может отказать пока не обновлены до .NET Framework 4.7 или более поздней версии.

Задать [SchUseStrongCrypto](#schusestrongcrypto) и [SystemDefaultTlsVersions](#systemdefaulttlsversions) разделы реестра на 1. В разделе [Настройка безопасности в реестре Windows](#configuring-security-via-the-windows-registry). Платформа .NET Framework версии 3.5 поддерживает `SchUseStrongCrypto` флаг только при передаче явное значение TLS.

При выполнении на .NET Framework 3.5 необходимо установить горячего обновления, чтобы TLS 1.2 можно указать в программе:

| [KB3154518](https://support.microsoft.com/kb/3154518) | Надежность свертки HR-1605 - в .NET Framework 3.5.1 на Windows 7 с пакетом обновления 1 и Server 2008 R2 SP1 включена поддержка версий по умолчанию системы TLS |
| --- | --- |
| [KB3154519](https://support.microsoft.com/kb/3154519) | Надежность свертки HR-1605 - поддержка версий по умолчанию TLS системы включены в .NET Framework 3.5 в Windows Server 2012 |
| [KB3154520](https://support.microsoft.com/kb/3154520) | Свертка надежность 1605 HR - включена поддержка TLS системы по умолчанию версий в .NET Framework 3.5 в Windows 8.1 и Windows Server 2012 R2 |
| [KB3156421](https://support.microsoft.com/kb/3156421) | 1605 накопительный пакет исправлений 3154521 для платформы .NET Framework 4.5.2 и 4.5.1 в Windows |

### <a name="for-wcf-using-net-framework-35---452-using-tcp-transport-security-with-certificate-credentials"></a>Для WCF с помощью .NET Framework 3.5 - 4.5.2 Использование безопасности транспорта TCP с учетными данными сертификата

Эти версии WCF framework жестко запрограммированы для использования значений, SSL 3.0 и TLS 1.0. Эти значения нельзя изменить. Необходимо обновить и изменить целевую платформу на .NET Framework 4.6 или более поздней версии, чтобы использовать TLS 1.1 и 1.2.

## <a name="if-your-app-targets-net-framework-35"></a>Если приложение предназначено для .NET Framework 3.5

Если необходимо явно задать протокол безопасности вместо платформы .NET framework или выбора ОС протокол безопасности, добавьте `SecurityProtocolTypeExtensions` и `SslProtocolsExtension` перечисления в код. `SecurityProtocolTypeExtensions` и `SslProtocolsExtension` указывайте значения для `Tls12`, `Tls11`и `SystemDefault` значение. В разделе [поддержка версий по умолчанию TLS системы включены в .NET Framework 3.5 в Windows 8.1 и Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework).

<a name="configuring-security-via-appcontext-switches"></a>

## <a name="configuring-security-via-appcontext-switches-for-net-framework-46-or-later-versions"></a>Настройка безопасности с помощью параметров AppContext переключается (для .NET Framework 4.6 или более поздней версии)

[Параметров AppContext](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) параметры, описанные в этом разделе Если приложение нацелено на или выполняется на .NET Framework 4.6 или более поздней версии. По умолчанию, либо явной установки, что коммутаторы должны ли `false` Если это возможно. Если вы хотите настроить безопасность с помощью одного или обоих параметров, затем не указать значение протокола безопасности в коде; Поэтому это переопределит выключатели.

Параметры имеют тот же эффект ли вы выполняете сети HTTP (<xref:System.Net.ServicePointManager>) или TCP сокеты сети (<xref:System.Net.Security.SslStream>).

### <a name="switchsystemnetdontenableschusestrongcrypto"></a>Switch.System.Net.DontEnableSchUseStrongCrypto

Значение `false` для `Switch.System.Net.DontEnableSchUseStrongCrypto` вызывает приложение на использование надежного шифрования. Значение `false` для `DontEnableSchUseStrongCrypto` использует более безопасные сетевые протоколы (TLS 1.2, TLS 1.1 и TLS 1.0) и блокирует протоколы, которые не являются безопасными. Дополнительные сведения см. в разделе [SCH_USE_STRONG_CRYPTO флаг](#the-schusestrongcrypto-flag). Значение `true` отключает устойчивое шифрование для приложения.

Если приложение предназначено для .NET Framework 4.6 или более поздней версии, этот параметр по умолчанию `false`. Это безопасности по умолчанию, который рекомендуется использовать. Если приложение работает в .NET Framework 4.6, но на более раннюю версию, по умолчанию используется параметр `true`. В этом случае необходимо явно задать значение `false`.

`DontEnableSchUseStrongCrypto` должен иметь только значение `true` Если необходимо соединиться с предыдущих версий служб, которые не поддерживают надежного шифрования и не могут быть обновлены.

### <a name="switchsystemnetdontenablesystemdefaulttlsversions"></a>Switch.System.Net.DontEnableSystemDefaultTlsVersions

Значение `false` для `Switch.System.Net.DontEnableSystemDefaultTlsVersions` вызывает приложение разрешить операционной системе для выбора протокола. Значение `true` вызывает приложения к использованию протоколов, которые используются платформой .NET Framework.

Если приложение предназначено для .NET Framework 4.7 или более поздней версии, этот параметр по умолчанию `false`. Это безопасности по умолчанию, которое рекомендуется использовать. Если приложение работает в .NET Framework 4.7 или более поздней версии, но на более раннюю версию, по умолчанию используется параметр `true`. В этом случае необходимо явно задать значение `false`.

### <a name="switchsystemservicemodeldisableusingservicepointmanagersecurityprotocols"></a>Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols

Значение `false` для `Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols` предписывает приложению использовать значение, определенное в `ServicePointManager.SecurityProtocols` для обеспечения безопасности сообщений с использованием учетных данных сертификата. Значение `true` с протоколом наибольший доступны до TLS1.0

Для приложений, предназначенных для .NET Framework 4.7 и более поздних версиях, это значение по умолчанию `false`. Для приложений, предназначенных для .NET Framework 4.6.2 и более ранних версиях это значение по умолчанию `true`.

### <a name="switchsystemservicemodeldontenablesystemdefaulttlsversions"></a>Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions

Значение `false` для `Switch.System.ServiceModel.DontEnableSystemDefaultTlsVersions` задает конфигурацию по умолчанию, чтобы разрешить операционной системе для выбора протокола. Значение `true` задает наибольшее недоступно TLS1.2 протокола по умолчанию.

Для приложений, предназначенных для .NET Framework 4.7.1 и более поздних версиях, это значение по умолчанию `false`. Для приложений, предназначенных для .NET Framework 4,7 и более ранних версий, это значение по умолчанию `true`.

Дополнительные сведения о протоколах TLS см. в разделе [устранение рисков: протоколы TLS](../migration-guide/mitigation-tls-protocols.md). Дополнительные сведения о `AppContext` коммутаторов, в разделе [ `<AppContextSwitchOverrides> Element` ](../configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md).

## <a name="configuring-security-via-the-windows-registry"></a>Настройка параметров безопасности в реестре Windows

При установке одного или обоих `AppContext` коммутаторы не представляется возможным, можно управлять протоколы безопасности, которые приложение использует с разделами реестра Windows, описанные в этом разделе. Можно не будет использовать один или оба `AppContext` переключается, если приложение предназначено для версии платформы .NET Framework более ранней, чем 4.6 или не удается изменить файл конфигурации. Если вы хотите настроить безопасность с реестром, затем не указать значение протокола безопасности в коде; Поэтому это переопределит реестра.

Имена ключей реестра похожи на соответствующие имена `AppContext` переключается, но без `DontEnable` присоединяется к имени. Например `AppContext` переключения `DontEnableSchUseStrongCrypto` , раздел реестра называется [SchUseStrongCrypto](#schusestrongcrypto).

Эти ключи будут доступны во всех версиях .NET Framework, в которых нет последние исправления безопасности. В разделе [обновления для системы безопасности](#security-updates).

Все описанные ниже разделы реестра имеют тот же эффект ли вы выполняете сети HTTP (<xref:System.Net.ServicePointManager>) или TCP сокеты сети (<xref:System.Net.Security.SslStream>).

### <a name="schusestrongcrypto"></a>SchUseStrongCrypto

`HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SchUseStrongCrypto` Раздел реестра имеет значение типа DWORD. Значение 1 вызывает приложение на использование надежного шифрования. Устойчивое шифрование использует более безопасные сетевые протоколы (TLS 1.2, TLS 1.1 и TLS 1.0) и блокирует протоколы, которые не являются безопасными. Значение 0 отключает устойчивого шифрования. Дополнительные сведения см. в разделе [SCH_USE_STRONG_CRYPTO флаг](#the-schusestrongcrypto-flag).

Если приложение предназначено для .NET Framework 4.6 или более поздней версии, этот ключ по умолчанию используется значение 1. Это безопасности по умолчанию, которое рекомендуется использовать. Если приложение работает в .NET Framework 4.6, но на более раннюю версию, затем ключ по умолчанию 0. В этом случае следует явным образом присвойте ему значение 1.

Этот ключ должен иметь значение 0 только в том случае, если необходимо соединиться с предыдущих версий служб, которые не поддерживают надежного шифрования и не могут быть обновлены.

### <a name="systemdefaulttlsversions"></a>SystemDefaultTlsVersions

`HKEY_LOCAL_MACHINE\SOFTWARE\[Wow6432Node\]Microsoft\.NETFramework\<VERSION>: SystemDefaultTlsVersions` Раздел реестра имеет значение типа DWORD. Значение 1, вызывает приложение разрешить операционной системе выбрать протокол. Значение 0 вызывает приложения к использованию протоколов, которые используются платформой .NET Framework.

`<VERSION>` должно быть v4.0.30319 (для .NET Framework 4 и более поздних версий) или v2.0.50727 (для .NET Framework 3.5).

Если приложение предназначено для .NET Framework 4.7 или более поздней версии, этот ключ по умолчанию используется значение 1. Это безопасности по умолчанию, которое рекомендуется использовать. Если приложение запускается в .NET Framework 4.7 или более поздних версиях, но на более раннюю версию, ключ по умолчанию равно 0. В этом случае следует явным образом присвойте ему значение 1.

Дополнительные сведения см. в разделе [накопительный пакет обновления для Windows 10 версии 1511 и Windows Server 2016 Technical Preview 4: 10 мая 2016 г](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016).

Дополнительные сведения о .NET framework 3.5.1. в разделе [поддержка версий по умолчанию TLS системы включены в .NET Framework 3.5.1 на Windows 7 с пакетом обновления 1 и Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework).

Следующие _. REG_ файл задает их наиболее безопасные значения разделов реестра и их вариантов:

```
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

## <a name="configuring-schannel-protocols-in-the-windows-registry"></a>Настройка Schannel протоколов в реестре Windows

Реестра можно использовать для точного управления протоколы, которые согласовывает приложения клиента или сервера. Сетевые приложения проходит через Schannel (который — это другое имя для [безопасный канал](https://msdn.microsoft.com/library/windows/desktop/aa380123). Настроив `Schannel`, можно настроить поведение приложения.

Начать с `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SecurityProviders\SCHANNEL\Protocols` раздел реестра. В данном разделе, можно создать все разделы в наборе `SSL 2.0`, `SSL 3.0`, `TLS 1.0`, `TLS 1.1`, и `TLS 1.2`. В каждом из этих подразделов, можно создать подразделов `Client` и/или `Server`. В разделе `Client` и `Server`, можно создать параметр DWORD `DisabledByDefault` (0 или 1) и `Enabled` (0 или 0xFFFFFFFF).

## <a name="the-schusestrongcrypto-flag"></a>The SCH_USE_STRONG_CRYPTO flag

При включении (по умолчанию, `AppContext` перейти, или в реестре Windows), платформа .NET Framework использует `SCH_USE_STRONG_CRYPTO` флаг, когда приложение запрашивает протокол безопасности TLS. `SCH_USE_STRONG_CRYPTO` Флаг может быть включен по умолчанию с `AppContext` перейти, или с реестром. Операционная система передает флаг `Schannel`задать для него отключить известных слабых алгоритмов шифрования, шифра, наборы и версиям протокола TLS/SSL, в противном случае можно включить для улучшения возможностей взаимодействия. Дополнительные сведения:

- [Безопасный канал](https://msdn.microsoft.com/library/windows/desktop/aa380123)
- [Структура SCHANNEL_CRED](https://msdn.microsoft.com/library/windows/desktop/aa379810)

`SCH_USE_STRONG_CRYPTO` Флаг также передается `Schannel` при использовании явно `Tls` (TLS 1.0) `Tls11`, или `Tls12` значений из перечисления <xref:System.Net.SecurityProtocolType> или <xref:System.Security.Authentication.SslProtocols>.

## <a name="security-updates"></a>Обновления для системы безопасности

Рекомендации в данной статье, зависят от установки последних обновлений безопасности. Эти обновления включают возможность использования расширенных 4.7 .NET Framework и более поздних версий компонентов. Последние обновления безопасности, важно, если ваше приложение запускается .NET Framework 4.7 и более поздних версиях (даже если он предназначен для более ранней версии).

Чтобы обновить .NET Framework, чтобы разрешить операционной системе выбрать лучший версии TLS для использования, необходимо установить по крайней мере:

- [.NET Framework августа 2017 г. Предварительный просмотр свертки качество](https://blogs.msdn.microsoft.com/dotnet/2017/08/16/net-framework-august-2017-preview-of-quality-rollup).
- **Или** [2017 г сентября безопасность платформы .NET Framework и качество Rollup](https://blogs.msdn.microsoft.com/dotnet/2017/09/12/net-framework-september-2017-security-and-quality-rollup).

См. также:

- [Версии платформы .NET framework и зависимости](../migration-guide/versions-and-dependencies.md)
- [Как: Определение установленных версий платформы .NET Framework](../migration-guide/how-to-determine-which-versions-are-installed.md).

## <a name="support-for-tls-12"></a>Поддержка TLS 1.2

Для вашего приложения для согласования TLS 1.2, операционной системы и версии платформы .NET Framework и должны поддерживать TLS 1.2.

**Требования к операционной системе для поддержки TLS 1.2**

Чтобы включить или повторно включить в системе, которая их поддерживает TLS 1.2 и/или TLS 1.1, см. [параметры реестра Transport Layer Security (TLS)](/windows-server/security/tls/tls-registry-settings).

| **OS** | **Поддержка TLS 1.2** |
| --- | --- |
| Windows 10</br>Windows Server 2016 | Поддерживается и включен по умолчанию. |
| Windows 8.1</br>Windows Server 2012 R2 | Поддерживается и включен по умолчанию. |
| Windows 8.0</br>Windows Server 2012 | Поддерживается и включен по умолчанию. |
| Windows 7 SP1</br>Windows Server 2008 R2 с пакетом обновления 1 (SP1) | Поддерживается, но не включено по умолчанию. В разделе [параметры реестра Transport Layer Security (TLS)](/windows-server/security/tls/tls-registry-settings) веб-страницы, Дополнительные сведения о том, как включить TLS 1.2. |
| Windows Server 2008 | Поддержка TLS 1.2 и TLS 1.1 требуется обновить. В разделе [обновления для добавления поддержки TLS 1.1 и TLS 1.2 в Windows Server 2008 SP2](https://support.microsoft.com/help/4019276/update-to-add-support-for-tls-1-1-and-tls-1-2-in-windows-server-2008-s). |
| Windows Vista | Не поддерживается. |

Сведения о какой TLS/SSL включенные протоколы по умолчанию для каждой версии Windows см. [протоколы TLS/SSL (Schannel SSP)](https://msdn.microsoft.com/library/windows/desktop/mt808159).

**Требования для поддержки TLS 1.2 на .NET Framework 3.5**

В этой таблице показаны обновления ОС необходимо для поддержки TLS 1.2 на .NET Framework 3.5. Мы рекомендуем применять все обновления операционной системы.

| **OS** | **Минимального обновления, необходимые для поддержки TLS 1.2 на .NET Framework 3.5** |
| --- | --- |
| Windows 10</br>Windows Server 2016 | [Накопительный пакет обновления для Windows 10 версии 1511 и Windows Server 2016 Technical предварительного просмотра 4: 10 мая 2016 г.](https://support.microsoft.com/help/3156421/cumulative-update-for-windows-10-version-1511-and-windows-server-2016) |
| Windows 8.1</br>Windows Server 2012 R2 | [Поддержка версий по умолчанию TLS системы включены в .NET Framework 3.5 в Windows 8.1 и Windows Server 2012 R2](https://support.microsoft.com/help/3154520/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 8.0</br>Windows Server 2012 | [Поддержка версий по умолчанию TLS системы включены в .NET Framework 3.5 в Windows Server 2012](https://support.microsoft.com/help/3154519/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows 7 SP1</br>Windows Server 2008 R2 с пакетом обновления 1 (SP1) | [Поддержка версий по умолчанию TLS системы включены в .NET Framework 3.5.1 на Windows 7 с пакетом обновления 1 и Server 2008 R2 SP1](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Server 2008 | [Поддержка версий по умолчанию TLS системы включены в .NET Framework 2.0 с пакетом обновления 2 в Windows Vista SP2 и Server 2008 SP2](https://support.microsoft.com/help/3154517/support-for-tls-system-default-versions-included-in-the--net-framework) |
| Windows Vista | Не поддерживается |

## <a name="azure-cloud-services"></a>Облачные службы Azure

Если вы используете [облачных служб Azure](https://azure.microsoft.com/services/cloud-services/) рабочих и веб-роли для размещения и запустите приложение, существуют определенные рекомендации, которые необходимо принимать во внимание для поддержки TLS 1.2.

### <a name="net-framework-47-is-not-installed-on-azure-guest-os-by-default"></a>.NET framework 4.7 не установлена на гостевой ОС Azure по умолчанию

Последнюю версию, установленную в последнем выпуске гостевой ОС Azure семейства-5 (Windows Server 2016) — 4.6.2. Версий платформы .NET Framework, установленных на каждом гостевой ОС Azure см. [выпуски гостевой ОС Azure и Матрица совместимости пакетов SDK](https://docs.microsoft.com/azure/cloud-services/cloud-services-guestos-update-matrix).

Если приложение предназначено для версии .NET Framework, не доступны в версии гостевой ОС Azure, необходимо установить его. В разделе [установить .NET на роли Azure облачной службы](https://docs.microsoft.com/azure/cloud-services/cloud-services-dotnet-install-dotnet). Если framework установки необходима перезагрузка, роли службы также может перезапуститься перед переходом в состояние готовности.

### <a name="azure-guest-os-registry-settings"></a>Параметры реестра Azure гостевой ОС

Гостевая ОС Azure из образа для [облачных служб Azure](https://azure.microsoft.com/services/cloud-services/) уже `SchUseStrongCrypto` реестра присвоено значение 1. Дополнительные сведения см. в разделе [SchUseStrongCrypto](#schusestrongcrypto).

Задать [SystemDefaultTlsVersions](#systemdefaulttlsversions) раздел реестра на 1. В разделе [Настройка безопасности в реестре Windows](#configuring-security-via-the-windows-registry).
