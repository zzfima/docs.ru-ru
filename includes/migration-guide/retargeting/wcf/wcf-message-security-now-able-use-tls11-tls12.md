---
ms.openlocfilehash: 3b7b50700541649a785fa9bbe3ecc56c2697fbfc
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58760348"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="023b3-101">Для безопасности сообщений WCF теперь могут использоваться TLS1.1 и TLS1.2</span><span class="sxs-lookup"><span data-stu-id="023b3-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

|   |   |
|---|---|
|<span data-ttu-id="023b3-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="023b3-102">Details</span></span>|<span data-ttu-id="023b3-103">Начиная с .NET Framework 4.7 клиенты могут настроить в параметрах конфигурации приложения не только SSL3.0 и TLS1.0, но и TLS1.1 или TLS1.2.</span><span class="sxs-lookup"><span data-stu-id="023b3-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>|
|<span data-ttu-id="023b3-104">Предложение</span><span class="sxs-lookup"><span data-stu-id="023b3-104">Suggestion</span></span>|<span data-ttu-id="023b3-105">В .NET Framework 4.7 поддержка TLS1.1 и TLS1.2 в безопасности сообщений WCF по умолчанию отключена.</span><span class="sxs-lookup"><span data-stu-id="023b3-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="023b3-106">Вы можете включить ее, добавив следующую строку в раздел <code>&lt;runtime&gt;</code> файла app.config или web.config:</span><span class="sxs-lookup"><span data-stu-id="023b3-106">You can enable it by adding the following line to the <code>&lt;runtime&gt;</code> section of the app.config or web.config file:</span></span><pre><code class="lang-xml">&lt;runtime&gt;&#13;&#10;&lt;AppContextSwitchOverrides value=&quot;Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false&quot; /&gt;&#13;&#10;&lt;/runtime&gt;&#13;&#10;</code></pre>|
|<span data-ttu-id="023b3-107">Область</span><span class="sxs-lookup"><span data-stu-id="023b3-107">Scope</span></span>|<span data-ttu-id="023b3-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="023b3-108">Edge</span></span>|
|<span data-ttu-id="023b3-109">Версия</span><span class="sxs-lookup"><span data-stu-id="023b3-109">Version</span></span>|<span data-ttu-id="023b3-110">4.7</span><span class="sxs-lookup"><span data-stu-id="023b3-110">4.7</span></span>|
|<span data-ttu-id="023b3-111">Тип</span><span class="sxs-lookup"><span data-stu-id="023b3-111">Type</span></span>|<span data-ttu-id="023b3-112">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="023b3-112">Retargeting</span></span>|

