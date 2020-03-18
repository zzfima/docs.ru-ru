---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857268"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>MsmqSecureHashAlgorithm WCF теперь по умолчанию имеет значение SHA256

|   |   |
|---|---|
|Подробнее|Начиная с версии .NET Framework 4.7.1, в WCF для подписывания сообщений Msmq по умолчанию используется алгоритм SHA256. В .NET Framework 4.7 и более ранних версий для подписывания сообщений по умолчанию используется алгоритм SHA1.|
|Предложение|Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Version|4.7.1|
|Type|Параметры выполнения|
