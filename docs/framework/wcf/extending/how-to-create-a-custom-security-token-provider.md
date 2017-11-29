---
title: "Практическое руководство. Создание пользовательского поставщика маркеров безопасности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords: security [WCF], providing credentials
ms.assetid: db8cb478-aa43-478b-bf97-c6489ad7c7fd
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 0bf616b1af46c62166b0430c1b67b3a97f0613ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-security-token-provider"></a><span data-ttu-id="5dea8-102">Практическое руководство. Создание пользовательского поставщика маркеров безопасности</span><span class="sxs-lookup"><span data-stu-id="5dea8-102">How to: Create a Custom Security Token Provider</span></span>
<span data-ttu-id="5dea8-103">В этом разделе показано, как создавать новые типы маркеров с помощью поставщика пользовательских маркеров безопасности и как интегрировать поставщик с диспетчером пользовательских маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="5dea8-103">This topic shows how to create new token types with a custom security token provider and how to integrate the provider with a custom security token manager.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5dea8-104">Поставщик пользовательских маркеров следует создавать, если предоставляемые системой маркеры в пространстве имен <xref:System.IdentityModel.Tokens> не соответствуют требованиям.</span><span class="sxs-lookup"><span data-stu-id="5dea8-104">Create a custom token provider if the system-provided tokens found in the <xref:System.IdentityModel.Tokens> namespace do not match your requirements.</span></span>  
  
 <span data-ttu-id="5dea8-105">Поставщик маркеров безопасности создает представление маркера безопасности на основании сведений в учетных данных клиента или службы.</span><span class="sxs-lookup"><span data-stu-id="5dea8-105">The security token provider creates a security token representation based on information in the client or service credentials.</span></span> <span data-ttu-id="5dea8-106">Чтобы использовать пользовательский поставщик проверки подлинности в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], необходимо создать пользовательские реализации учетных данных и диспетчера маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="5dea8-106">To use the custom security token provider in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] security, you must create custom credentials and security token manager implementations.</span></span>  
  
 <span data-ttu-id="5dea8-107">Дополнительные сведения о пользовательских учетных данных и диспетчера маркеров безопасности. в разделе [Пошаговое руководство: Создание настраиваемых клиентских учетных данных и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="5dea8-107">For more information about custom credentials and security token manager see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
 <span data-ttu-id="5dea8-108">Дополнительные сведения об учетных данных безопасности маркера manager поставщика классов и проверки подлинности, в разделе [архитектуры безопасности](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f).</span><span class="sxs-lookup"><span data-stu-id="5dea8-108">For more information about credentials, security token manager, provider and authenticator classes, see the [Security Architecture](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f).</span></span>  
  
### <a name="to-create-a-custom-security-token-provider"></a><span data-ttu-id="5dea8-109">Создание поставщика пользовательских маркеров безопасности</span><span class="sxs-lookup"><span data-stu-id="5dea8-109">To create a custom security token provider</span></span>  
  
1.  <span data-ttu-id="5dea8-110">Определите новый класс, производный от класса <xref:System.IdentityModel.Selectors.SecurityTokenProvider>.</span><span class="sxs-lookup"><span data-stu-id="5dea8-110">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class.</span></span>  
  
2.  <span data-ttu-id="5dea8-111">Выполните метод <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>.</span><span class="sxs-lookup"><span data-stu-id="5dea8-111">Implement the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method.</span></span> <span data-ttu-id="5dea8-112">Этот метод отвечает за создание и возвращение экземпляра маркера безопасности.</span><span class="sxs-lookup"><span data-stu-id="5dea8-112">The method is responsible for creating and returning an instance of the security token.</span></span> <span data-ttu-id="5dea8-113">В следующем примере создается класс с именем `MySecurityTokenProvider` и переопределяется метод <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29>, чтобы он возвращал экземпляр класса <xref:System.IdentityModel.Tokens.X509SecurityToken>.</span><span class="sxs-lookup"><span data-stu-id="5dea8-113">The following example creates a class named `MySecurityTokenProvider`, and overrides the <xref:System.IdentityModel.Selectors.SecurityTokenProvider.GetTokenCore%28System.TimeSpan%29> method to return an instance of the <xref:System.IdentityModel.Tokens.X509SecurityToken> class.</span></span> <span data-ttu-id="5dea8-114">Конструктору класса требуется экземпляр класса <xref:System.Security.Cryptography.X509Certificates.X509Certificate2>.</span><span class="sxs-lookup"><span data-stu-id="5dea8-114">The class constructor requires an instance of the <xref:System.Security.Cryptography.X509Certificates.X509Certificate2> class.</span></span>  
  
     [!code-csharp[c_CustomTokenProvider#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#1)]
     [!code-vb[c_CustomTokenProvider#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#1)]  
  
### <a name="to-integrate-a-custom-security-token-provider-with-a-custom-security-token-manager"></a><span data-ttu-id="5dea8-115">Интеграция поставщика пользовательских маркеров безопасности с диспетчером пользовательских маркеров безопасности</span><span class="sxs-lookup"><span data-stu-id="5dea8-115">To integrate a custom security token provider with a custom security token manager</span></span>  
  
1.  <span data-ttu-id="5dea8-116">Определите новый класс, производный от класса <xref:System.IdentityModel.Selectors.SecurityTokenManager>.</span><span class="sxs-lookup"><span data-stu-id="5dea8-116">Define a new class derived from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.</span></span> <span data-ttu-id="5dea8-117">(В следующем примере кода создается класс <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager>, наследуемый от класса <xref:System.IdentityModel.Selectors.SecurityTokenManager>.)</span><span class="sxs-lookup"><span data-stu-id="5dea8-117">(The example below derives from the <xref:System.ServiceModel.ClientCredentialsSecurityTokenManager> class, which derives from the <xref:System.IdentityModel.Selectors.SecurityTokenManager> class.)</span></span>  
  
2.  <span data-ttu-id="5dea8-118">Переопределите метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29>, если он еще не переопределен.</span><span class="sxs-lookup"><span data-stu-id="5dea8-118">Override the <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method if is not already overridden.</span></span>  
  
     <span data-ttu-id="5dea8-119">Метод <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> отвечает за возврат экземпляра класса <xref:System.IdentityModel.Selectors.SecurityTokenProvider> в соответствии с параметром <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>, переданным методу средой безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5dea8-119">The <xref:System.IdentityModel.Selectors.SecurityTokenManager.CreateSecurityTokenProvider%28System.IdentityModel.Selectors.SecurityTokenRequirement%29> method is responsible for returning an instance of the <xref:System.IdentityModel.Selectors.SecurityTokenProvider> class appropriate to the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter passed to the method by the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security framework.</span></span> <span data-ttu-id="5dea8-120">Измените метод, чтобы он возвращал реализацию поставщика пользовательских маркеров безопасности (созданную перед этим), когда этот метод вызывается с соответствующим параметром маркера безопасности.</span><span class="sxs-lookup"><span data-stu-id="5dea8-120">Modify the method to return the custom security token provider implementation (created in the previous procedure) when the method is called with an appropriate security token parameter.</span></span> <span data-ttu-id="5dea8-121">Дополнительные сведения о диспетчере маркера безопасности. в разделе [Пошаговое руководство: Создание настраиваемых клиентских учетных данных и службы](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span><span class="sxs-lookup"><span data-stu-id="5dea8-121">For more information about the security token manager, see the [Walkthrough: Creating Custom Client and Service Credentials](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md).</span></span>  
  
3.  <span data-ttu-id="5dea8-122">Добавьте в метод соответствующие инструкции, чтобы он мог возвращать поставщик пользовательских маркеров безопасности на основании параметра <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>.</span><span class="sxs-lookup"><span data-stu-id="5dea8-122">Add custom logic to the method to enable it to return your custom security token provider based on the <xref:System.IdentityModel.Selectors.SecurityTokenRequirement> parameter.</span></span> <span data-ttu-id="5dea8-123">В следующем примере метод возвращает поставщик пользовательских маркеров безопасности, если выполняются требования маркера.</span><span class="sxs-lookup"><span data-stu-id="5dea8-123">The following sample returns the custom security token provider if the token requirements are met.</span></span> <span data-ttu-id="5dea8-124">Требования включают маркер безопасности X.509 и направление сообщения (маркер используется для вывода сообщений).</span><span class="sxs-lookup"><span data-stu-id="5dea8-124">The requirements include an X.509 security token and the message direction (that the token is used for message output).</span></span> <span data-ttu-id="5dea8-125">Во всех остальных случаях код вызывает базовый класс для поддержки предоставляемого системой поведения для требований других маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="5dea8-125">For all other cases, the code calls the base class to maintain the system-provided behavior for other security token requirements.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#2)]
 [!code-vb[c_CustomTokenProvider#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#2)]  
  
## <a name="example"></a><span data-ttu-id="5dea8-126">Пример</span><span class="sxs-lookup"><span data-stu-id="5dea8-126">Example</span></span>  
 <span data-ttu-id="5dea8-127">Ниже показана полная реализация поставщика <xref:System.IdentityModel.Selectors.SecurityTokenProvider>, а также соответствующая реализация диспетчера <xref:System.IdentityModel.Selectors.SecurityTokenManager>.</span><span class="sxs-lookup"><span data-stu-id="5dea8-127">The following shows a complete <xref:System.IdentityModel.Selectors.SecurityTokenProvider> implementation along with a corresponding <xref:System.IdentityModel.Selectors.SecurityTokenManager> implementation.</span></span>  
  
 [!code-csharp[c_CustomTokenProvider#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customtokenprovider/cs/source.cs#0)]
 [!code-vb[c_CustomTokenProvider#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customtokenprovider/vb/source.vb#0)]  
  
## <a name="see-also"></a><span data-ttu-id="5dea8-128">См. также</span><span class="sxs-lookup"><span data-stu-id="5dea8-128">See Also</span></span>  
 <xref:System.IdentityModel.Selectors.SecurityTokenProvider>  
 <xref:System.IdentityModel.Selectors.SecurityTokenRequirement>  
 <xref:System.IdentityModel.Selectors.SecurityTokenManager>  
 <xref:System.IdentityModel.Tokens.X509SecurityToken>  
 [<span data-ttu-id="5dea8-129">Пошаговое руководство: Создание пользовательского клиента и учетные данные службы</span><span class="sxs-lookup"><span data-stu-id="5dea8-129">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 [<span data-ttu-id="5dea8-130">Как: создать средство проверки подлинности маркеров безопасности</span><span class="sxs-lookup"><span data-stu-id="5dea8-130">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 [<span data-ttu-id="5dea8-131">Архитектура безопасности</span><span class="sxs-lookup"><span data-stu-id="5dea8-131">Security Architecture</span></span>](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)
