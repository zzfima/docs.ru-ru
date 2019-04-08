---
ms.openlocfilehash: a2d4b7592727ca20ee79867094d6972eb9c4baed
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760460"
---
### <a name="wcf-msmqsecurehashalgorithm-default-value-is-now-sha256"></a><span data-ttu-id="485fe-101">MsmqSecureHashAlgorithm WCF теперь по умолчанию имеет значение SHA256</span><span class="sxs-lookup"><span data-stu-id="485fe-101">WCF MsmqSecureHashAlgorithm default value is now SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="485fe-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="485fe-102">Details</span></span>|<span data-ttu-id="485fe-103">Начиная с версии .NET Framework 4.7.1, в WCF для подписывания сообщений Msmq по умолчанию используется алгоритм SHA256.</span><span class="sxs-lookup"><span data-stu-id="485fe-103">Starting with the .NET Framework 4.7.1, the default message signing algorithm in WCF for Msmq messages is SHA256.</span></span> <span data-ttu-id="485fe-104">В .NET Framework 4.7 и более ранних версий для подписывания сообщений по умолчанию используется алгоритм SHA1.</span><span class="sxs-lookup"><span data-stu-id="485fe-104">In the .NET Framework 4.7 and earlier versions, the default message signing algorithm is SHA1.</span></span>|
|<span data-ttu-id="485fe-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="485fe-105">Suggestion</span></span>|<span data-ttu-id="485fe-106">Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config:</span><span class="sxs-lookup"><span data-stu-id="485fe-106">If you run into compatibility issues with this change on the .NET Framework 4.7.1 or later, you can opt-out the change by adding the following line to the <code>&lt;runtime&gt;</code>section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InMsmqEncryptionAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="485fe-107">Область</span><span class="sxs-lookup"><span data-stu-id="485fe-107">Scope</span></span>|<span data-ttu-id="485fe-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="485fe-108">Minor</span></span>|
|<span data-ttu-id="485fe-109">Версия</span><span class="sxs-lookup"><span data-stu-id="485fe-109">Version</span></span>|<span data-ttu-id="485fe-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="485fe-110">4.7.1</span></span>|
|<span data-ttu-id="485fe-111">Тип</span><span class="sxs-lookup"><span data-stu-id="485fe-111">Type</span></span>|<span data-ttu-id="485fe-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="485fe-112">Runtime</span></span>|

