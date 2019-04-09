---
title: <claimTypeRequirements> элемент
ms.date: 03/30/2017
ms.assetid: a26efe73-4bad-4731-8cad-27f00d54354b
ms.openlocfilehash: 236ae880fff24f7ccbf5d6c9c03c0208d446688f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59085848"
---
# <a name="claimtyperequirements-element"></a><span data-ttu-id="ef1e1-102">\<claimTypeRequirements > элемент</span><span class="sxs-lookup"><span data-stu-id="ef1e1-102">\<claimTypeRequirements> element</span></span>
<span data-ttu-id="ef1e1-103">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="ef1e1-103">Specifies a collection of required claim types.</span></span>  
  
 <span data-ttu-id="ef1e1-104">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="ef1e1-104">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="ef1e1-105">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="ef1e1-105">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="ef1e1-106">Каждый дочерний элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="ef1e1-106">Each child element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>  
  
 <span data-ttu-id="ef1e1-107">Требование типа утверждения состоит из универсального кода ресурса (URI) типа утверждения, запрашиваемого в выданном маркере, и логического параметра, который определяет, является ли обязательным этот тип утверждения в выданном маркере.</span><span class="sxs-lookup"><span data-stu-id="ef1e1-107">A claim type requirement consists of the URI of the claim type requested in the issued token along with a Boolean parameter that indicates whether that claim type is required in the issued token, or is optional.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef1e1-108">См. также</span><span class="sxs-lookup"><span data-stu-id="ef1e1-108">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Configuration.SecurityElementBase.IssuedTokenParameters%2A>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="ef1e1-109">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="ef1e1-109">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="ef1e1-110">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="ef1e1-110">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ef1e1-111">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="ef1e1-111">Security Capabilities with Custom Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="ef1e1-112">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="ef1e1-112">Federation and Issued Tokens</span></span>](../../../../../docs/framework/wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="ef1e1-113">\<add></span><span class="sxs-lookup"><span data-stu-id="ef1e1-113">\<add></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/add-of-claimtyperequirements.md)
- [<span data-ttu-id="ef1e1-114">Привязки</span><span class="sxs-lookup"><span data-stu-id="ef1e1-114">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="ef1e1-115">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="ef1e1-115">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="ef1e1-116">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="ef1e1-116">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="ef1e1-117">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="ef1e1-117">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="ef1e1-118">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="ef1e1-118">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="ef1e1-119">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="ef1e1-119">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
