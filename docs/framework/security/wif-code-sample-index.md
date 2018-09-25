---
title: Индекс образцов кода WIF
ms.date: 03/30/2017
ms.assetid: 6711f01a-4743-43ce-95ab-5e2302a363ea
author: BrucePerlerMS
ms.openlocfilehash: b4c73bac9ddda83d78a4d9c95e3864d8d4e8ec4e
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47070322"
---
# <a name="wif-code-sample-index"></a><span data-ttu-id="6f863-102">Индекс образцов кода WIF</span><span class="sxs-lookup"><span data-stu-id="6f863-102">WIF Code Sample Index</span></span>
<span data-ttu-id="6f863-103">Ниже приведены образцы кода для Windows Identity Foundation 4.5.</span><span class="sxs-lookup"><span data-stu-id="6f863-103">The following are code samples for Windows Identity Foundation 4.5:</span></span>  
  
-   <span data-ttu-id="6f863-104">[ClaimsAwareWebApp](https://go.microsoft.com/fwlink/?LinkID=248405) — этот образец демонстрирует основные принципы экспорта проверки подлинности (в локальную тестовую службу маркеров безопасности из средства Identity and Access Tool для Visual Studio 11) в классическом приложении ASP.NET (а не на веб-сайте).</span><span class="sxs-lookup"><span data-stu-id="6f863-104">[ClaimsAwareWebApp](https://go.microsoft.com/fwlink/?LinkID=248405) - this sample demonstrates basic use of authentication externalization (to the local test Security Token Service from the Identity and Access Tool for Visual Studio 11) on a classic ASP.NET application (as opposed to a web site).</span></span>  
  
-   <span data-ttu-id="6f863-105">[ClaimsAwareWebService](https://go.microsoft.com/fwlink/?LinkID=248406) — этот образец демонстрирует основные принципы экспорта проверки подлинности в классической службе WCF.</span><span class="sxs-lookup"><span data-stu-id="6f863-105">[ClaimsAwareWebService](https://go.microsoft.com/fwlink/?LinkID=248406) - this sample demonstrates basic use of authentication externalization on a classic WCF service.</span></span>  
  
-   <span data-ttu-id="6f863-106">[ClaimsAwareMvcApplication](https://go.microsoft.com/fwlink/?LinkID=248407) — в этом примере демонстрируется интеграция WIF с MVC, включая направленную защиту и код, в котором учитываются перенаправления проверки подлинности на основе форм из контроллера LogOn.</span><span class="sxs-lookup"><span data-stu-id="6f863-106">[ClaimsAwareMvcApplication](https://go.microsoft.com/fwlink/?LinkID=248407) - this sample demonstrates how to integrate WIF with MVC, including non-blanket protection and code which honors the forms authentication redirects out of the LogOn controller.</span></span>  
  
-   <span data-ttu-id="6f863-107">[ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408) — в этом примере демонстрируется готовый к применению в ферме кэш сеанса (вместо tokenreplycache), который позволяет использовать сеансы по ссылке, а не обмениваться большими файлами cookie.</span><span class="sxs-lookup"><span data-stu-id="6f863-107">[ClaimsAwareWebFarm](https://go.microsoft.com/fwlink/?LinkID=248408) - this sample demonstrates a farm ready session cache (as opposed to a tokenreplycache) so that you can use sessions by reference instead of exchanging big cookies.</span></span> <span data-ttu-id="6f863-108">Также показан более простой способ защиты файлов cookie в ферме.</span><span class="sxs-lookup"><span data-stu-id="6f863-108">It also demonstrates an easier way of securing cookies in a farm.</span></span>  
  
-   <span data-ttu-id="6f863-109">[ClaimsAwareFormsAuthentication](https://go.microsoft.com/fwlink/?LinkID=248409) — в этом очень простом примере показано, что в .NET 4.5 вы получаете утверждения в субъектах вне зависимости от способа проверки подлинности пользователей.</span><span class="sxs-lookup"><span data-stu-id="6f863-109">[ClaimsAwareFormsAuthentication](https://go.microsoft.com/fwlink/?LinkID=248409) - this very simple sample demonstrates that in .NET 4.5 you get claims in your principals regardless of how you authenticate your users.</span></span>  
  
-   <span data-ttu-id="6f863-110">[ClaimsBasedAuthorization](https://go.microsoft.com/fwlink/?LinkID=248410) — в этих примерах показано, как использовать класс CLaimsAuthorizationManager и модуль ClaimsAuthorizationModule для применения собственных политик авторизации.</span><span class="sxs-lookup"><span data-stu-id="6f863-110">[ClaimsBasedAuthorization](https://go.microsoft.com/fwlink/?LinkID=248410)- this samples shows how to use your CLaimsAuthorizationManager class and the ClaimsAuthorizationModule for applying your own authorization policies.</span></span>  
  
-   <span data-ttu-id="6f863-111">[FederationMetadata](https://go.microsoft.com/fwlink/?LinkID=248411) — в этом примере демонстрируются как динамическое создание (в пользовательской службе STS), так и динамическое потребление (в приложении проверяющей стороны) документов метаданных.</span><span class="sxs-lookup"><span data-stu-id="6f863-111">[FederationMetadata](https://go.microsoft.com/fwlink/?LinkID=248411) – this sample demonstrates both dynamic generation (on a custom STS) and dynamic consumption (on a relying party application) of metadata documents.</span></span>  
  
-   <span data-ttu-id="6f863-112">[CustomToken](https://go.microsoft.com/fwlink/?LinkID=248412) — этот образец демонстрирует создание пользовательского типа токена Simple Web Token (SWT).</span><span class="sxs-lookup"><span data-stu-id="6f863-112">[CustomToken](https://go.microsoft.com/fwlink/?LinkID=248412) – this sample demonstrates how to build a custom Simple Web Token (SWT) token type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f863-113">См. также</span><span class="sxs-lookup"><span data-stu-id="6f863-113">See Also</span></span>  
 [<span data-ttu-id="6f863-114">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="6f863-114">Windows Identity Foundation</span></span>](../../../docs/framework/security/index.md)
