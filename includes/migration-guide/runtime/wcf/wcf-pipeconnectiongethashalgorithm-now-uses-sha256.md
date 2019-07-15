---
ms.openlocfilehash: 71f61f23a8b17459610d253766a99e594f09428e
ms.sourcegitcommit: d55e14eb63588830c0ba1ea95a24ce6c57ef8c8c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2019
ms.locfileid: "67857205"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a>WCF PipeConnection.GetHashAlgorithm теперь использует SHA256

|   |   |
|---|---|
|Подробные сведения|Начиная с версии .NET Framework 4.7.1 Windows Communication Foundation использует хэш SHA256 для формирования случайных имен для именованных каналов. В .NET Framework 4.7 и более ранних версиях используется хэш SHA-1.|
|Предложение|Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config:<pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|Область|Дополнительный номер|
|Версия|4.7.1|
|Тип|Среда выполнения|

