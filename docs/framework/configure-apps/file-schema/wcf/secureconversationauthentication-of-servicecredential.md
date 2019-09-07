---
title: <secureConversationAuthentication> из <serviceCredential>
ms.date: 03/30/2017
ms.assetid: 0bd3fac7-befd-4a45-ba51-c200b33be0fd
ms.openlocfilehash: 336969c654f332ae3d838d8fd6d1c4243838539c
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399945"
---
# <a name="secureconversationauthentication-of-servicecredential"></a><span data-ttu-id="7a549-102">\<секуреконверсатионаусентикатион > \<сервицекредентиал ></span><span class="sxs-lookup"><span data-stu-id="7a549-102">\<secureConversationAuthentication> of \<serviceCredential></span></span>
<span data-ttu-id="7a549-103">Задает параметры службы безопасного обмена данными.</span><span class="sxs-lookup"><span data-stu-id="7a549-103">Specifies the settings for a secure conversation service.</span></span>  
  
<span data-ttu-id="7a549-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7a549-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7a549-105">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="7a549-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7a549-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7a549-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)</span></span>\
<span data-ttu-id="7a549-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceBehaviors >** ](servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7a549-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceBehaviors>**](servicebehaviors.md)</span></span>\
<span data-ttu-id="7a549-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> поведения**](behavior-of-servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="7a549-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-servicebehaviors.md)</span></span>\
<span data-ttu-id="7a549-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<serviceCredentials >** ](servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="7a549-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<serviceCredentials>**](servicecredentials.md)</span></span>\
<span data-ttu-id="7a549-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Секуреконверсатионаусентикатион >**</span><span class="sxs-lookup"><span data-stu-id="7a549-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<secureConversationAuthentication>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a549-111">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="7a549-111">Syntax</span></span>  
  
```xml  
<secureConversationAuthentication securityStateEncoderType="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7a549-112">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="7a549-112">Attributes and Elements</span></span>  
 <span data-ttu-id="7a549-113">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="7a549-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7a549-114">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="7a549-114">Attributes</span></span>  
  
|<span data-ttu-id="7a549-115">Атрибут</span><span class="sxs-lookup"><span data-stu-id="7a549-115">Attribute</span></span>|<span data-ttu-id="7a549-116">Описание</span><span class="sxs-lookup"><span data-stu-id="7a549-116">Description</span></span>|  
|---------------|-----------------|  
|`securityStateEncoderType`|<span data-ttu-id="7a549-117">Строка, указывающая используемый тип <xref:System.ServiceModel.Security.SecurityStateEncoder>.</span><span class="sxs-lookup"><span data-stu-id="7a549-117">A string that specifies the type of <xref:System.ServiceModel.Security.SecurityStateEncoder> to be used.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7a549-118">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="7a549-118">Child Elements</span></span>  
 <span data-ttu-id="7a549-119">Нет.</span><span class="sxs-lookup"><span data-stu-id="7a549-119">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7a549-120">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="7a549-120">Parent Elements</span></span>  
  
|<span data-ttu-id="7a549-121">Элемент</span><span class="sxs-lookup"><span data-stu-id="7a549-121">Element</span></span>|<span data-ttu-id="7a549-122">Описание</span><span class="sxs-lookup"><span data-stu-id="7a549-122">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7a549-123">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="7a549-123">\<serviceCredentials></span></span>](servicecredentials.md)|<span data-ttu-id="7a549-124">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="7a549-124">Specifies the credential to be used in authenticating the service, and the client credential validation-related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7a549-125">Примечания</span><span class="sxs-lookup"><span data-stu-id="7a549-125">Remarks</span></span>  
 <span data-ttu-id="7a549-126">Данный элемент конфигурации используется для указания списка известных типов утверждений для сериализации файлов cookie маркера контекста безопасности (SCT), а также в качестве кодировщика для шифрования и защиты данных файлов cookie.</span><span class="sxs-lookup"><span data-stu-id="7a549-126">Use this configuration element to specify a list of known claim types for the Security Context Token (SCT) cookies serialization, as well as an encoder to encode and secure cookies information.</span></span> <span data-ttu-id="7a549-127">Дополнительные сведения о маркерах контекста безопасности см. в разделе <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span><span class="sxs-lookup"><span data-stu-id="7a549-127">For more information on SCT, see <xref:System.ServiceModel.Security.SecureConversationServiceCredential>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a549-128">См. также</span><span class="sxs-lookup"><span data-stu-id="7a549-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.SecureConversationServiceElement>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Description.ServiceCredentials.SecureConversationAuthentication%2A>
- <xref:System.ServiceModel.Security.SecureConversationServiceCredential>
