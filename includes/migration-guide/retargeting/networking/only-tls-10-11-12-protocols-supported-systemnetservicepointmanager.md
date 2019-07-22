---
ms.openlocfilehash: 5b531dc23feb311a797823dfa2a4d853859f9e18
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/16/2019
ms.locfileid: "68235578"
---
### <a name="only-tls-10-11-and-12-protocols-supported-in-systemnetservicepointmanager-and-systemnetsecuritysslstream"></a>В System.Net.ServicePointManager и System.Net.Security.SslStream поддерживаются только протоколы Tls 1.0, 1.1 и 1.2

|   |   |
|---|---|
|Подробные сведения|Начиная с версии .NET Framework 4.6, классы <xref:System.Net.ServicePointManager> и <xref:System.Net.Security.SslStream> могут использовать только один из трех протоколов: Tls1.0, Tls1.1 или Tls1.2. Протокол SSL 3.0 и шифрование RC4 не поддерживаются.|
|Предложение|Рекомендуется обновить приложения на стороне сервера для использования Tls1.0, Tls1.1 или Tls1.2. Если это невозможно, или если клиентские приложения не работают, можно использовать класс <xref:System.AppContext?displayProperty=name>, чтобы отказаться от этой функции одним из двух способов.<ol><li>Путем программной установки параметров совместимости в <xref:System.AppContext?displayProperty=name>, как описано [здесь](https://devblogs.microsoft.com/dotnet/net-announcements-at-build-2015/#dotnet46).</li><li>путем добавления следующей строки в раздел <code>&lt;runtime&gt;</code> файла app.config:</li></ol><pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Net.DontEnableSchUseStrongCrypto=true&quot;/&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.6|
|Тип|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Net.SecurityProtocolType.Ssl3?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.None?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.Ssl2?displayProperty=nameWithType></li><li><xref:System.Security.Authentication.SslProtocols.Ssl3?displayProperty=nameWithType></li></ul>|
