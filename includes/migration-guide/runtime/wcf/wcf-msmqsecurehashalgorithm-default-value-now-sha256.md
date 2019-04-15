---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59236223"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a>MsmqSecureHashAlgorithm WCF теперь по умолчанию имеет значение SHA256

|   |   |
|---|---|
|Подробные сведения|Начиная с версии .NET Framework 4.7.1, в WCF для подписывания сообщений Msmq по умолчанию используется алгоритм SHA256. В .NET Framework 4.7 и более ранних версий для подписывания сообщений по умолчанию используется алгоритм SHA1.|
|Предложение|Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.7.1|
|Тип|Среда выполнения|
