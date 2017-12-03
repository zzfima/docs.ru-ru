---
title: "Утверждения и маркеры SAML"
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
helpviewer_keywords:
- WCF, federation
- federation
- issued tokens
- SAML token
ms.assetid: 930b6e34-9eab-4e95-826c-4e06659bb977
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4e1d797b7c86f57f4f9cf4d604e264d3534a79bf
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="saml-tokens-and-claims"></a><span data-ttu-id="84e34-102">Утверждения и маркеры SAML</span><span class="sxs-lookup"><span data-stu-id="84e34-102">SAML Tokens and Claims</span></span>
<span data-ttu-id="84e34-103">Язык разметки утверждения безопасности (SAML) *маркеры* являются XML-представлением утверждений.</span><span class="sxs-lookup"><span data-stu-id="84e34-103">Security Assertions Markup Language (SAML) *tokens* are XML representations of claims.</span></span> <span data-ttu-id="84e34-104">По умолчанию маркеры SAML [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] в сценариях федеративной безопасности используется в следующих *выданные маркеры*.</span><span class="sxs-lookup"><span data-stu-id="84e34-104">By default, SAML tokens [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] uses in federated security scenarios are *issued tokens*.</span></span>  
  
 <span data-ttu-id="84e34-105">Маркеры SAML содержат операторы, которые являются набором утверждений, выполненных одной сущностью в отношении другой сущности.</span><span class="sxs-lookup"><span data-stu-id="84e34-105">SAML tokens carry statements that are sets of claims made by one entity about another entity.</span></span> <span data-ttu-id="84e34-106">Например, в сценариях федеративной безопасности операторы относительно пользователя выполняются в системе службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="84e34-106">For example, in federated security scenarios, the statements are made by a security token service about a user in the system.</span></span> <span data-ttu-id="84e34-107">Служба маркеров безопасности подписывает маркер SAML, чтобы подтвердить достоверность оператора, содержащегося в маркере.</span><span class="sxs-lookup"><span data-stu-id="84e34-107">The security token service signs the SAML token to indicate the veracity of the statements contained in the token.</span></span> <span data-ttu-id="84e34-108">Кроме того, маркер SAML связан с материалом ключа шифрования, который должен быть известен пользователю маркера SAML.</span><span class="sxs-lookup"><span data-stu-id="84e34-108">In addition, the SAML token is associated with cryptographic key material that the user of the SAML token proves knowledge of.</span></span> <span data-ttu-id="84e34-109">Эта проверка убеждает проверяющую сторону, что на самом деле маркер SAML был выдан указанному пользователю.</span><span class="sxs-lookup"><span data-stu-id="84e34-109">This proof satisfies the relying party that the SAML token was, in fact, issued to that user.</span></span> <span data-ttu-id="84e34-110">Например, в типичном сценарии происходит следующее.</span><span class="sxs-lookup"><span data-stu-id="84e34-110">For example, in a typical scenario:</span></span>  
  
1.  <span data-ttu-id="84e34-111">Клиент запрашивает маркер SAML у службы маркеров безопасности, проходя проверку подлинности в службе маркеров безопасности с использованием учетных данных Windows.</span><span class="sxs-lookup"><span data-stu-id="84e34-111">A client requests a SAML token from a security token service, authenticating to that security token service by using Windows credentials.</span></span>  
  
2.  <span data-ttu-id="84e34-112">Служба маркеров безопасности выдает маркер SAML клиенту.</span><span class="sxs-lookup"><span data-stu-id="84e34-112">The security token service issues a SAML token to the client.</span></span> <span data-ttu-id="84e34-113">Маркер SAML подписан сертификатом, связанным со службой маркеров безопасности, и содержит ключ проверки, зашифрованный для целевой службы.</span><span class="sxs-lookup"><span data-stu-id="84e34-113">The SAML token is signed with a certificate associated with the security token service and contains a proof key encrypted for the target service.</span></span>  
  
3.  <span data-ttu-id="84e34-114">Клиент также получает копию *ключ проверки*.</span><span class="sxs-lookup"><span data-stu-id="84e34-114">The client also receives a copy of the *proof key*.</span></span> <span data-ttu-id="84e34-115">Клиент представляет маркер SAML службе приложений ( *проверяющая сторона*) и подписывает сообщение с помощью этого ключа проверки.</span><span class="sxs-lookup"><span data-stu-id="84e34-115">The client then presents the SAML token to the application service (the *relying party*) and signs the message with that proof key.</span></span>  
  
4.  <span data-ttu-id="84e34-116">Подпись маркера SAML указывает проверяющей стороне, что маркер выдан службой маркеров безопасности.</span><span class="sxs-lookup"><span data-stu-id="84e34-116">The signature over the SAML token tells the relying party that the security token service issued the token.</span></span> <span data-ttu-id="84e34-117">Подпись сообщения, созданная при помощи ключа проверки, указывает проверяющей стороне, что маркер был выдан клиенту.</span><span class="sxs-lookup"><span data-stu-id="84e34-117">The message signature created with the proof key tells the relying party that the token was issued to the client.</span></span>  
  
