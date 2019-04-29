---
title: Пользовательские учетные данные и проверка учетных данных
ms.date: 03/30/2017
helpviewer_keywords:
- credentials [WCF], custom
- credentials [WCF]
- custom credentials [WCF]
- credential validation [WCF]
- credentials [WCF], validation
ms.assetid: da831bec-e281-4d44-b343-437b5eef688e
ms.openlocfilehash: 3b1ff700010f471a4d9be117f363083b6cbed493
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61696448"
---
# <a name="custom-credential-and-credential-validation"></a><span data-ttu-id="1c58d-102">Пользовательские учетные данные и проверка учетных данных</span><span class="sxs-lookup"><span data-stu-id="1c58d-102">Custom Credential and Credential Validation</span></span>
<span data-ttu-id="1c58d-103">Безопасность в Windows Communication Foundation (WCF) основана на обменом учетными данными между службами и клиентами.</span><span class="sxs-lookup"><span data-stu-id="1c58d-103">Security in Windows Communication Foundation (WCF) is based on the exchange of credentials between services and clients.</span></span> <span data-ttu-id="1c58d-104">Большинство сценариев обеспечения безопасности можно реализовать с использованием стандартных типов учетных данных, например Windows (Kerberos), имен пользователей и паролей, а также сертификатов.</span><span class="sxs-lookup"><span data-stu-id="1c58d-104">Most security scenarios can be satisfied using common credential types, such as Windows (Kerberos), username and passwords, and certificates.</span></span> <span data-ttu-id="1c58d-105">Если требуются учетные данные новых типов, в приведенных ниже разделах можно найти сведения о том, как обрабатывать и проверять эти типы.</span><span class="sxs-lookup"><span data-stu-id="1c58d-105">However, if a new type of credential is required, the topics in this section explain how to handle and validate new types.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c58d-106">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="1c58d-106">In This Section</span></span>  
 [<span data-ttu-id="1c58d-107">Практическое руководство. Создание службы, использующей пользовательское средство проверки сертификатов</span><span class="sxs-lookup"><span data-stu-id="1c58d-107">How to: Create a Service that Employs a Custom Certificate Validator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-service-that-employs-a-custom-certificate-validator.md)  
 <span data-ttu-id="1c58d-108">Объясняется, как настроить проверку WCF путем наследования от <xref:System.IdentityModel.Selectors.X509CertificateValidator> класса.</span><span class="sxs-lookup"><span data-stu-id="1c58d-108">Explains how to customize WCF validation by inheriting from the <xref:System.IdentityModel.Selectors.X509CertificateValidator> class.</span></span>  
  
 [<span data-ttu-id="1c58d-109">Пошаговое руководство: Создание пользовательских клиента и учетные данные службы</span><span class="sxs-lookup"><span data-stu-id="1c58d-109">Walkthrough: Creating Custom Client and Service Credentials</span></span>](../../../../docs/framework/wcf/extending/walkthrough-creating-custom-client-and-service-credentials.md)  
 <span data-ttu-id="1c58d-110">Демонстрирует расширение <xref:System.ServiceModel.Description.ClientCredentials> и <xref:System.ServiceModel.Description.ServiceCredentials> классы для работы с новыми типы учетных данных.</span><span class="sxs-lookup"><span data-stu-id="1c58d-110">Demonstrates how to extend the <xref:System.ServiceModel.Description.ClientCredentials> and <xref:System.ServiceModel.Description.ServiceCredentials> classes to accommodate new credential types.</span></span> <span data-ttu-id="1c58d-111">Это первый раздел в серии, посвященной созданию пользовательских типов учетных данных.</span><span class="sxs-lookup"><span data-stu-id="1c58d-111">This is first in a series of topics that enable creation of custom credential types.</span></span>  
  
 [<span data-ttu-id="1c58d-112">Практическое руководство. Создание поставщика маркеров безопасности</span><span class="sxs-lookup"><span data-stu-id="1c58d-112">How to: Create a Custom Security Token Provider</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-provider.md)  
 <span data-ttu-id="1c58d-113">Создание поставщика маркеров безопасности для обработки новых типов учетных данных и возврата новых маркеров для учетных данных.</span><span class="sxs-lookup"><span data-stu-id="1c58d-113">Explains how to create a security token provider to handle new credential types and return new tokens for the credential.</span></span> <span data-ttu-id="1c58d-114">Это второй раздел в данной серии.</span><span class="sxs-lookup"><span data-stu-id="1c58d-114">This is the second topic in the series.</span></span>  
  
 [<span data-ttu-id="1c58d-115">Практическое руководство. Создать структуру проверки подлинности маркеров безопасности</span><span class="sxs-lookup"><span data-stu-id="1c58d-115">How to: Create a Custom Security Token Authenticator</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-security-token-authenticator.md)  
 <span data-ttu-id="1c58d-116">Создание пользовательских структур проверки подлинности для проверки подлинности учетных данных новых типов.</span><span class="sxs-lookup"><span data-stu-id="1c58d-116">Explains how to create a custom authenticator to authenticate a new credential type.</span></span> <span data-ttu-id="1c58d-117">Это третий раздел в данной серии.</span><span class="sxs-lookup"><span data-stu-id="1c58d-117">This is the third topic in the series.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="1c58d-118">Ссылка</span><span class="sxs-lookup"><span data-stu-id="1c58d-118">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Selectors.X509CertificateValidator>  
  
 <xref:System.ServiceModel.Description.ClientCredentials>  
  
 <xref:System.ServiceModel.Description.ServiceCredentials>  
  
## <a name="related-sections"></a><span data-ttu-id="1c58d-119">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="1c58d-119">Related Sections</span></span>  
 [<span data-ttu-id="1c58d-120">Authentication</span><span class="sxs-lookup"><span data-stu-id="1c58d-120">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
 [<span data-ttu-id="1c58d-121">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="1c58d-121">Federation and Issued Tokens</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
  
 [<span data-ttu-id="1c58d-122">Авторизация</span><span class="sxs-lookup"><span data-stu-id="1c58d-122">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="1c58d-123">См. также</span><span class="sxs-lookup"><span data-stu-id="1c58d-123">See also</span></span>

- [<span data-ttu-id="1c58d-124">Безопасность</span><span class="sxs-lookup"><span data-stu-id="1c58d-124">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)
