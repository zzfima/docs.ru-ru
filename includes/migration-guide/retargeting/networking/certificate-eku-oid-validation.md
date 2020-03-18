---
ms.openlocfilehash: ee9bba91a2c4e11bd005fedb8adf0c2e7c7b0d3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67804551"
---
### <a name="certificate-eku-oid-validation"></a>Проверка OID EKU сертификата

|   |   |
|---|---|
|Подробнее|Начиная с .NET Framework 4.6 классы <xref:System.Net.Security.SslStream> или <xref:System.Net.ServicePointManager> выполняют проверку идентификатора объекта (OID) расширенного использования ключа (EKU). Расширение расширенного использования ключа (EKU) — это коллекция идентификаторов объекта (OID), которые указывают приложения, использующие ключ. При проверке OID EKU используются обратные вызовы удаленного сертификата, чтобы у удаленного сертификата были правильные OID для указанных целей.|
|Предложение|Если это изменение нежелательно, можно отключить проверку OID EKU сертификата, добавив следующий переключатель в [\<AppContextSwitchOverrides>](~/docs/framework/configure-apps/file-schema/runtime/appcontextswitchoverrides-element.md) в [`](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) в файле конфигурации приложения:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides&#13;&#10;value=&quot;Switch.System.Net.DontCheckCertificateEKUs=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre> <blockquote> [!IMPORTANT] Этот параметр предоставляется исключительно для обратной совместимости. Его использование в других целях не рекомендуется.</blockquote> |
|Область|Дополнительный номер|
|Version|4.6|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Net.Security.SslStream?displayProperty=nameWithType></li><li><xref:System.Net.ServicePointManager?displayProperty=nameWithType></li><li><xref:System.Net.Http.HttpClient?displayProperty=nameWithType></li><li><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType></li><li><xref:System.Net.HttpWebRequest?displayProperty=nameWithType></li><li><xref:System.Net.FtpWebRequest?displayProperty=nameWithType></li></ul>|
