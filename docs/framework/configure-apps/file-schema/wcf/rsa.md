---
title: <rsa>
ms.date: 03/30/2017
ms.assetid: ae1f2267-e40d-42ff-8abf-06ab7067bdb9
ms.openlocfilehash: 0e1651f563bdb2b2b24eacacf7bfe387e33a82c7
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855044"
---
# <a name="rsa"></a><span data-ttu-id="59e69-101">\<> RSA</span><span class="sxs-lookup"><span data-stu-id="59e69-101">\<rsa></span></span>
<span data-ttu-id="59e69-102">Защищенный клиент WCF, подключающийся к конечной точке с использованием этого удостоверения, проверяет, что среди утверждений, представленных сервером, есть утверждение, содержащее открытый ключ RSA, который используется для конструирования этого удостоверения.</span><span class="sxs-lookup"><span data-stu-id="59e69-102">A secure WCF client that connects to an endpoint with this identity verifies that the claims presented by the server contain a claim that contains the RSA public key used to construct this identity.</span></span>  
  
<span data-ttu-id="59e69-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="59e69-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="59e69-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="59e69-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="59e69-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> клиента**](client.md)</span><span class="sxs-lookup"><span data-stu-id="59e69-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="59e69-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> конечной точки**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="59e69-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="59e69-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> удостоверений**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="59e69-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="59e69-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> RSA**</span><span class="sxs-lookup"><span data-stu-id="59e69-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<rsa>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59e69-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="59e69-109">Syntax</span></span>  
  
```xml  
<rsa value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59e69-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="59e69-110">Attributes and Elements</span></span>  
 <span data-ttu-id="59e69-111">В следующих разделах описываются атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="59e69-111">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59e69-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="59e69-112">Attributes</span></span>  
  
|<span data-ttu-id="59e69-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="59e69-113">Attribute</span></span>|<span data-ttu-id="59e69-114">Описание</span><span class="sxs-lookup"><span data-stu-id="59e69-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59e69-115">value</span><span class="sxs-lookup"><span data-stu-id="59e69-115">value</span></span>|<span data-ttu-id="59e69-116">Дополнительная строка.</span><span class="sxs-lookup"><span data-stu-id="59e69-116">Optional String.</span></span> <span data-ttu-id="59e69-117">Значение открытого ключа RSA, с которым происходит сравнение на клиенте.</span><span class="sxs-lookup"><span data-stu-id="59e69-117">The RSA public key value to be compared with on the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59e69-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="59e69-118">Child Elements</span></span>  
 <span data-ttu-id="59e69-119">Отсутствуют</span><span class="sxs-lookup"><span data-stu-id="59e69-119">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59e69-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="59e69-120">Parent Elements</span></span>  
  
|<span data-ttu-id="59e69-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="59e69-121">Element</span></span>|<span data-ttu-id="59e69-122">Описание</span><span class="sxs-lookup"><span data-stu-id="59e69-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59e69-123">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="59e69-123">\<identity></span></span>](identity.md)|<span data-ttu-id="59e69-124">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="59e69-124">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59e69-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="59e69-125">Remarks</span></span>  
 <span data-ttu-id="59e69-126">Проверка RSA дает возможность ограничить проверку подлинности, задействовав один сертификат с использованием его ключа RSA или другого значения ключа RSA, созданного в отдельном порядке.</span><span class="sxs-lookup"><span data-stu-id="59e69-126">A RSA check enables you to specifically restrict authentication to a single certificate based upon its RSA key or generated your own RSA key value.</span></span> <span data-ttu-id="59e69-127">Это позволяет выполнить более строгую проверку подлинности конкретного ключа RSA, однако если значение ключа RSA будет изменено, служба больше не будет работать с существующими клиентами.</span><span class="sxs-lookup"><span data-stu-id="59e69-127">This enables stricter authentication of a specific RSA key at the expense of the service no longer working with existing clients if the RSA key value is changed.</span></span>  
  
 <span data-ttu-id="59e69-128">Дополнительные сведения об использовании удостоверения для проверки службы для клиента см. в статье [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="59e69-128">For more information about using identity to validate a service to a client, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="59e69-129">Пример</span><span class="sxs-lookup"><span data-stu-id="59e69-129">Example</span></span>  
 <span data-ttu-id="59e69-130">В следующем коде конфигурации задается значение открытого ключа сертификата X.509, используемого для проверки подлинности сервера.</span><span class="sxs-lookup"><span data-stu-id="59e69-130">The following configuration code specifies the public key value of an X.509 certificate that is used to authenticate a server.</span></span>  
  
```xml  
<identity>
  <rsa value="0000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000000" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="59e69-131">См. также</span><span class="sxs-lookup"><span data-stu-id="59e69-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.RsaEndpointIdentity>
- [<span data-ttu-id="59e69-132">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="59e69-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="59e69-133">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="59e69-133">\<identity></span></span>](identity.md)
