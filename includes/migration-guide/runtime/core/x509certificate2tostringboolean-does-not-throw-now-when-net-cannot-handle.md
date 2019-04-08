---
ms.openlocfilehash: d48519443aeee05617538cf2cc12bea49ad3e16d
ms.sourcegitcommit: 0aca6c5d166d7961a1e354c248495645b97a1dc5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58761327"
---
### <a name="x509certificate2tostringboolean-does-not-throw-now-when-net-cannot-handle-the-certificate"></a><span data-ttu-id="c2a06-101">Теперь метод X509Certificate2.ToString(Boolean) не создает исключение, когда .NET не удается обработать сертификат</span><span class="sxs-lookup"><span data-stu-id="c2a06-101">X509Certificate2.ToString(Boolean) does not throw now when .NET cannot handle the certificate</span></span>

|   |   |
|---|---|
|<span data-ttu-id="c2a06-102">Подробные сведения</span><span class="sxs-lookup"><span data-stu-id="c2a06-102">Details</span></span>|<span data-ttu-id="c2a06-103">В .NET Framework 4.5.2 и более ранних версиях этот метод создавал исключение, если значение <code>true</code> передавалось в параметр verbose и были установлены сертификаты, не поддерживаемые .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c2a06-103">In .NET Framework 4.5.2 and earlier versions, this method would throw if <code>true</code> was passed for the verbose parameter and there were certificates installed that weren't supported by the .NET Framework.</span></span> <span data-ttu-id="c2a06-104">Теперь метод будет выполняться успешно и возвращать допустимую строку, в которой пропущены недоступные части сертификата.</span><span class="sxs-lookup"><span data-stu-id="c2a06-104">Now, the method will succeed and return a valid string that omits the inaccessible portions of the certificate.</span></span>|
|<span data-ttu-id="c2a06-105">Предложение</span><span class="sxs-lookup"><span data-stu-id="c2a06-105">Suggestion</span></span>|<span data-ttu-id="c2a06-106">Любой код, зависящий от <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType>, следует обновить для ожидания того, что в некоторых случаях, когда ранее API возвращал исключение, в возвращаемой строке могут отсутствовать некоторые данные сертификата (например, открытый ключ, закрытый ключ и расширения).</span><span class="sxs-lookup"><span data-stu-id="c2a06-106">Any code depending on <xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType> should be updated to expect that the returned string may exclude some certificate data (such as public key, private key, and extensions) in some cases in which the API would have previously thrown.</span></span>|
|<span data-ttu-id="c2a06-107">Область</span><span class="sxs-lookup"><span data-stu-id="c2a06-107">Scope</span></span>|<span data-ttu-id="c2a06-108">Пограничный случай</span><span class="sxs-lookup"><span data-stu-id="c2a06-108">Edge</span></span>|
|<span data-ttu-id="c2a06-109">Версия</span><span class="sxs-lookup"><span data-stu-id="c2a06-109">Version</span></span>|<span data-ttu-id="c2a06-110">4.6</span><span class="sxs-lookup"><span data-stu-id="c2a06-110">4.6</span></span>|
|<span data-ttu-id="c2a06-111">Тип</span><span class="sxs-lookup"><span data-stu-id="c2a06-111">Type</span></span>|<span data-ttu-id="c2a06-112">Среда выполнения</span><span class="sxs-lookup"><span data-stu-id="c2a06-112">Runtime</span></span>|
|<span data-ttu-id="c2a06-113">Затронутые API</span><span class="sxs-lookup"><span data-stu-id="c2a06-113">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.X509Certificates.X509Certificate2.ToString(System.Boolean)?displayProperty=nameWithType></li></ul>|

