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
ms.openlocfilehash: 05a110318bbe92f18d0bc6becb453a5d7851821c
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="federation-and-issued-tokens"></a><span data-ttu-id="936e6-102">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="936e6-102">Federation and Issued Tokens</span></span>
<span data-ttu-id="936e6-103">С помощью [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] можно создавать клиенты, обеспечивающие безопасный обмен данными со службами, реализующими спецификации WS-Federation и WS-Trust.</span><span class="sxs-lookup"><span data-stu-id="936e6-103">With [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], you can create clients that communicate securely with services that implement the WS-Federation and WS-Trust specifications.</span></span> <span data-ttu-id="936e6-104">В этих спецификациях XML, протокол SOAP и язык WSDL используются для предоставления механизмов, позволяющих производить проверку подлинности и авторизацию в различных областях доверия.</span><span class="sxs-lookup"><span data-stu-id="936e6-104">The specifications use XML, SOAP, and Web Services Description Language (WSDL) to provide mechanisms that enable authentication and authorization across different trust realms.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="936e6-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="936e6-105">In This Section</span></span>  
 [<span data-ttu-id="936e6-106">Федерации</span><span class="sxs-lookup"><span data-stu-id="936e6-106">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 <span data-ttu-id="936e6-107">Общие сведения о федерации.</span><span class="sxs-lookup"><span data-stu-id="936e6-107">Provides an overview of federation.</span></span>  
  
 [<span data-ttu-id="936e6-108">Федерация и доверие</span><span class="sxs-lookup"><span data-stu-id="936e6-108">Federation and Trust</span></span>](../../../../docs/framework/wcf/feature-details/federation-and-trust.md)  
 <span data-ttu-id="936e6-109">Список вопросов архитектуры, о которых необходимо помнить при создании федеративных служб или клиентов.</span><span class="sxs-lookup"><span data-stu-id="936e6-109">Lists the design issues to be aware of when creating federated services or clients.</span></span>  
  
 [<span data-ttu-id="936e6-110">Как: создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="936e6-110">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 <span data-ttu-id="936e6-111">Основы создания федеративного клиента с помощью [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="936e6-111">Describes the basics of creating a federated client with [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="936e6-112">Как: настройте учетные данные для службы федерации</span><span class="sxs-lookup"><span data-stu-id="936e6-112">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 <span data-ttu-id="936e6-113">Основные этапы создания федеративной службы.</span><span class="sxs-lookup"><span data-stu-id="936e6-113">Describes the steps of creating a federated service.</span></span>  
  
 [<span data-ttu-id="936e6-114">Как: создание WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="936e6-114">How to: Create a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="936e6-115">Порядок настройки клиентов и служб, использующих `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="936e6-115">Describes how to configure clients and services that use the `WSFederationHttpBinding`.</span></span>  
  
 [<span data-ttu-id="936e6-116">Как: создание службы маркеров безопасности</span><span class="sxs-lookup"><span data-stu-id="936e6-116">How to: Create a Security Token Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-token-service.md)  
 <span data-ttu-id="936e6-117">Этапы создания службы маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="936e6-117">Describes the steps of creating a security token service.</span></span>  
  
 [<span data-ttu-id="936e6-118">Утверждения Markup Language (SAML) токены безопасности и утверждений</span><span class="sxs-lookup"><span data-stu-id="936e6-118">Security Assertions Markup Language (SAML) Tokens and Claims</span></span>](../../../../docs/framework/wcf/feature-details/saml-tokens-and-claims.md)  
 <span data-ttu-id="936e6-119">Маркеры языка Security Assertions Markup Language (SAML), допускающие расширение и позволяющие создавать типы утверждений с широкими функциональными возможностями.</span><span class="sxs-lookup"><span data-stu-id="936e6-119">Describes Security Assertions Markup Language (SAML) tokens, which are extensible and enable you to create rich claim types.</span></span>  
  
 [<span data-ttu-id="936e6-120">Как: Настройка локального издателя</span><span class="sxs-lookup"><span data-stu-id="936e6-120">How to: Configure a Local Issuer</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-a-local-issuer.md)  
 <span data-ttu-id="936e6-121">Порядок создания локального издателя маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="936e6-121">Describes how to create a local issuer of security tokens.</span></span>  
  
 [<span data-ttu-id="936e6-122">Как: отключения безопасных сеансов в WSFederationHttpBinding</span><span class="sxs-lookup"><span data-stu-id="936e6-122">How to: Disable Secure Sessions on a WSFederationHttpBinding</span></span>](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 <span data-ttu-id="936e6-123">Порядок отключения безопасных сеансов в `WSFederationHttpBinding`.</span><span class="sxs-lookup"><span data-stu-id="936e6-123">Describes how to disable secure sessions on a `WSFederationHttpBinding`.</span></span> <span data-ttu-id="936e6-124">Отключение безопасных сеансов необходимо при создании веб-фермы, требующей сеансы для каждого клиента.</span><span class="sxs-lookup"><span data-stu-id="936e6-124">Disabling secure sessions is necessary when creating a Web farm that requires a session for each client.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="936e6-125">Ссылка</span><span class="sxs-lookup"><span data-stu-id="936e6-125">Reference</span></span>  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
  
 <xref:System.IdentityModel.Tokens.SamlSecurityToken>  
  
 <xref:System.ServiceModel.Security.IssuedTokenClientCredential>  
  
 <xref:System.ServiceModel.Security.IssuedTokenServiceCredential>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters>  
  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenProvider>  
  
 <xref:System.ServiceModel.WSFederationHttpBinding>  
  
## <a name="see-also"></a><span data-ttu-id="936e6-126">См. также</span><span class="sxs-lookup"><span data-stu-id="936e6-126">See Also</span></span>  
 [<span data-ttu-id="936e6-127">Авторизация</span><span class="sxs-lookup"><span data-stu-id="936e6-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
 [<span data-ttu-id="936e6-128">Пользовательские маркеры</span><span class="sxs-lookup"><span data-stu-id="936e6-128">Custom Tokens</span></span>](../../../../docs/framework/wcf/extending/custom-tokens.md)  
 [<span data-ttu-id="936e6-129">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="936e6-129">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
