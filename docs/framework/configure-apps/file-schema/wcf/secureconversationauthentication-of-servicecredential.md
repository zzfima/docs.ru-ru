---
title: '&lt;secureConversationAuthentication&gt; для &lt;serviceCredential&gt;'
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
author: BrucePerlerMS
ms.openlocfilehash: 3adcf7ba9814bcf494d345cf0e3f47c57df2152c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/25/2018
ms.locfileid: "47173412"
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a><span data-ttu-id="5cd22-102">&lt;secureConversationAuthentication&gt; для &lt;serviceCredential&gt;</span><span class="sxs-lookup"><span data-stu-id="5cd22-102">&lt;secureConversationAuthentication&gt; of &lt;serviceCredential&gt;</span></span>
<span data-ttu-id="5cd22-103">Задает параметры службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="5cd22-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="5cd22-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="5cd22-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="5cd22-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="5cd22-105">\<behaviors></span></span>  
<span data-ttu-id="5cd22-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="5cd22-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="5cd22-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="5cd22-107">\<behavior></span></span>  
<span data-ttu-id="5cd22-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="5cd22-108">\<serviceCredentials></span></span>  
<span data-ttu-id="5cd22-109">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="5cd22-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cd22-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="5cd22-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5cd22-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="5cd22-111">Attributes and Elements</span></span>  
 <span data-ttu-id="5cd22-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="5cd22-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5cd22-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="5cd22-113">Attributes</span></span>  
  
|<span data-ttu-id="5cd22-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="5cd22-114">Attribute</span></span>|<span data-ttu-id="5cd22-115">Описание</span><span class="sxs-lookup"><span data-stu-id="5cd22-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="5cd22-116">Строка, указывающая используемый тип <xref:System.ServiceModel.Security.SecurityStateEncoder>.</span><span class="sxs-lookup"><span data-stu-id="5cd22-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5cd22-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="5cd22-117">Child Elements</span></span>  
 <span data-ttu-id="5cd22-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="5cd22-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5cd22-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="5cd22-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5cd22-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="5cd22-120">Element</span></span>|<span data-ttu-id="5cd22-121">Описание</span><span class="sxs-lookup"><span data-stu-id="5cd22-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5cd22-122">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="5cd22-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="5cd22-123">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="5cd22-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cd22-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="5cd22-124">Remarks</span></span>  
 <span data-ttu-id="5cd22-125">Данный элемент конфигурации используется для указания списка известных типов утверждений для сериализации файлов cookie маркера контекста безопасности (SCT), а также в качестве кодировщика для шифрования и защиты данных файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="5cd22-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="5cd22-126">Дополнительные сведения о маркерах контекста безопасности см. в разделе <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="5cd22-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cd22-127">См. также</span><span class="sxs-lookup"><span data-stu-id="5cd22-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
