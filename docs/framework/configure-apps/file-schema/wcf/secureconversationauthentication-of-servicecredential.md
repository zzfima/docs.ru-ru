---
title: "&lt;secureConversationAuthentication&gt; для &lt;serviceCredential&gt;"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
caps.latest.revision: "7"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 0fb9ff476812b6b889750e8eb7b80efce801f041
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecureconversationauthenticationgt-of-ltservicecredentialgt"></a><span data-ttu-id="6615d-102">&lt;secureConversationAuthentication&gt; для &lt;serviceCredential&gt;</span><span class="sxs-lookup"><span data-stu-id="6615d-102">&lt;secureConversationAuthentication&gt; of &lt;serviceCredential&gt;</span></span>
<span data-ttu-id="6615d-103">Задает параметры службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="6615d-103">Specifies the settings for a secure conversation service.</span></span>  
  
 <span data-ttu-id="6615d-104">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="6615d-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="6615d-105">\<поведения ></span><span class="sxs-lookup"><span data-stu-id="6615d-105">\<behaviors></span></span>  
<span data-ttu-id="6615d-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="6615d-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="6615d-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="6615d-107">\<behavior></span></span>  
<span data-ttu-id="6615d-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="6615d-108">\<serviceCredentials></span></span>  
<span data-ttu-id="6615d-109">\<secureConversationAuthentication ></span><span class="sxs-lookup"><span data-stu-id="6615d-109">\<secureConversationAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6615d-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="6615d-110">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6615d-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="6615d-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6615d-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="6615d-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6615d-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="6615d-113">Attributes</span></span>  
  
|<span data-ttu-id="6615d-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="6615d-114">Attribute</span></span>|<span data-ttu-id="6615d-115">Описание</span><span class="sxs-lookup"><span data-stu-id="6615d-115">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="6615d-116">Строка, указывающая используемый тип <xref:System.ServiceModel.Security.SecurityStateEncoder>.</span><span class="sxs-lookup"><span data-stu-id="6615d-116">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6615d-117">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="6615d-117">Child Elements</span></span>  
 <span data-ttu-id="6615d-118">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="6615d-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6615d-119">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="6615d-119">Parent Elements</span></span>  
  
|<span data-ttu-id="6615d-120">Элемент</span><span class="sxs-lookup"><span data-stu-id="6615d-120">Element</span></span>|<span data-ttu-id="6615d-121">Описание</span><span class="sxs-lookup"><span data-stu-id="6615d-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6615d-122">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="6615d-122">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="6615d-123">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="6615d-123">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6615d-124">Примечания</span><span class="sxs-lookup"><span data-stu-id="6615d-124">Remarks</span></span>  
 <span data-ttu-id="6615d-125">Данный элемент конфигурации используется для указания списка известных типов утверждений для сериализации файлов cookie маркера контекста безопасности (SCT), а также в качестве кодировщика для шифрования и защиты данных файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="6615d-125">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="6615d-126">Дополнительные сведения о маркерах контекста безопасности см. в разделе <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="6615d-126">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6615d-127">См. также</span><span class="sxs-lookup"><span data-stu-id="6615d-127">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>  
 <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>  
 <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
