---
ms.openlocfilehash: 0a3dc43ebdc58d54675f2264a8ee56d9f4358cd8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2020
ms.locfileid: "67859087"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="8f48f-101">Для безопасности сообщений WCF теперь могут использоваться TLS1.1 и TLS1.2</span><span class="sxs-lookup"><span data-stu-id="8f48f-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="8f48f-102">Подробнее</span><span class="sxs-lookup"><span data-stu-id="8f48f-102">Details</span></span>|<span data-ttu-id="8f48f-103">Начиная с .NET Framework 4.7 клиенты могут настроить в параметрах конфигурации приложения не только SSL3.0 и TLS1.0, но и TLS1.1 или TLS1.2.</span><span class="sxs-lookup"><span data-stu-id="8f48f-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>|
|<span data-ttu-id="8f48f-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="8f48f-104">Suggestion</span></span>|<span data-ttu-id="8f48f-105">В .NET Framework 4.7 поддержка TLS1.1 и TLS1.2 в безопасности сообщений WCF по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="8f48f-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="8f48f-106">Вы можете включить ее, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config или web.config:</span><span class="sxs-lookup"><span data-stu-id="8f48f-106">You can enable it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config or web.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="8f48f-107">Область</span><span class="sxs-lookup"><span data-stu-id="8f48f-107">Scope</span></span>|<span data-ttu-id="8f48f-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="8f48f-108">Edge</span></span>|
|<span data-ttu-id="8f48f-109">Version</span><span class="sxs-lookup"><span data-stu-id="8f48f-109">Version</span></span>|<span data-ttu-id="8f48f-110">4.7</span><span class="sxs-lookup"><span data-stu-id="8f48f-110">4.7</span></span>|
|<span data-ttu-id="8f48f-111">Type</span><span class="sxs-lookup"><span data-stu-id="8f48f-111">Type</span></span>|<span data-ttu-id="8f48f-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="8f48f-112">Retargeting</span></span>|
