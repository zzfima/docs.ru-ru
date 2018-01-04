---
title: "Пользовательские учетные данные и проверка учетных данных"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bdfd50253c71bfc9edd737964e771546cb797b9e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="27528-102">Пользовательские учетные данные и проверка учетных данных</span><span class="sxs-lookup"><span data-stu-id="27528-102">Custom Credential and Credential Validation</span></span>
<span data-ttu-id="27528-103">В основе обеспечения безопасности в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] лежит обмен учетными данными между службами и клиентами.</span><span class="sxs-lookup"><span data-stu-id="27528-103">Security in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="27528-104">Большинство сценариев обеспечения безопасности можно реализовать с использованием стандартных типов учетных данных, например Windows (Kerberos), имен пользователей и паролей, а также сертификатов.</span><span class="sxs-lookup"><span data-stu-id="27528-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="27528-105">Если требуются учетные данные новых типов, в приведенных ниже разделах можно найти сведения о том, как обрабатывать и проверять эти типы.</span><span class="sxs-lookup"><span data-stu-id="27528-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="27528-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="27528-106">In This Section</span></span>  
 [<span data-ttu-id="27528-107">Практическое руководство. Создание службы, использующей пользовательский проверяющий элемент управления для сертификатов</span><span class="sxs-lookup"><span data-stu-id="27528-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="27528-108">Настройка проверки [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] путем наследования от класса <xref:System.IdentityModel.Selectors.X509CertificateValidator>.</span><span class="sxs-lookup"><span data-stu-id="27528-108">Explains how to customize [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="27528-109">Пошаговое руководство. Создание пользовательских учетных данных для клиента и службы</span><span class="sxs-lookup"><span data-stu-id="27528-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="27528-110">Демонстрирует расширение <xref:System.ServiceModel.Description.ClientCredentials> и <xref:System.ServiceModel.Description.ServiceCredentials> классы для работы с новыми типами учетных данных.</span><span class="sxs-lookup"><span data-stu-id="27528-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="27528-111">Это первый раздел в серии, посвященной созданию пользовательских типов учетных данных.</span><span class="sxs-lookup"><span data-stu-id="27528-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="27528-112">Практическое руководство. Создание пользовательского поставщика маркеров безопасности</span><span class="sxs-lookup"><span data-stu-id="27528-112">How to: Create a Custom Security Token Provider</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="27528-113">Создание поставщика маркеров безопасности для обработки новых типов учетных данных и возврата новых маркеров для учетных данных.</span><span class="sxs-lookup"><span data-stu-id="27528-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="27528-114">Это второй раздел в данной серии.</span><span class="sxs-lookup"><span data-stu-id="27528-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="27528-115">Практическое руководство. Создание пользовательской структуры проверки подлинности маркера безопасности</span><span class="sxs-lookup"><span data-stu-id="27528-115">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="27528-116">Создание пользовательских структур проверки подлинности для проверки подлинности учетных данных новых типов.</span><span class="sxs-lookup"><span data-stu-id="27528-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="27528-117">Это третий раздел в данной серии.</span><span class="sxs-lookup"><span data-stu-id="27528-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="27528-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="27528-118">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="27528-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="27528-119">Related Sections</span></span>  
 [<span data-ttu-id="27528-120">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="27528-120">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="27528-121">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="27528-121">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="27528-122">Авторизация</span><span class="sxs-lookup"><span data-stu-id="27528-122">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="27528-123">См. также</span><span class="sxs-lookup"><span data-stu-id="27528-123">See Also</span></span>  
 [<span data-ttu-id="27528-124">Безопасность</span><span class="sxs-lookup"><span data-stu-id="27528-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
