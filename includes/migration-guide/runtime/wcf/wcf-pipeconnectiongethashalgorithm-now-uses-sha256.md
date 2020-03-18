---
ms.openlocfilehash: 318609c15d2e0b9a7ee59b38463735b33ef87974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67857205"
---
### <a name="wcf-pipeconnectiongethashalgorithm-now-uses-sha256"></a><span data-ttu-id="94b2c-101">WCF PipeConnection.GetHashAlgorithm теперь использует SHA256</span><span class="sxs-lookup"><span data-stu-id="94b2c-101">WCF PipeConnection.GetHashAlgorithm now uses SHA256</span></span>

|   |   |
|---|---|
|<span data-ttu-id="94b2c-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="94b2c-102">Details</span></span>|<span data-ttu-id="94b2c-103">Начиная с версии .NET Framework 4.7.1 Windows Communication Foundation использует хэш SHA256 для формирования случайных имен для именованных каналов.</span><span class="sxs-lookup"><span data-stu-id="94b2c-103">Starting with the .NET Framework 4.7.1, Windows Communication Foundation uses a SHA256 hash to generate random names for named pipes.</span></span> <span data-ttu-id="94b2c-104">В .NET Framework 4.7 и более ранних версиях используется хэш SHA-1.</span><span class="sxs-lookup"><span data-stu-id="94b2c-104">In the .NET Framework 4.7 and earlier versions, it used a SHA1 hash.</span></span>|
|<span data-ttu-id="94b2c-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="94b2c-105">Suggestion</span></span>|<span data-ttu-id="94b2c-106">Если из-за этого изменения в .NET Framework 4.7.1 или более поздних версий вы сталкиваетесь с проблемами совместимости, вы можете отключить это изменение, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config:</span><span class="sxs-lookup"><span data-stu-id="94b2c-106">If you run into compatibility issue with this change on the .NET Framework 4.7.1 or later, you can opt-out it by adding the following line to the <code>&lt;runtime&gt;</code> section of your app.config file:</span></span><pre><code class="lang-xml">&lt;configuration&gt;&#13;&#10;&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.UseSha1InPipeConnectionGetHashAlgorithm=true&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;&lt;/configuration&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="94b2c-107">Область</span><span class="sxs-lookup"><span data-stu-id="94b2c-107">Scope</span></span>|<span data-ttu-id="94b2c-108">Дополнительный номер</span><span class="sxs-lookup"><span data-stu-id="94b2c-108">Minor</span></span>|
|<span data-ttu-id="94b2c-109">Version</span><span class="sxs-lookup"><span data-stu-id="94b2c-109">Version</span></span>|<span data-ttu-id="94b2c-110">4.7.1</span><span class="sxs-lookup"><span data-stu-id="94b2c-110">4.7.1</span></span>|
|<span data-ttu-id="94b2c-111">Type</span><span class="sxs-lookup"><span data-stu-id="94b2c-111">Type</span></span>|<span data-ttu-id="94b2c-112">Параметры выполнения</span><span class="sxs-lookup"><span data-stu-id="94b2c-112">Runtime</span></span>|
