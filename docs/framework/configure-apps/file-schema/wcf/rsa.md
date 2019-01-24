---
title: '&lt;RSA&gt;'
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 74da1e2ae02f151f928afec24d6af3adf703bdcd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54612806"
---
# <a name="ltrsagt"></a><span data-ttu-id="9f450-102">&lt;RSA&gt;</span><span class="sxs-lookup"><span data-stu-id="9f450-102">&lt;rsa&gt;</span></span>
<span data-ttu-id="9f450-103">Защищенный клиент WCF, подключающийся к конечной точке с использованием этого удостоверения, проверяет, что среди утверждений, представленных сервером, есть утверждение, содержащее открытый ключ RSA, который используется для конструирования этого удостоверения.</span><span class="sxs-lookup"><span data-stu-id="9f450-103">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="9f450-104">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="9f450-104">\<identity></span></span>  
<span data-ttu-id="9f450-105">\<RSA ></span><span class="sxs-lookup"><span data-stu-id="9f450-105">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f450-106">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9f450-106">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f450-107">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9f450-107">Attributes and Elements</span></span>  
 <span data-ttu-id="9f450-108">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9f450-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f450-109">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9f450-109">Attributes</span></span>  
  
|<span data-ttu-id="9f450-110">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9f450-110">Attribute</span></span>|<span data-ttu-id="9f450-111">Описание</span><span class="sxs-lookup"><span data-stu-id="9f450-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9f450-112">value</span><span class="sxs-lookup"><span data-stu-id="9f450-112">value</span></span>|<span data-ttu-id="9f450-113">Дополнительная строка.</span><span class="sxs-lookup"><span data-stu-id="9f450-113">Optional String.</span></span> <span data-ttu-id="9f450-114">Значение открытого ключа RSA, с которым происходит сравнение на клиенте.</span><span class="sxs-lookup"><span data-stu-id="9f450-114">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f450-115">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9f450-115">Child Elements</span></span>  
 <span data-ttu-id="9f450-116">Нет</span><span class="sxs-lookup"><span data-stu-id="9f450-116">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f450-117">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9f450-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9f450-118">Элемент</span><span class="sxs-lookup"><span data-stu-id="9f450-118">Element</span></span>|<span data-ttu-id="9f450-119">Описание</span><span class="sxs-lookup"><span data-stu-id="9f450-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f450-120">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="9f450-120">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="9f450-121">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="9f450-121">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f450-122">Примечания</span><span class="sxs-lookup"><span data-stu-id="9f450-122">Remarks</span></span>  
 <span data-ttu-id="9f450-123">Проверка RSA дает возможность ограничить проверку подлинности, задействовав один сертификат с использованием его ключа RSA или другого значения ключа RSA, созданного в отдельном порядке.</span><span class="sxs-lookup"><span data-stu-id="9f450-123">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="9f450-124">Это позволяет выполнить более строгую проверку подлинности конкретного ключа RSA, однако если значение ключа RSA будет изменено, служба больше не будет работать с существующими клиентами.</span><span class="sxs-lookup"><span data-stu-id="9f450-124">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="9f450-125">Дополнительные сведения об использовании удостоверения для проверки службы для клиента, см. в разделе [службы идентификации и проверки подлинности](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="9f450-125">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f450-126">Пример</span><span class="sxs-lookup"><span data-stu-id="9f450-126">Example</span></span>  
 <span data-ttu-id="9f450-127">В следующем коде конфигурации задается значение открытого ключа сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="9f450-127">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="9f450-128">См. также</span><span class="sxs-lookup"><span data-stu-id="9f450-128">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="9f450-129">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="9f450-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="9f450-130">\<удостоверение ></span><span class="sxs-lookup"><span data-stu-id="9f450-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
