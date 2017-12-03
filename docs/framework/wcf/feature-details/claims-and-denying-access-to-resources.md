---
title: "Утверждения и запрет доступа к ресурсам"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: claims [WCF], denying access to resources
ms.assetid: 145ebb41-680e-4256-b14c-1efb4af1e982
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 00d6a797b8099313c15d075457ee757c1f22f744
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="claims-and-denying-access-to-resources"></a><span data-ttu-id="09d6b-102">Утверждения и запрет доступа к ресурсам</span><span class="sxs-lookup"><span data-stu-id="09d6b-102">Claims and Denying Access to Resources</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="09d6b-103"> поддерживает механизм авторизации на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="09d6b-103"> supports a claims-based authorization mechanism.</span></span> <span data-ttu-id="09d6b-104">Системы могут предоставлять доступ к ресурсам на основе утверждений или отказывать в доступе к ресурсам на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="09d6b-104">As well as allowing access to resources based on the presence of claims, systems often deny access to resources based on the presence of claims.</span></span> <span data-ttu-id="09d6b-105">Такие системы должны сначала проверять контекст <xref:System.IdentityModel.Policy.AuthorizationContext> на наличие утверждений, запрещающих доступ, а лишь затем - на наличие утверждений, разрешающих доступ.</span><span class="sxs-lookup"><span data-stu-id="09d6b-105">Such systems should examine the <xref:System.IdentityModel.Policy.AuthorizationContext> for claims that result in access being denied before looking for claims that result in access being allowed.</span></span>  
  
 <span data-ttu-id="09d6b-106">Например, система может отказать в доступе к ресурсу всем пользователям, имеющим утверждение типа `Age`, право <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A> и значение ресурса `Under 21`, если для данного удостоверения также имеется утверждение типа `Name`, право <xref:System.IdentityModel.Claims.Rights.Identity%2A> и значение ресурса `Mallory`.</span><span class="sxs-lookup"><span data-stu-id="09d6b-106">For example, a system might deny access to a resource to anyone who has a claim with a type of `Age`, a right of <xref:System.IdentityModel.Claims.Rights.PossessProperty%2A>, and a resource value of `Under 21` only when that identity also has a claim of type `Name`, a right of <xref:System.IdentityModel.Claims.Rights.Identity%2A>, and a resource value of `Mallory`.</span></span> <span data-ttu-id="09d6b-107">Иными словами, система отказывает в доступе пользователям младше 21 года и предоставляет доступ пользователю с именем Mallory.</span><span class="sxs-lookup"><span data-stu-id="09d6b-107">Put another way, the system denies access to anyone who is under 21 years old and grants access when the name is Mallory.</span></span> <span data-ttu-id="09d6b-108">Для правильно реализации такой семантики важно сначала проверять утверждение `Age`, чтобы определить, что пользователю исполнился 21 год.</span><span class="sxs-lookup"><span data-stu-id="09d6b-108">To correctly implement this semantic, it is important to look for the `Age` claim first and determine whether the age is under 21 years old.</span></span> <span data-ttu-id="09d6b-109">В противном случае, если пользователь Мэллори младше 21 года, он получит доступ к ресурсам только на том основании, что он соответствует утверждению `Name`.</span><span class="sxs-lookup"><span data-stu-id="09d6b-109">Otherwise, if Mallory is under 21, then the resource may be granted access solely on the basis of the `Name` claim.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09d6b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="09d6b-110">See Also</span></span>  
 [<span data-ttu-id="09d6b-111">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="09d6b-111">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 [<span data-ttu-id="09d6b-112">Утверждения и маркеры</span><span class="sxs-lookup"><span data-stu-id="09d6b-112">Claims and Tokens</span></span>](../../../../docs/framework/wcf/feature-details/claims-and-tokens.md)
