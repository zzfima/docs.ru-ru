---
title: Создание первого веб-приложения ASP.NET с поддержкой утверждений
ms.date: 03/30/2017
ms.assetid: 3ee8ee7f-caba-4267-9343-e313fae2876d
author: BrucePerlerMS
ms.openlocfilehash: 5a24a2117a031bfe49d0c27dbcefae6db00e6045
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59314559"
---
# <a name="building-my-first-claims-aware-aspnet-web-application"></a><span data-ttu-id="7bc46-102">Создание первого веб-приложения ASP.NET с поддержкой утверждений</span><span class="sxs-lookup"><span data-stu-id="7bc46-102">Building My First Claims-Aware ASP.NET Web Application</span></span>
## <a name="applies-to"></a><span data-ttu-id="7bc46-103">Применение</span><span class="sxs-lookup"><span data-stu-id="7bc46-103">Applies To</span></span>  
  
-   <span data-ttu-id="7bc46-104">Windows Identity Foundation (WIF)</span><span class="sxs-lookup"><span data-stu-id="7bc46-104">Windows Identity Foundation (WIF)</span></span>  
  
-   <span data-ttu-id="7bc46-105">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="7bc46-105">ASP.NET</span></span>  
  
 <span data-ttu-id="7bc46-106">В этом разделе представлен сценарий создания веб-приложений ASP.NET с учетом утверждений при помощи WIF.</span><span class="sxs-lookup"><span data-stu-id="7bc46-106">This topic outlines the scenario of building claims-aware ASP.NET web applications using WIF.</span></span> <span data-ttu-id="7bc46-107">Обычно существует три участника сценария для приложения с учетом утверждений: само приложение, пользователь и служба маркеров безопасности (STS).</span><span class="sxs-lookup"><span data-stu-id="7bc46-107">There are usually three participants in a claims-aware application scenario: the application itself, the end user, and the Security Token Service (STS).</span></span> <span data-ttu-id="7bc46-108">Данный сценарий представлен на иллюстрации ниже:</span><span class="sxs-lookup"><span data-stu-id="7bc46-108">The following figure describes this scenario:</span></span>  
  
 ![Схема, показывающая компоненты WIF базовое веб-приложение.](./media/building-my-first-claims-aware-aspnet-web-app/windows-identity-foundation-basic-web-application.gif)  
  
1. <span data-ttu-id="7bc46-110">Приложение, поддерживающее утверждения, использует WIF для идентификации запросов, не прошедших аутентификацию, и для перенаправления этих запросов в STS.</span><span class="sxs-lookup"><span data-stu-id="7bc46-110">The claims-aware application uses WIF to identify unauthenticated requests and to redirect them to the STS.</span></span>  
  
2. <span data-ttu-id="7bc46-111">Конечный пользователь предоставляет учетные данные в STS, и после успешной аутентификации STS назначает токен данному пользователю.</span><span class="sxs-lookup"><span data-stu-id="7bc46-111">The end user provides credentials to the STS and upon successful authentication the user is issued a token by the STS.</span></span>  
  
3. <span data-ttu-id="7bc46-112">Из STS пользователь перенаправляется в приложение, поддерживающее утверждения, с определенным STS токеном в запросе.</span><span class="sxs-lookup"><span data-stu-id="7bc46-112">The user is redirected from the STS to the claims-aware application with the STS-issued token in the request.</span></span>  
  
4. <span data-ttu-id="7bc46-113">Приложение, поддерживающее утверждения, настроено на доверие к службе STS и ее токенам.</span><span class="sxs-lookup"><span data-stu-id="7bc46-113">The claims-aware application is configured to trust the STS and the tokens it issues.</span></span> <span data-ttu-id="7bc46-114">Приложение, поддерживающее утверждения, использует WIF для проверки и анализа токена.</span><span class="sxs-lookup"><span data-stu-id="7bc46-114">The claims-aware application uses WIF to validate the token and to parse it.</span></span> <span data-ttu-id="7bc46-115">Разработчики используют соответствующий API-интерфейс WIF и типы, например **ClaimsPrincpal**, для удовлетворения потребностей приложения (например, внедрения авторизации).</span><span class="sxs-lookup"><span data-stu-id="7bc46-115">Developers use the appropriate WIF API and types, for example, **ClaimsPrincpal** for the application’s needs, such as implementing authorization for it.</span></span>  
  
 <span data-ttu-id="7bc46-116">WIF входит в пакет .NET Framework, начиная с версии .NET 4.5.</span><span class="sxs-lookup"><span data-stu-id="7bc46-116">Starting from .NET 4.5, WIF is part of the .NET Framework package.</span></span> <span data-ttu-id="7bc46-117">Прямая доступность классов WIF на этой платформе обеспечивает гораздо более глубокую интеграцию удостоверения на базе утверждений с платформой .NET, благодаря которой использовать утверждения становится проще.</span><span class="sxs-lookup"><span data-stu-id="7bc46-117">Having the WIF classes directly available in the framework allows a much deeper integration of claims-based identity in .NET, making it easier to use claims.</span></span> <span data-ttu-id="7bc46-118">Если используется WIF 4.5, то для того, чтобы приступить к разработке веб-приложений, поддерживающих утверждения, не требуется устанавливать никакие дополнительные компоненты.</span><span class="sxs-lookup"><span data-stu-id="7bc46-118">With WIF 4.5, you do not need to install any out-of-band components in order to start developing claims-aware web applications.</span></span> <span data-ttu-id="7bc46-119">Классы WIF теперь распространяются на различные сборки, например System.Security.Claims, System.IdentityModel и System.IdentityModel.Services.</span><span class="sxs-lookup"><span data-stu-id="7bc46-119">WIF classes are now spread across various assemblies, the main ones being System.Security.Claims, System.IdentityModel and System.IdentityModel.Services.</span></span>  
  
 <span data-ttu-id="7bc46-120">STS — это служба, использующая токены после успешной аутентификации.</span><span class="sxs-lookup"><span data-stu-id="7bc46-120">STS is a service that issues tokens upon successful authentication.</span></span> <span data-ttu-id="7bc46-121">Microsoft предлагает две службы STS, соответствующие отраслевым стандартам:</span><span class="sxs-lookup"><span data-stu-id="7bc46-121">Microsoft offers two industry standard STS’s:</span></span>  
  
