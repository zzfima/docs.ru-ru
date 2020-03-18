---
ms.openlocfilehash: db076d6799e4de5b8610cf9c1aac79b5386a7229
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859031"
---
### <a name="default-signedxml-and-signedxms-algorithms-changed-to-sha256"></a>Алгоритмы SignedXML и SignedXMS по умолчанию изменены на SHA256

|   |   |
|---|---|
|Подробнее|В .NET Framework 4.7 и более ранних версий SignedXML и SignedCMS по умолчанию изменены на SHA-1 для некоторых операций. Начиная с .NET Framework 4.7.1 по умолчанию для этих операций включен SHA256. Это изменение было необходимо, поскольку алгоритм SHA-1 больше не считается безопасным.|
|Предложение|Существует два новых значения переключения контекста для выбора алгоритма SHA-1 (небезопасно) или SHA256 по умолчанию:<ul><li>Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms</li><li>Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms</li></ul>Если в приложениях, предназначенных для .NET Framework 4.7.1 и более поздних версий, использование SHA256 нежелательно, можно восстановить алгоритм по умолчанию SHA-1, добавив следующую конфигурацию в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=true;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=true&quot; /&gt;&#13;&#10;</code></pre>В приложениях, предназначенных для .NET Framework 4.7 и более ранних версий, вы можете выбрать это изменение, добавив следующую конфигурацию в раздел [runtime](~/docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла конфигурации приложения:<pre><code class="lang-xml">&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.Xml.UseInsecureHashAlgorithms=false;Switch.System.Security.Cryptography.Pkcs.UseInsecureHashAlgorithms=false&quot; /&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Version|4.7.1|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.Pkcs.CmsSigner?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.Reference?displayProperty=nameWithType></li></ul>|
