---
ms.openlocfilehash: 141e906077748795e0360cec450a54a9fd170dc9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858956"
---
### <a name="the-default-hash-algorithm-for-wpf-packagedigitalsignaturemanager-is-now-sha256"></a>В качестве хэш-алгоритма по умолчанию для PackageDigitalSignatureManager WPF теперь используется SHA256

|   |   |
|---|---|
|Подробнее|<code>System.IO.Packaging.PackageDigitalSignatureManager</code> реализует функции цифровой подписи для пакетов WPF.  В .NET Framework 4.7 и более ранних версиях для подписывания частей пакетов по умолчанию использовался хэш-алгоритм SHA1 (<xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType>).  С учетом выявленных проблем с безопасностью SHA1, начиная с версии .NET Framework 4.7.1, теперь по умолчанию используется алгоритм SHA256.  Это изменение затрагивает все операции подписывания пакетов, включая документы XPS.|
|Предложение|Тем разработчикам, которые хотят реализовать это изменение в приложениях для версий платформы .NET Framework ниже 4.7.1, а также тем, кому необходимо использовать старые функции в приложениях для версии .NET Framework 4.7.1 или более поздних, необходимо соответствующим образом установить флаг AppContext.  Чтобы использовать алгоритм SHA1, следует установить значение true. Значение false позволяет использовать алгоритм SHA256.<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.MS.Internal.UseSha1AsDefaultHashAlgorithmForDigitalSignatures=true&quot;/&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Пограничный случай|
|Version|4.7.1|
|Type|Изменение целевой платформы|
|Затронутые API|<ul><li><xref:System.IO.Packaging.PackageDigitalSignatureManager.DefaultHashAlgorithm?displayProperty=nameWithType></li></ul>|
