---
title: "Федерация и выданные маркеры"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF, federation
- issued tokens [WCF]
- federation [WCF], issued tokens
ms.assetid: 4c31ee7d-a820-4067-8b84-a83049021bb6
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 017d3e51022ad9980dc8f058415697c80a2a6b35
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="ff718-102">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="ff718-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="ff718-103">С помощью [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно создавать клиенты, обеспечивающие безопасный обмен данными со службами, реализующими спецификации WS-Federation и WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="ff718-103">With [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="ff718-104">В этих спецификациях XML, протокол SOAP и язык WSDL используются для предоставления механизмов, позволяющих производить проверку подлинности и авторизацию в различных областях доверия.</span><span class="sxs-lookup"><span data-stu-id="ff718-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ff718-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="ff718-105">In This Section</span></span>  
 [<span data-ttu-id="ff718-106">Федерация</span><span class="sxs-lookup"><span data-stu-id="ff718-106">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 <span data-ttu-id="ff718-107">Общие сведения о федерации.</span><span class="sxs-lookup"><span data-stu-id="ff718-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="ff718-108">Федерация и доверие</span><span class="sxs-lookup"><span data-stu-id="ff718-108">Federation and Trust</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 <span data-ttu-id="ff718-109">Список вопросов архитектуры, о которых необходимо помнить при создании федеративных служб или клиентов.</span><span class="sxs-lookup"><span data-stu-id="ff718-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="ff718-110">Практическое руководство. Создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="ff718-110">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 <span data-ttu-id="ff718-111">Основы создания федеративного клиента с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="ff718-111">Describes the basics of creating a federated client with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="ff718-112">Практическое руководство. Настройка учетных данных службы федерации</span><span class="sxs-lookup"><span data-stu-id="ff718-112">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="ff718-113">Основные этапы создания федеративной службы.</span><span class="sxs-lookup"><span data-stu-id="ff718-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="ff718-114">Практическое руководство. Создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ff718-114">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="ff718-115">Порядок настройки клиентов и служб, использующих `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="ff718-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="ff718-116">Практическое руководство. Создание службы маркеров безопасности</span><span class="sxs-lookup"><span data-stu-id="ff718-116">How to: Create a Security Token Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 <span data-ttu-id="ff718-117">Этапы создания службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="ff718-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="ff718-118">Утверждения и маркеры языка SAML (Security Assertions Markup Language)</span><span class="sxs-lookup"><span data-stu-id="ff718-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 <span data-ttu-id="ff718-119">Маркеры языка Security Assertions Markup Language (SAML), допускающие расширение и позволяющие создавать типы утверждений с широкими функциональными возможностями.</span><span class="sxs-lookup"><span data-stu-id="ff718-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="ff718-120">Практическое руководство. Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="ff718-120">How to: Configure a Local Issuer</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="ff718-121">Порядок создания локального издателя маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="ff718-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="ff718-122">Практическое руководство. Порядок отключения безопасных сеансов в WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="ff718-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="ff718-123">Порядок отключения безопасных сеансов в `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="ff718-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="ff718-124">Отключение безопасных сеансов необходимо при создании веб-фермы, требующей сеансы для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="ff718-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ff718-125">Ссылка</span><span class="sxs-lookup"><span data-stu-id="ff718-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="ff718-126">См. также</span><span class="sxs-lookup"><span data-stu-id="ff718-126">See Also</span></span>  
 [<span data-ttu-id="ff718-127">Авторизация</span><span class="sxs-lookup"><span data-stu-id="ff718-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="ff718-128">Пользовательские маркеры</span><span class="sxs-lookup"><span data-stu-id="ff718-128">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 [<span data-ttu-id="ff718-129">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="ff718-129">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
