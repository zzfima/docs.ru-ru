---
title: Устранение рисков. Протоколы TLS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
ms.openlocfilehash: 45225d73ac60564d3e22c73270faab6b4e04d697
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2019
ms.locfileid: "73457834"
---
# <a name="mitigation-tls-protocols"></a><span data-ttu-id="7ae59-102">Устранение рисков. Протоколы TLS</span><span class="sxs-lookup"><span data-stu-id="7ae59-102">Mitigation: TLS Protocols</span></span>
<span data-ttu-id="7ae59-103">Начиная с версии .NET Framework 4.6 классы <xref:System.Net.ServicePointManager?displayProperty=nameWithType> и <xref:System.Net.Security.SslStream?displayProperty=nameWithType> могут использовать один из трех протоколов: Tls1.0, Tls1.1 или Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="7ae59-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager?displayProperty=nameWithType> and <xref:System.Net.Security.SslStream?displayProperty=nameWithType> classes are allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="7ae59-104">Протокол SSL 3.0 и шифрование RC4 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="7ae59-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="7ae59-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="7ae59-105">Impact</span></span>  
 <span data-ttu-id="7ae59-106">Это изменение влияет:</span><span class="sxs-lookup"><span data-stu-id="7ae59-106">This change affects:</span></span>  
  
- <span data-ttu-id="7ae59-107">на все приложения, использующие протокол SSL для связи с сервером HTTPS или сервером сокетов с помощью любого из следующих типов: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> и <xref:System.Net.Security.SslStream>;</span><span class="sxs-lookup"><span data-stu-id="7ae59-107">Any app that uses SSL to talk to an HTTPS server or a socket server using any of the following types: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient>, and <xref:System.Net.Security.SslStream>.</span></span>  
  
- <span data-ttu-id="7ae59-108">на все приложения на стороне сервера, которые нельзя обновить для поддержки Tls1.0, Tls1.1 или Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="7ae59-108">Any server-side app that cannot be upgraded to support Tls1.0, Tls1.1, or Tls 1.2..</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="7ae59-109">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="7ae59-109">Mitigation</span></span>  
 <span data-ttu-id="7ae59-110">Рекомендуется обновить приложения на стороне сервера для использования Tls1.0, Tls1.1 или Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="7ae59-110">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="7ae59-111">Если это невозможно, или если клиентские приложения не работают, можно использовать класс <xref:System.AppContext>, чтобы отказаться от этой функции одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="7ae59-111">If this is not feasible, or if client apps are broken, the <xref:System.AppContext> class can be used to opt out of this feature in either of two ways:</span></span>  
  
- <span data-ttu-id="7ae59-112">Программно с помощью фрагмента кода следующего вида:</span><span class="sxs-lookup"><span data-stu-id="7ae59-112">Programmatically, by using a code snippet like the following:</span></span>  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     <span data-ttu-id="7ae59-113">Поскольку объект <xref:System.Net.ServicePointManager> инициализируется только один раз, определение этих параметров совместимости должно быть первым действием приложения.</span><span class="sxs-lookup"><span data-stu-id="7ae59-113">Because the <xref:System.Net.ServicePointManager> object is initialized only once, defining these compatibility settings must be the first thing the application does.</span></span>  
  
- <span data-ttu-id="7ae59-114">Путем добавления следующей строки в раздел [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) файла app.config:</span><span class="sxs-lookup"><span data-stu-id="7ae59-114">By adding the following line to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 <span data-ttu-id="7ae59-115">Следует, тем не менее, заметить, что отказ от поведения по умолчанию не рекомендуется, поскольку приводит к снижению безопасности приложения.</span><span class="sxs-lookup"><span data-stu-id="7ae59-115">Note, however, that opting out of the default behavior is not recommended, since it makes the application less secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ae59-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7ae59-116">See also</span></span>

- [<span data-ttu-id="7ae59-117">Совместимость приложений</span><span class="sxs-lookup"><span data-stu-id="7ae59-117">Application compatibility</span></span>](application-compatibility.md)
