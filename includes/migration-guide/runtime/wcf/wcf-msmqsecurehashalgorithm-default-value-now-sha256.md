---
ms.openlocfilehash: ce8e162e11802de1b06bfbc63d5c55de67ef23df
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857268"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="50f19-101">MsmqSecureHashAlgorithm WCF теперь по умолчанию имеет значение SHA256</span><span class="sxs-lookup"><span data-stu-id="50f19-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="50f19-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="50f19-102">Details</span></span>|<span data-ttu-id="50f19-103">Начиная с версии .NET Framework 4.7.1, в WCF для подписывания сообщений Msmq по умолчанию используется алгоритм SHA256.</span><span class="sxs-lookup"><span data-stu-id="50f19-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="50f19-104">В .NET Framework 4.7 и более ранних версий для подписывания сообщений по умолчанию используется алгоритм SHA1.</span><span class="sxs-lookup"><span data-stu-id="50f19-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="50f19-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="50f19-105">Suggestion</span></span>|<span data-ttu-id="50f19-106">Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config:</span><span class="sxs-lookup"><span data-stu-id="50f19-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="50f19-107">Область</span><span class="sxs-lookup"><span data-stu-id="50f19-107">Scope</span></span>|<span data-ttu-id="50f19-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="50f19-108">Minor</span></span>|
|<span data-ttu-id="50f19-109">Version</span><span class="sxs-lookup"><span data-stu-id="50f19-109">Version</span></span>|<span data-ttu-id="50f19-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="50f19-110">4.7.1</span></span>|
|<span data-ttu-id="50f19-111">Type</span><span class="sxs-lookup"><span data-stu-id="50f19-111">Type</span></span>|<span data-ttu-id="50f19-112">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="50f19-112">Runtime</span></span>|
