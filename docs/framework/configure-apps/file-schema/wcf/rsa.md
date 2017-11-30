---
title: '&lt;RSA&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
caps.latest.revision: "6"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ab07508c4cab32cb2a60d37af368c345a0f12d88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltrsagt"></a><span data-ttu-id="89b85-102">&lt;RSA&gt;</span><span class="sxs-lookup"><span data-stu-id="89b85-102">&lt;rsa&gt;</span></span>
<span data-ttu-id="89b85-103">Защищенный клиент WCF, подключающийся к конечной точке с использованием этого удостоверения, проверяет, что среди утверждений, представленных сервером, есть утверждение, содержащее открытый ключ RSA, который используется для конструирования этого удостоверения.</span><span class="sxs-lookup"><span data-stu-id="89b85-103">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="89b85-104">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="89b85-104">\<identity></span></span>  
<span data-ttu-id="89b85-105">\<RSA ></span><span class="sxs-lookup"><span data-stu-id="89b85-105">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89b85-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="89b85-106">Syntax</span></span>  
  
```xml  
<rsa value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="89b85-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="89b85-107">Attributes and Elements</span></span>  
 <span data-ttu-id="89b85-108">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="89b85-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="89b85-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="89b85-109">Attributes</span></span>  
  
|<span data-ttu-id="89b85-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="89b85-110">Attribute</span></span>|<span data-ttu-id="89b85-111">Описание</span><span class="sxs-lookup"><span data-stu-id="89b85-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="89b85-112">value</span><span class="sxs-lookup"><span data-stu-id="89b85-112">value</span></span>|<span data-ttu-id="89b85-113">Дополнительная строка.</span><span class="sxs-lookup"><span data-stu-id="89b85-113">Optional String.</span></span> <span data-ttu-id="89b85-114">Значение открытого ключа RSA, с которым происходит сравнение на клиенте.</span><span class="sxs-lookup"><span data-stu-id="89b85-114">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="89b85-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="89b85-115">Child Elements</span></span>  
 <span data-ttu-id="89b85-116">Нет</span><span class="sxs-lookup"><span data-stu-id="89b85-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="89b85-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="89b85-117">Parent Elements</span></span>  
  
|<span data-ttu-id="89b85-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="89b85-118">Element</span></span>|<span data-ttu-id="89b85-119">Описание</span><span class="sxs-lookup"><span data-stu-id="89b85-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="89b85-120">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="89b85-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="89b85-121">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="89b85-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="89b85-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="89b85-122">Remarks</span></span>  
 <span data-ttu-id="89b85-123">Проверка RSA дает возможность ограничить проверку подлинности, задействовав один сертификат с использованием его ключа RSA или другого значения ключа RSA, созданного в отдельном порядке.</span><span class="sxs-lookup"><span data-stu-id="89b85-123">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="89b85-124">Это позволяет выполнить более строгую проверку подлинности конкретного ключа RSA, однако если значение ключа RSA будет изменено, служба больше не будет работать с существующими клиентами.</span><span class="sxs-lookup"><span data-stu-id="89b85-124">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="89b85-125">Дополнительные сведения об использовании идентификаторов для проверки службы для клиента см. в разделе [службы удостоверений и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="89b85-125">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="89b85-126">Пример</span><span class="sxs-lookup"><span data-stu-id="89b85-126">Example</span></span>  
 <span data-ttu-id="89b85-127">В следующем коде конфигурации задается значение открытого ключа сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="89b85-127">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>  
  <rsa value = "0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000"/>  
</identity>  
```  
  
## <a name="see-also"></a><span data-ttu-id="89b85-128">См. также</span><span class="sxs-lookup"><span data-stu-id="89b85-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.RsaEndpointIdentity>  
 [<span data-ttu-id="89b85-129">Службы идентификации и проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="89b85-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="89b85-130">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="89b85-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
