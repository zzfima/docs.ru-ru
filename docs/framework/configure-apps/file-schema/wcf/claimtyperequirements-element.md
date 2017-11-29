---
title: "Элемент &lt;claimTypeRequirements&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0146250c12c9c12e1f204c467a9a454b90e9f47a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltclaimtyperequirementsgt-element"></a><span data-ttu-id="b8746-102">Элемент &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="b8746-102">&lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="b8746-103">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="b8746-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="b8746-104">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="b8746-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="b8746-105">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="b8746-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="b8746-106">Каждый дочерний элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="b8746-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="b8746-107">Требование типа утверждения состоит из универсального кода ресурса (URI) типа утверждения, запрашиваемого в выданном маркере, и логического параметра, который определяет, является ли обязательным этот тип утверждения в выданном маркере.</span><span class="sxs-lookup"><span data-stu-id="b8746-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8746-108">См. также</span><span class="sxs-lookup"><span data-stu-id="b8746-108">See Also</span></span>  
 <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>  
 <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [<span data-ttu-id="b8746-109">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="b8746-109">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="b8746-110">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="b8746-110">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="b8746-111">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="b8746-111">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [<span data-ttu-id="b8746-112">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="b8746-112">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)  
 [<span data-ttu-id="b8746-113">\<add></span><span class="sxs-lookup"><span data-stu-id="b8746-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)  
 [<span data-ttu-id="b8746-114">Привязки</span><span class="sxs-lookup"><span data-stu-id="b8746-114">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="b8746-115">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="b8746-115">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="b8746-116">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="b8746-116">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="b8746-117">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b8746-117">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [<span data-ttu-id="b8746-118">Как: Создание пользовательской привязки, с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b8746-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [<span data-ttu-id="b8746-119">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="b8746-119">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