-   [<span data-ttu-id="7bc46-122">Службы федерации Active Directory (AD FS) 2.0</span><span class="sxs-lookup"><span data-stu-id="7bc46-122">Active Directory Federation Services (AD FS) 2.0</span></span>](https://go.microsoft.com/fwlink/?LinkID=247516)
  
-   [<span data-ttu-id="7bc46-123">Windows Azure Access Control Service (ACS)</span><span class="sxs-lookup"><span data-stu-id="7bc46-123">Windows Azure Access Control Service (ACS)</span></span>](https://go.microsoft.com/fwlink/?LinkID=247517)
  
 <span data-ttu-id="7bc46-124">AD FS 2.0 является компонентом решения Windows Server R2 и может использоваться в качестве службы STS для локальных сценариев.</span><span class="sxs-lookup"><span data-stu-id="7bc46-124">AD FS 2.0 is part of the Windows Server R2 and can be used as an STS for on-premise scenarios.</span></span> <span data-ttu-id="7bc46-125">ACS — это облачная служба, предлагаемая в составе платформы Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="7bc46-125">ACS is a cloud service, offered as part of the Windows Azure Platform.</span></span> <span data-ttu-id="7bc46-126">Для тестирования или обучения можно также использовать другие службы STS, создавая с их помощью приложения, поддерживающие утверждения.</span><span class="sxs-lookup"><span data-stu-id="7bc46-126">For testing or educational purposes, you can also use other STS’s in order to build your claims-aware applications.</span></span> <span data-ttu-id="7bc46-127">Например, можно использовать STS локальной разработки, который является частью [Identity and Access Tool для Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) которая доступна через Интернет.</span><span class="sxs-lookup"><span data-stu-id="7bc46-127">For example, you can use the Local Development STS that is part of the [Identity and Access Tool for Visual Studio](https://go.microsoft.com/fwlink/?LinkID=245849) which is freely available online.</span></span>  
  
 <span data-ttu-id="7bc46-128">Чтобы создать первое приложение ASP.NET, поддерживающее утверждения, с помощью WIF, выполните инструкции, представленные в одном из нижеперечисленных разделов:</span><span class="sxs-lookup"><span data-stu-id="7bc46-128">To build your first claims-aware ASP.NET application using WIF, follow the instructions in one of the following:</span></span>  
  
-   [<span data-ttu-id="7bc46-129">Как выполнить: создание веб-приложения ASP.NET MVC, поддерживающего утверждения, с использованием WIF</span><span class="sxs-lookup"><span data-stu-id="7bc46-129">How To: Build Claims-Aware ASP.NET MVC Web Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-mvc-web-app-using-wif.md)  
  
-   [<span data-ttu-id="7bc46-130">Как выполнить: создание приложения ASP.NET Web Forms, поддерживающего утверждения, с использованием WIF</span><span class="sxs-lookup"><span data-stu-id="7bc46-130">How To: Build Claims-Aware ASP.NET Web Forms Application Using WIF</span></span>](../../../docs/framework/security/how-to-build-claims-aware-aspnet-web-forms-app-using-wif.md)  
  
-   [<span data-ttu-id="7bc46-131">Как выполнить: создание приложения ASP.NET, поддерживающего утверждения, с использованием аутентификации на основе форм</span><span class="sxs-lookup"><span data-stu-id="7bc46-131">How To: Build Claims-Aware ASP.NET Application Using Forms-Based Authentication</span></span>](../../../docs/framework/security/claims-aware-aspnet-app-forms-authentication.md)  
  
## <a name="see-also"></a><span data-ttu-id="7bc46-132">См. также</span><span class="sxs-lookup"><span data-stu-id="7bc46-132">See also</span></span>

- [<span data-ttu-id="7bc46-133">Приступая к работе с WIF</span><span class="sxs-lookup"><span data-stu-id="7bc46-133">Getting Started With WIF</span></span>](../../../docs/framework/security/getting-started-with-wif.md)
