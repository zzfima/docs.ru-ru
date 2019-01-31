---
title: <secureConversationAuthentication> из <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 13e9312e4c4eade003fec77909a743009aa9bca7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278529"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="867da-102">\<secureConversationAuthentication > из \<serviceCredential ></span><span class="sxs-lookup"><span data-stu-id="867da-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="867da-103">Задает параметры службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="867da-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="867da-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="867da-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="867da-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="867da-105">\<behaviors></span></span>  
<span data-ttu-id="867da-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="867da-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="867da-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="867da-107">\<behavior></span></span>  
<span data-ttu-id="867da-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="867da-108">\<serviceCredentials></span></span>  
<span data-ttu-id="867da-109">\<secureConversationAuthentication></span><span class="sxs-lookup"><span data-stu-id="867da-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="867da-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="867da-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="867da-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="867da-111">Attributes and Elements</span></span>  
 <span data-ttu-id="867da-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="867da-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="867da-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="867da-113">Attributes</span></span>  
  
|<span data-ttu-id="867da-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="867da-114">Attribute</span></span>|<span data-ttu-id="867da-115">Описание</span><span class="sxs-lookup"><span data-stu-id="867da-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="867da-116">Строка, указывающая используемый тип <xref:System.ServiceModel.Security.SecurityStateEncoder>.</span><span class="sxs-lookup"><span data-stu-id="867da-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="867da-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="867da-117">Child Elements</span></span>  
 <span data-ttu-id="867da-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="867da-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="867da-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="867da-119">Parent Elements</span></span>  
  
|<span data-ttu-id="867da-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="867da-120">Element</span></span>|<span data-ttu-id="867da-121">Описание</span><span class="sxs-lookup"><span data-stu-id="867da-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="867da-122">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="867da-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="867da-123">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="867da-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="867da-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="867da-124">Remarks</span></span>  
 <span data-ttu-id="867da-125">Данный элемент конфигурации используется для указания списка известных типов утверждений для сериализации файлов cookie маркера контекста безопасности (SCT), а также в качестве кодировщика для шифрования и защиты данных файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="867da-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="867da-126">Дополнительные сведения о маркерах контекста безопасности см. в разделе <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="867da-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="867da-127">См. также</span><span class="sxs-lookup"><span data-stu-id="867da-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
