---
title: <certificate> для <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850014"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="27a7d-102">\<> сертификатов для \<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="27a7d-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="27a7d-103">Задает сертификат X.509, используемый для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="27a7d-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="27a7d-104">Дополнительные сведения о задании значения элемента см. в разделе [удостоверение службы и проверка подлинности](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="27a7d-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="27a7d-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="27a7d-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="27a7d-106">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="27a7d-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="27a7d-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> клиента**](client.md)</span><span class="sxs-lookup"><span data-stu-id="27a7d-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="27a7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> конечной точки**](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="27a7d-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="27a7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> удостоверений**](identity.md)</span><span class="sxs-lookup"><span data-stu-id="27a7d-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="27a7d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> сертификата**</span><span class="sxs-lookup"><span data-stu-id="27a7d-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a7d-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27a7d-111">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27a7d-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="27a7d-112">Attributes and Elements</span></span>  
 <span data-ttu-id="27a7d-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="27a7d-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27a7d-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="27a7d-114">Attributes</span></span>  
  
|<span data-ttu-id="27a7d-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="27a7d-115">Attribute</span></span>|<span data-ttu-id="27a7d-116">Описание</span><span class="sxs-lookup"><span data-stu-id="27a7d-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="27a7d-117">encodedValue</span><span class="sxs-lookup"><span data-stu-id="27a7d-117">encodedValue</span></span>|<span data-ttu-id="27a7d-118">Кодировка Base64 сертификата.</span><span class="sxs-lookup"><span data-stu-id="27a7d-118">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27a7d-119">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="27a7d-119">Child Elements</span></span>  
 <span data-ttu-id="27a7d-120">Нет.</span><span class="sxs-lookup"><span data-stu-id="27a7d-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27a7d-121">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="27a7d-121">Parent Elements</span></span>  
  
|<span data-ttu-id="27a7d-122">Элемент</span><span class="sxs-lookup"><span data-stu-id="27a7d-122">Element</span></span>|<span data-ttu-id="27a7d-123">Описание</span><span class="sxs-lookup"><span data-stu-id="27a7d-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27a7d-124">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="27a7d-124">\<identity></span></span>](identity.md)|<span data-ttu-id="27a7d-125">Задает удостоверение службы, подлинность которой должна быть проверена клиентом.</span><span class="sxs-lookup"><span data-stu-id="27a7d-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="27a7d-126">Пример</span><span class="sxs-lookup"><span data-stu-id="27a7d-126">Example</span></span>  
 <span data-ttu-id="27a7d-127">В следующем коде задается кодированное представление сертификата, используемого для проверки сервера при подключении к клиенту.</span><span class="sxs-lookup"><span data-stu-id="27a7d-127">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="27a7d-128">См. также</span><span class="sxs-lookup"><span data-stu-id="27a7d-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="27a7d-129">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="27a7d-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="27a7d-130">\<> удостоверений</span><span class="sxs-lookup"><span data-stu-id="27a7d-130">\<identity></span></span>](identity.md)
