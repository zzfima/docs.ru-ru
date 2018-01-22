---
title: "Создание первой службы WCF на основе утверждений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e0e6d091-9a97-4888-8f2c-cbcee42d90ee
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 791c86b8f833c6b1a8acb6da3b03cfccdafca0e5
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/19/2018
---
# <a name="building-my-first-claims-aware-wcf-service"></a><span data-ttu-id="f4689-102">Создание первой службы WCF на основе утверждений</span><span class="sxs-lookup"><span data-stu-id="f4689-102">Building My First Claims-Aware WCF Service</span></span>
## <a name="applies-to"></a><span data-ttu-id="f4689-103">Применение</span><span class="sxs-lookup"><span data-stu-id="f4689-103">Applies To</span></span>  
  
-   <span data-ttu-id="f4689-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="f4689-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="f4689-105">Windows Communication Foundation (WCF)</span><span class="sxs-lookup"><span data-stu-id="f4689-105">Windows Communication Foundation (WCF)</span></span>  
  
## <a name="overview"></a><span data-ttu-id="f4689-106">Обзор</span><span class="sxs-lookup"><span data-stu-id="f4689-106">Overview</span></span>  
 <span data-ttu-id="f4689-107">В этом разделе представлен сценарий создания служб WCF, поддерживающих утверждения, при помощи WIF.</span><span class="sxs-lookup"><span data-stu-id="f4689-107">This topic outlines the scenario of building claims-aware WCF services using WIF.</span></span> <span data-ttu-id="f4689-108">Обычно существует три участника сценария для веб-службы, поддерживающей утверждения: сама веб-служба, пользователь и служба маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="f4689-108">There are usually three participants in a claims-aware web service scenario: the web service itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="f4689-109">Данный сценарий представлен на иллюстрации ниже:</span><span class="sxs-lookup"><span data-stu-id="f4689-109">The following figure describes this scenario:</span></span>  
  
 <span data-ttu-id="f4689-110">![Базовая служба WCF с поддержкой утверждений на основе WIF](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span><span class="sxs-lookup"><span data-stu-id="f4689-110">![WIF Basic Claims Aware WCF Service](../../../docs/framework/security/media/wifbasicclaimsawarewcfservice.gif "WIFBasicClaimsAwareWCFService")</span></span>  
  
1.  <span data-ttu-id="f4689-111">Клиент службы WCF (который иногда называют агентом) использует WIF для отправки учетных данных в службу STS. После успешной аутентификации служба STS создает токен для данного агента.</span><span class="sxs-lookup"><span data-stu-id="f4689-111">The WCF service client (sometimes called agent) uses WIF to send credentials to the STS and upon successful authentication, the agent is issued a token by the STS.</span></span>  
  
2.  <span data-ttu-id="f4689-112">Агент отправляет токен, созданный STS, в службу WCF.</span><span class="sxs-lookup"><span data-stu-id="f4689-112">The agent sends this STS-issued token to the WCF service.</span></span>  
  
3.  <span data-ttu-id="f4689-113">Служба WCF, поддерживающая утверждения, настроена на доверие к службе STS и ее токенам.</span><span class="sxs-lookup"><span data-stu-id="f4689-113">The claims-aware WCF service is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="f4689-114">Служба WCF, поддерживающая утверждения, использует WIF для проверки и анализа токена.</span><span class="sxs-lookup"><span data-stu-id="f4689-114">The claims-aware WCF service uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="f4689-115">Разработчики используют соответствующий API-интерфейс WIF и типы, например **ClaimsPrincipal**, для удовлетворения потребностей приложения (например, внедрения авторизации).</span><span class="sxs-lookup"><span data-stu-id="f4689-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincipal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="f4689-116">WIF входит в пакет .NET Framework, начиная с версии .NET 4.5.</span><span class="sxs-lookup"><span data-stu-id="f4689-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="f4689-117">Прямая доступность классов WIF на этой платформе обеспечивает гораздо более глубокую интеграцию удостоверения на базе утверждений с платформой .NET, благодаря которой использовать утверждения становится проще.</span><span class="sxs-lookup"><span data-stu-id="f4689-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="f4689-118">Если используется WIF 4.5, то для того, чтобы приступить к разработке веб-приложений, поддерживающих утверждения, не требуется устанавливать никакие дополнительные компоненты.</span><span class="sxs-lookup"><span data-stu-id="f4689-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="f4689-119">Классы WIF теперь распространяются на различные сборки, например System.Security.Claims, System.IdentityModel и System.IdentityModel.Services.</span><span class="sxs-lookup"><span data-stu-id="f4689-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="f4689-120">STS — это служба, использующая токены после успешной аутентификации.</span><span class="sxs-lookup"><span data-stu-id="f4689-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="f4689-121">Microsoft предлагает две службы STS, соответствующие отраслевым стандартам:</span><span class="sxs-lookup"><span data-stu-id="f4689-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   <span data-ttu-id="f4689-122">[Службы федерации Active Directory (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span><span class="sxs-lookup"><span data-stu-id="f4689-122">[Active Directory Federation Services (AD FS) 2.0](http://go.microsoft.com/fwlink/?LinkID=247516) (http://go.microsoft.com/fwlink/?LinkID=247516)</span></span>  
  
-   <span data-ttu-id="f4689-123">[Служба управления доступом Windows Azure (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span><span class="sxs-lookup"><span data-stu-id="f4689-123">[Windows Azure Access Control Service (ACS)](http://go.microsoft.com/fwlink/?LinkID=247517) (http://go.microsoft.com/fwlink/?LinkID=247517).</span></span>  
  
 <span data-ttu-id="f4689-124">AD FS 2.0 является компонентом решения Windows Server R2 и может использоваться в качестве службы STS для локальных сценариев.</span><span class="sxs-lookup"><span data-stu-id="f4689-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="f4689-125">Контроль доступа Azure Active Directory (также называемый службой контроля доступа или ACS) — это облачная служба, входящая в состав Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="f4689-125">Azure Active Directory Access Control (also known as Access Control Service or ACS) is a cloud service, offered as part of Microsoft Azure.</span></span> <span data-ttu-id="f4689-126">Для тестирования или обучения можно также использовать другие службы STS, создавая с их помощью приложения, поддерживающие утверждения.</span><span class="sxs-lookup"><span data-stu-id="f4689-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="f4689-127">Например, можно использовать службу STS локальной разработки, входящую в средство [Identity and Access Tool для Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849), которое можно бесплатно загрузить из Интернета.</span><span class="sxs-lookup"><span data-stu-id="f4689-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](http://go.microsoft.com/fwlink/?LinkID=245849) (http://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="f4689-128">Инструкции по сборке первой службы WCF, поддерживающей утверждения с помощью WIF, см. в разделе [Практическое руководство. Сборка службы WCF, поддерживающей утверждения с помощью WIF](http://msdn.microsoft.com/library/431e6415-62ed-4a9f-af03-f14d2b4dfe6d).</span><span class="sxs-lookup"><span data-stu-id="f4689-128">To build your first claims-aware WCF service using WIF, see [How To: Build Claims-Aware WCF Service Using WIF](http://msdn.microsoft.com/library/431e6415-62ed-4a9f-af03-f14d2b4dfe6d).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4689-129">См. также</span><span class="sxs-lookup"><span data-stu-id="f4689-129">See Also</span></span>  
 [<span data-ttu-id="f4689-130">Приступая к работе с WIF</span><span class="sxs-lookup"><span data-stu-id="f4689-130">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
