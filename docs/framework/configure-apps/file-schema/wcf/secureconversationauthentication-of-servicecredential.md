---
title: <secureConversationAuthentication> из <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 61034c2c66a6d8e27a87ec5380aa7297247eb31e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2019
ms.locfileid: "69935835"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="6114e-102">\<секуреконверсатионаусентикатион > \<сервицекредентиал ></span><span class="sxs-lookup"><span data-stu-id="6114e-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="6114e-103">Задает параметры службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="6114e-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="6114e-104">\<системой. > ServiceModel</span><span class="sxs-lookup"><span data-stu-id="6114e-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6114e-105">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="6114e-105">\<behaviors></span></span>  
<span data-ttu-id="6114e-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6114e-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="6114e-107">\<> поведения</span><span class="sxs-lookup"><span data-stu-id="6114e-107">\<behavior></span></span>  
<span data-ttu-id="6114e-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="6114e-108">\<serviceCredentials></span></span>  
<span data-ttu-id="6114e-109">\<Секуреконверсатионаусентикатион ></span><span class="sxs-lookup"><span data-stu-id="6114e-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6114e-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6114e-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6114e-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6114e-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6114e-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6114e-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6114e-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6114e-113">Attributes</span></span>  
  
|<span data-ttu-id="6114e-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6114e-114">Attribute</span></span>|<span data-ttu-id="6114e-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6114e-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="6114e-116">Строка, указывающая используемый тип <xref:System.ServiceModel.Security.SecurityStateEncoder>.</span><span class="sxs-lookup"><span data-stu-id="6114e-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6114e-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6114e-117">Child Elements</span></span>  
 <span data-ttu-id="6114e-118">Нет.</span><span class="sxs-lookup"><span data-stu-id="6114e-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6114e-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6114e-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6114e-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="6114e-120">Element</span></span>|<span data-ttu-id="6114e-121">Описание</span><span class="sxs-lookup"><span data-stu-id="6114e-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6114e-122">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="6114e-122">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="6114e-123">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="6114e-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6114e-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="6114e-124">Remarks</span></span>  
 <span data-ttu-id="6114e-125">Данный элемент конфигурации используется для указания списка известных типов утверждений для сериализации файлов cookie маркера контекста безопасности (SCT), а также в качестве кодировщика для шифрования и защиты данных файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="6114e-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="6114e-126">Дополнительные сведения о маркерах контекста безопасности см. в разделе <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="6114e-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6114e-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6114e-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
