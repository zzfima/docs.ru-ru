---
title: "&lt;claimTypeRequirements&gt; для &lt;message&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f95c5ecd-abb6-4b77-a6d7-a38727f4a142
caps.latest.revision: "4"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 747ac641f8602010819baa00033f3663e2e5f678
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltclaimtyperequirementsgt-for-ltmessagegt"></a><span data-ttu-id="6119c-102">&lt;claimTypeRequirements&gt; для &lt;message&gt;</span><span class="sxs-lookup"><span data-stu-id="6119c-102">&lt;claimTypeRequirements&gt; for &lt;message&gt;</span></span>
<span data-ttu-id="6119c-103">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="6119c-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="6119c-104">Коллекция используется службой, чтобы задать обязательные и необязательные утверждения, которые должны содержаться в выданном маркере, используемом клиентом для доступа к службе.</span><span class="sxs-lookup"><span data-stu-id="6119c-104">The collection is used by the service to specify any required and optional claims which must be in the issued token the client uses to access the service.</span></span> <span data-ttu-id="6119c-105">Служба предоставляет обязательные типы утверждений в метаданных, если публикация WDSL включена, но WCF не требует, чтобы выданный маркер содержал заданные типы утверждений.</span><span class="sxs-lookup"><span data-stu-id="6119c-105">The service exposes the required claim types in metadata if WSDL publishing is enabled but WCF does not require the issued token contain the specified claim types.</span></span> <span data-ttu-id="6119c-106">Службы, для которых необходимо принудительное наличие обязательных типов утверждений, должны использовать политику авторизации.</span><span class="sxs-lookup"><span data-stu-id="6119c-106">Services wishing to enforce required claim types are present should do using authorization policy.</span></span>  
  
 <span data-ttu-id="6119c-107">В федеративных клиентах эта коллекция содержит список обязательных и необязательных утверждений, который отправляется службе маркеров безопасности в запросе клиента для выданного маркера.</span><span class="sxs-lookup"><span data-stu-id="6119c-107">On federated clients, this collection contains the list of required and optional claims which is sent to the security token service in the client’s request for an issued token.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6119c-108">См. также</span><span class="sxs-lookup"><span data-stu-id="6119c-108">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
