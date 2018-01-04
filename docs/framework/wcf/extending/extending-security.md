---
title: "Расширение безопасности"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: security [WCF], extending
ms.assetid: a015a040-9fdf-4147-9ea9-f83b570be1d4
caps.latest.revision: "23"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: ecbbaac0023ca528967abe2cb60c3d790772fb2e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="extending-security"></a><span data-ttu-id="2592d-102">Расширение безопасности</span><span class="sxs-lookup"><span data-stu-id="2592d-102">Extending Security</span></span>
<span data-ttu-id="2592d-103">Для размещения новых типов утверждений и пользовательских маркеров можно расширить инфраструктуру безопасности [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2592d-103">To accommodate new claim types and custom tokens, you can extend the security infrastructure of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="2592d-104">Это подробно описывается в следующих подразделах.</span><span class="sxs-lookup"><span data-stu-id="2592d-104">The topics in this section show you how this is done.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2592d-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="2592d-105">In This Section</span></span>  
 [<span data-ttu-id="2592d-106">Архитектура безопасности</span><span class="sxs-lookup"><span data-stu-id="2592d-106">Security Architecture</span></span>](http://msdn.microsoft.com/en-us/16593476-d36a-408d-808c-ae6fd483e28f)  
 <span data-ttu-id="2592d-107">Пошаговое рассмотрение архитектуры системы безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2592d-107">Walks through the architecture of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security system.</span></span>  
  
 [<span data-ttu-id="2592d-108">Пользовательские учетные данные и проверка учетных данных</span><span class="sxs-lookup"><span data-stu-id="2592d-108">Custom Credential and Credential Validation</span></span>](../../../../docs/framework/wcf/extending/custom-credential-and-credential-validation.md)  
 <span data-ttu-id="2592d-109">Рассматривается, как модель удостоверения используется при проверке пользовательских учетных данных.</span><span class="sxs-lookup"><span data-stu-id="2592d-109">Explains how the Identity Model is used when validating custom credentials.</span></span>  
  
 [<span data-ttu-id="2592d-110">Пользовательские маркеры</span><span class="sxs-lookup"><span data-stu-id="2592d-110">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 <span data-ttu-id="2592d-111">Маркеры, выдаваемые службой маркеров безопасности (STS), - обычно маркеры SAML.</span><span class="sxs-lookup"><span data-stu-id="2592d-111">Issued tokens from a Security Token Service (STS) are typically SAML tokens.</span></span> <span data-ttu-id="2592d-112">В этом разделе описывается, как создать тип пользовательского маркера.</span><span class="sxs-lookup"><span data-stu-id="2592d-112">This topic explains how to create a custom token type.</span></span>  
  
 [<span data-ttu-id="2592d-113">Пользовательская авторизация</span><span class="sxs-lookup"><span data-stu-id="2592d-113">Custom Authorization</span></span>](../../../../docs/framework/wcf/extending/custom-authorization.md)  
 <span data-ttu-id="2592d-114">Объясняется, как реализовать пользовательскую авторизацию.</span><span class="sxs-lookup"><span data-stu-id="2592d-114">Explains how to implement custom authorization.</span></span>  
  
 [<span data-ttu-id="2592d-115">Переопределение идентификатора службы для проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="2592d-115">Overriding the Identity of a Service for Authentication</span></span>](../../../../docs/framework/wcf/extending/overriding-the-identity-of-a-service-for-authentication.md)  
 <span data-ttu-id="2592d-116">Описывается, как переопределить идентификацию службы для проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="2592d-116">Describes how to override the identity of a service for authentication.</span></span>  
  
 [<span data-ttu-id="2592d-117">Практическое руководство. Создание пользовательского средства проверки идентификации клиентов</span><span class="sxs-lookup"><span data-stu-id="2592d-117">How to: Create a Custom Client Identity Verifier</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-client-identity-verifier.md)  
 <span data-ttu-id="2592d-118">Демонстрирует, как проверить идентификацию пользовательской конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2592d-118">Demonstrates how to validate a custom endpoint identity.</span></span>  
  
 [<span data-ttu-id="2592d-119">Практическое руководство. Использование отдельных сертификатов X.509 для подписывания и шифрования</span><span class="sxs-lookup"><span data-stu-id="2592d-119">How to: Use Separate X.509 Certificates for Signing and Encryption</span></span>](../../../../docs/framework/wcf/extending/how-to-use-separate-x-509-certificates-for-signing-and-encryption.md)  
 <span data-ttu-id="2592d-120">Обычно сообщения подписываются и шифруются одним сертификатом.</span><span class="sxs-lookup"><span data-stu-id="2592d-120">Messages are typically signed and encrypted with a single certificate.</span></span> <span data-ttu-id="2592d-121">В этом разделе объясняется, как при необходимости использовать два сертификата.</span><span class="sxs-lookup"><span data-stu-id="2592d-121">This topic explains how two certificates can be used, when required.</span></span>  
  
 [<span data-ttu-id="2592d-122">Практическое руководство. Изменение поставщика служб шифрования для закрытого ключа сертификата X.509</span><span class="sxs-lookup"><span data-stu-id="2592d-122">How to: Change the Cryptographic Provider for an X.509 Certificate's Private Key</span></span>](../../../../docs/framework/wcf/extending/change-cryptographic-provider-x509-certificate-private-key.md)  
 <span data-ttu-id="2592d-123">Объясняется, как изменить поставщика служб шифрования, предоставлявшего закрытый ключ сертификата X.509, и как интегрировать поставщика в инфраструктуру [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2592d-123">Explains how to change the cryptographic provider used to provide an X.509 certificate's private key and how to integrate the provider into the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] framework.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="2592d-124">Ссылка</span><span class="sxs-lookup"><span data-stu-id="2592d-124">Reference</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Tokens>  
  
 <xref:System.IdentityModel.Selectors>  
  
## <a name="related-sections"></a><span data-ttu-id="2592d-125">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="2592d-125">Related Sections</span></span>  
 [<span data-ttu-id="2592d-126">Безопасность</span><span class="sxs-lookup"><span data-stu-id="2592d-126">Security</span></span>](../../../../docs/framework/wcf/feature-details/security.md)  
  
 [<span data-ttu-id="2592d-127">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="2592d-127">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
## <a name="see-also"></a><span data-ttu-id="2592d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="2592d-128">See Also</span></span>  
 [<span data-ttu-id="2592d-129">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="2592d-129">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
