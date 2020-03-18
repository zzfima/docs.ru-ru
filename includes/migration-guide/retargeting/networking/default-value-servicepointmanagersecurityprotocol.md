---
ms.openlocfilehash: 122a5ab3e2def7c19d3d523881fcb15df4dbca26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "68235588"
---
### <a name="default-value-of-servicepointmanagersecurityprotocol-is-securityprotocoltypesystemdefault"></a>Значение по умолчанию ServicePointManager.SecurityProtocol — SecurityProtocolType.System.Default

|   |   |
|---|---|
|Подробнее|Начиная с приложений, ориентированных на .NET Framework 4.7, свойство <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> имеет значение <xref:System.Net.SecurityProtocolType.SystemDefault?displayProperty=nameWithType>. Это изменение позволяет сетевым API-интерфейсам .NET Framework на основе SslStream (таких как FTP, HTTPS и SMTP) наследовать протоколы безопасности по умолчанию из операционной системы вместо использования жестко запрограммированных значений, определенных в .NET Framework. Значение по умолчанию зависит от операционной системы и пользовательской настройки, выполненной системным администратором. Сведения о протоколе SChannel по умолчанию в каждой версии операционной системы Windows см. в разделе [Протоколы TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/protocols-in-tls-ssl--schannel-ssp-).</p>В приложениях, предназначенных для более ранних версий платформы .NET Framework, значение по умолчанию свойства <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType> зависит от версии целевой платформы .NET Framework. Дополнительные сведения см. в разделе [Изменение целевой платформы для миграции с .NET Framework 4.5.2 на 4.6](~/docs/framework/migration-guide/retargeting/4.5.2-4.6.md#networking).|
|Предложение|Это изменение касается только приложений, предназначенных для .NET Framework 4.7 или более поздних версий. <br>Если вы предпочитаете использовать определенный протокол, а не полагаться на параметры системы по умолчанию, можно явно задать значение свойства <xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType>.<br>Если такое изменение нежелательно, от него можно отказаться, добавив параметр конфигурации в раздел [\<runtime>](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения. В следующем примере показан как раздел <code>&lt;runtime&gt;</code>, так и параметр отключения <code>Switch.System.Net.DontEnableSystemDefaultTlsVersions</code>:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSystemDefaultTlsVersions=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Version|4.7|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Net.ServicePointManager.SecurityProtocol?displayProperty=nameWithType></li></ul>|
