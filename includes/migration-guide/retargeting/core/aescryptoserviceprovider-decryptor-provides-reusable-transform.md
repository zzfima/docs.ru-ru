---
ms.openlocfilehash: c008809606372c84b05a2facd1cac1293382aed4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859344"
---
### <a name="aescryptoserviceprovider-decryptor-provides-a-reusable-transform"></a>Дешифратор AesCryptoServiceProvider предоставляет преобразование для повторного использования

|   |   |
|---|---|
|Подробнее|Начиная с приложений, предназначенных для .NET Framework 4.6.2, дешифратор <xref:System.Security.Cryptography.AesCryptoServiceProvider> возвращает преобразование, которое можно использовать повторно. Это преобразование повторно инициализируется после вызова <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=name> и его можно использовать снова. В приложениях, предназначенных для более ранних версий платформы .NET Framework, попытка повторного использования дешифратора путем вызова <xref:System.Security.Cryptography.CryptoAPITransform.TransformBlock(System.Byte[],System.Int32,System.Int32,System.Byte[],System.Int32)?displayProperty=name> после вызова <xref:System.Security.Cryptography.CryptoAPITransform.TransformFinalBlock(System.Byte[],System.Int32,System.Int32)?displayProperty=name> приводит к исключению <xref:System.Security.Cryptography.CryptographicException> или к повреждению данных.|
|Предложение|Влияние этого изменения должно быть минимальным, поскольку это ожидаемое поведение. В приложениях, которые зависят от прежнего поведения, можно отказаться от его изменения, добавив следующий параметр конфигурации в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>Кроме того, это поведение можно включить для приложений, предназначенных для предыдущих версий .NET Framework, но работающих под управлением .NET Framework 4.6.2 или более поздних версий. Для этого добавьте в раздел <code>&lt;runtime&gt;</code> файла конфигурации приложения следующий параметр:<pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.Security.Cryptography.AesCryptoServiceProvider.DontCorrectlyResetDecryptor=false&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Version|4.6.2|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.Security.Cryptography.AesCryptoServiceProvider.CreateDecryptor?displayProperty=nameWithType></li></ul>|
