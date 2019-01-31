---
title: Устранение рисков. Протоколы TLS
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 33f97d13-3022-43da-8b18-cdb5c88df9c2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: abfbea052072f0b90c9d018b520b67878d235701
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506814"
---
# <a name="mitigation-tls-protocols"></a><span data-ttu-id="e591c-102">Устранение рисков. Протоколы TLS</span><span class="sxs-lookup"><span data-stu-id="e591c-102">Mitigation: TLS Protocols</span></span>
<span data-ttu-id="e591c-103">Начиная с версии .NET Framework 4.6 классы <xref:System.Net.ServicePointManager?displayProperty=nameWithType> и <xref:System.Net.Security.SslStream?displayProperty=nameWithType> могут использовать один из трех протоколов: Tls1.0, Tls1.1 или Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="e591c-103">Starting with the .NET Framework 4.6, the <xref:System.Net.ServicePointManager?displayProperty=nameWithType> and <xref:System.Net.Security.SslStream?displayProperty=nameWithType> classes are allowed to use one of the following three protocols: Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="e591c-104">Протокол SSL 3.0 и шифрование RC4 не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="e591c-104">The SSL3.0 protocol and RC4 cipher are not supported.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="e591c-105">Последствия</span><span class="sxs-lookup"><span data-stu-id="e591c-105">Impact</span></span>  
 <span data-ttu-id="e591c-106">Это изменение влияет:</span><span class="sxs-lookup"><span data-stu-id="e591c-106">This change affects:</span></span>  
  
-   <span data-ttu-id="e591c-107">на все приложения, использующие протокол SSL для связи с сервером HTTPS или сервером сокетов с помощью любого из следующих типов: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient> и <xref:System.Net.Security.SslStream>;</span><span class="sxs-lookup"><span data-stu-id="e591c-107">Any app that uses SSL to talk to an HTTPS server or a socket server using any of the following types: <xref:System.Net.Http.HttpClient>, <xref:System.Net.HttpWebRequest>, <xref:System.Net.FtpWebRequest>, <xref:System.Net.Mail.SmtpClient>, and <xref:System.Net.Security.SslStream>.</span></span>  
  
-   <span data-ttu-id="e591c-108">на все приложения на стороне сервера, которые нельзя обновить для поддержки Tls1.0, Tls1.1 или Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="e591c-108">Any server-side app that cannot be upgraded to support Tls1.0, Tls1.1, or Tls 1.2..</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="e591c-109">Устранение рисков</span><span class="sxs-lookup"><span data-stu-id="e591c-109">Mitigation</span></span>  
 <span data-ttu-id="e591c-110">Рекомендуется обновить приложения на стороне сервера для использования Tls1.0, Tls1.1 или Tls 1.2.</span><span class="sxs-lookup"><span data-stu-id="e591c-110">The recommended mitigation is to upgrade the sever-side app to Tls1.0, Tls1.1, or Tls 1.2.</span></span> <span data-ttu-id="e591c-111">Если это невозможно, или если клиентские приложения не работают, можно использовать класс <xref:System.AppContext>, чтобы отказаться от этой функции одним из двух способов.</span><span class="sxs-lookup"><span data-stu-id="e591c-111">If this is not feasible, or if client apps are broken, the <xref:System.AppContext> class can be used to opt out of this feature in either of two ways:</span></span>  
  
-   <span data-ttu-id="e591c-112">Программно с помощью фрагмента кода следующего вида:</span><span class="sxs-lookup"><span data-stu-id="e591c-112">Programmatically, by using a code snippet like the following:</span></span>  
  
     [!code-csharp[AppCompat.SSLProtocols#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.sslprotocols/cs/program.cs#1)]
     [!code-vb[AppCompat.SSLProtocols#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.sslprotocols/vb/module1.vb#1)]  
  
     <span data-ttu-id="e591c-113">Поскольку объект <xref:System.Net.ServicePointManager> инициализируется только один раз, определение этих параметров совместимости должно быть первым действием приложения.</span><span class="sxs-lookup"><span data-stu-id="e591c-113">Because the <xref:System.Net.ServicePointManager> object is initialized only once, defining these compatibility settings must be the first thing the application does.</span></span>  
  
-   <span data-ttu-id="e591c-114">Путем добавления следующей строки в раздел [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) файла app.config:</span><span class="sxs-lookup"><span data-stu-id="e591c-114">By adding the following line to the [\<runtime>](../../../docs/framework/configure-apps/file-schema/runtime/runtime-element.md) section of your app.config file:</span></span>  
  
    ```xml  
    <AppContextSwitchOverrides value="Switch.System.Net.DontEnableSchUseStrongCrypto=true"/>  
    ```  
  
 <span data-ttu-id="e591c-115">Следует, тем не менее, заметить, что отказ от поведения по умолчанию не рекомендуется, поскольку приводит к снижению безопасности приложения.</span><span class="sxs-lookup"><span data-stu-id="e591c-115">Note, however, that opting out of the default behavior is not recommended, since it makes the application less secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e591c-116">См. также</span><span class="sxs-lookup"><span data-stu-id="e591c-116">See also</span></span>
- [<span data-ttu-id="e591c-117">Изменение целевой платформы</span><span class="sxs-lookup"><span data-stu-id="e591c-117">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
