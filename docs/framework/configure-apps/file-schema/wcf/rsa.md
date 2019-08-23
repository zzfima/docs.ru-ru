---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: dd8e5ab11a7c019a8fe967f1c14b88a922a16c33
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69934740"
---
# <a name="rsa"></a><span data-ttu-id="f449d-101">\<> RSA</span><span class="sxs-lookup"><span data-stu-id="f449d-101">\<rsa></span></span>
<span data-ttu-id="f449d-102">Защищенный клиент WCF, подключающийся к конечной точке с использованием этого удостоверения, проверяет, что среди утверждений, представленных сервером, есть утверждение, содержащее открытый ключ RSA, который используется для конструирования этого удостоверения.</span><span class="sxs-lookup"><span data-stu-id="f449d-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
 <span data-ttu-id="f449d-103">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="f449d-103">\<identity></span></span>  
<span data-ttu-id="f449d-104">\<> RSA</span><span class="sxs-lookup"><span data-stu-id="f449d-104">\<rsa></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f449d-105">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="f449d-105">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f449d-106">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="f449d-106">Attributes and Elements</span></span>  
 <span data-ttu-id="f449d-107">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="f449d-107">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f449d-108">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="f449d-108">Attributes</span></span>  
  
|<span data-ttu-id="f449d-109">Атрибут</span><span class="sxs-lookup"><span data-stu-id="f449d-109">Attribute</span></span>|<span data-ttu-id="f449d-110">Описание</span><span class="sxs-lookup"><span data-stu-id="f449d-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f449d-111">value</span><span class="sxs-lookup"><span data-stu-id="f449d-111">value</span></span>|<span data-ttu-id="f449d-112">Дополнительная строка.</span><span class="sxs-lookup"><span data-stu-id="f449d-112">Optional String.</span></span> <span data-ttu-id="f449d-113">Значение открытого ключа RSA, с которым происходит сравнение на клиенте.</span><span class="sxs-lookup"><span data-stu-id="f449d-113">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f449d-114">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="f449d-114">Child Elements</span></span>  
 <span data-ttu-id="f449d-115">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="f449d-115">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f449d-116">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="f449d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="f449d-117">Элемент</span><span class="sxs-lookup"><span data-stu-id="f449d-117">Element</span></span>|<span data-ttu-id="f449d-118">Описание</span><span class="sxs-lookup"><span data-stu-id="f449d-118">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f449d-119">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="f449d-119">\<identity></span></span>](identity.md)|<span data-ttu-id="f449d-120">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="f449d-120">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f449d-121">Примечания</span><span class="sxs-lookup"><span data-stu-id="f449d-121">Remarks</span></span>  
 <span data-ttu-id="f449d-122">Проверка RSA дает возможность ограничить проверку подлинности, задействовав один сертификат с использованием его ключа RSA или другого значения ключа RSA, созданного в отдельном порядке.</span><span class="sxs-lookup"><span data-stu-id="f449d-122">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="f449d-123">Это позволяет выполнить более строгую проверку подлинности конкретного ключа RSA, однако если значение ключа RSA будет изменено, служба больше не будет работать с существующими клиентами.</span><span class="sxs-lookup"><span data-stu-id="f449d-123">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="f449d-124">Дополнительные сведения об использовании удостоверения для проверки службы для клиента см. в статье [удостоверение службы и проверка](../../../wcf/feature-details/service-identity-and-authentication.md)подлинности.</span><span class="sxs-lookup"><span data-stu-id="f449d-124">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f449d-125">Пример</span><span class="sxs-lookup"><span data-stu-id="f449d-125">Example</span></span>  
 <span data-ttu-id="f449d-126">В следующем коде конфигурации задается значение открытого ключа сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="f449d-126">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="f449d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="f449d-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="f449d-128">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="f449d-128">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f449d-129">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="f449d-129">\<identity></span></span>](identity.md)