## <a name="from-claims-to-samlattributes"></a><span data-ttu-id="84e34-118">От Claims к SamlAttributes</span><span class="sxs-lookup"><span data-stu-id="84e34-118">From Claims to SamlAttributes</span></span>  
 <span data-ttu-id="84e34-119">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] операторы в маркерах SAML моделируются как объекты <xref:System.IdentityModel.Tokens.SamlAttribute>, которые могут заполняться прямо из объектов <xref:System.IdentityModel.Claims.Claim>. Если у предоставляемого объекта <xref:System.IdentityModel.Claims.Claim> есть свойство <xref:System.IdentityModel.Claims.Claim.Right%2A> равное <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, и свойство <xref:System.IdentityModel.Claims.Claim.Resource%2A> принадлежит к типу <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="84e34-119">In [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], statements in SAML tokens are modeled as <xref:System.IdentityModel.Tokens.SamlAttribute> objects, which can be populated directly from <xref:System.IdentityModel.Claims.Claim> objects, provided the <xref:System.IdentityModel.Claims.Claim> object has a <xref:System.IdentityModel.Claims.Claim.Right%2A> property of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> and the <xref:System.IdentityModel.Claims.Claim.Resource%2A> property is of type <xref:System.String>.</span></span> <span data-ttu-id="84e34-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="84e34-120">For example:</span></span>  
  
 [!code-csharp[c_CreateSTS#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_creatests/cs/source.cs#8)]
 [!code-vb[c_CreateSTS#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_creatests/vb/source.vb#8)]  
  
> [!NOTE]
>  <span data-ttu-id="84e34-121">Если в сообщениях маркеры SAML сериализуются, выдаются они службой маркеров безопасности или предоставляются клиентами службам как часть проверки подлинности, максимальный размер квоты сообщения должен быть достаточно большим, чтобы вместить маркер SAML и другие части сообщения.</span><span class="sxs-lookup"><span data-stu-id="84e34-121">When SAML tokens are serialized in messages, either when they are issued by a security token service or when they are presented by clients to services as part of authentication, the maximum message size quota must be sufficiently large to accommodate the SAML token and the other message parts.</span></span> <span data-ttu-id="84e34-122">Как правило, по умолчанию квоты на размер сообщения являются достаточными.</span><span class="sxs-lookup"><span data-stu-id="84e34-122">In normal cases, the default message size quotas are sufficient.</span></span> <span data-ttu-id="84e34-123">Впрочем, в случае большого размера маркера SAML (когда он содержит сотни утверждений), может потребоваться увеличение квот для выделения места сериализованному маркеру.</span><span class="sxs-lookup"><span data-stu-id="84e34-123">However, in cases where a SAML token is large because it contains hundreds of claims, you may need to increase the quotas to accommodate the serialized token.</span></span> [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)]<span data-ttu-id="84e34-124">[Вопросы безопасности для данных](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span><span class="sxs-lookup"><span data-stu-id="84e34-124"> [Security Considerations for Data](../../../../docs/framework/wcf/feature-details/security-considerations-for-data.md).</span></span>  
  
## <a name="from-samlattributes-to-claims"></a><span data-ttu-id="84e34-125">От SamlAttributes к Claims</span><span class="sxs-lookup"><span data-stu-id="84e34-125">From SamlAttributes to Claims</span></span>  
 <span data-ttu-id="84e34-126">Различные операторы в маркере SAML преобразуются в объекты <xref:System.IdentityModel.Policy.IAuthorizationPolicy>, которые помещаются в класс <xref:System.IdentityModel.Policy.AuthorizationContext>, когда в сообщении содержатся маркеры SAML.</span><span class="sxs-lookup"><span data-stu-id="84e34-126">When SAML tokens are received in messages, the various statements in the SAML token are turned into <xref:System.IdentityModel.Policy.IAuthorizationPolicy> objects that are placed into the <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span> <span data-ttu-id="84e34-127">Утверждения от каждого оператора SAML возвращаются свойством <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> класса <xref:System.IdentityModel.Policy.AuthorizationContext> и могут быть проверены на необходимость проверки подлинности и авторизации пользователя.</span><span class="sxs-lookup"><span data-stu-id="84e34-127">The claims from each SAML statement are returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> and can be examined to determine whether to authenticate and authorize the user.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="84e34-128">См. также</span><span class="sxs-lookup"><span data-stu-id="84e34-128">See Also</span></span>  
 <xref:System.IdentityModel.Policy.AuthorizationContext>  
 <xref:System.IdentityModel.Policy.IAuthorizationPolicy>  
 <xref:System.IdentityModel.Claims.ClaimSet>  
 [<span data-ttu-id="84e34-129">Федерации</span><span class="sxs-lookup"><span data-stu-id="84e34-129">Federation</span></span>](../../../../docs/framework/wcf/feature-details/federation.md)  
 [<span data-ttu-id="84e34-130">Как: создание федеративного клиента</span><span class="sxs-lookup"><span data-stu-id="84e34-130">How to: Create a Federated Client</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-federated-client.md)  
 [<span data-ttu-id="84e34-131">Как: настройте учетные данные для службы федерации</span><span class="sxs-lookup"><span data-stu-id="84e34-131">How to: Configure Credentials on a Federation Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-configure-credentials-on-a-federation-service.md)  
 [<span data-ttu-id="84e34-132">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="84e34-132">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="84e34-133">Утверждения и маркеры</span><span class="sxs-lookup"><span data-stu-id="84e34-133">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)  
 [<span data-ttu-id="84e34-134">Создание утверждений и значения ресурсов</span><span class="sxs-lookup"><span data-stu-id="84e34-134">Claim Creation and Resource Values</span></span>](../../../../docs/framework/wcf/feature-details/claim-creation-and-resource-values.md)  
 [<span data-ttu-id="84e34-135">Как: Создание пользовательского утверждения</span><span class="sxs-lookup"><span data-stu-id="84e34-135">How to: Create a Custom Claim</span></span>](../../../../docs/framework/wcf/extending/how-to-create-a-custom-claim.md)
