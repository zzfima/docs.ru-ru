---
title: <xmlElement>
ms.date: 03/30/2017
ms.assetid: 395205c2-d8c0-4a5e-90f3-7ce3c085fccd
ms.openlocfilehash: 841331f233bb8c42c25c88ad8e9b4fb1a86faa76
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398987"
---
# <a name="xmlelement"></a><span data-ttu-id="aad7a-101">\<> xmlElement</span><span class="sxs-lookup"><span data-stu-id="aad7a-101">\<xmlElement></span></span>
<span data-ttu-id="aad7a-102">Указывает элемент XML, отправляемый в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="aad7a-102">Specifies an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>  
  
<span data-ttu-id="aad7a-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="aad7a-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="aad7a-104">&nbsp;&nbsp;[ **\<> System. serviceModel**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="aad7a-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="aad7a-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<привязки >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="aad7a-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="aad7a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<wsFederationHttpBinding >** ](wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="aad7a-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsFederationHttpBinding>**](wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="aad7a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Привязка >** </span><span class="sxs-lookup"><span data-stu-id="aad7a-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="aad7a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> безопасности**](security-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="aad7a-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="aad7a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<> сообщения**](message-element-of-wsfederationhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="aad7a-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<message>**](message-element-of-wsfederationhttpbinding.md)</span></span>\
<span data-ttu-id="aad7a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Токенрекуестпараметерс >** ](tokenrequestparameters.md)</span><span class="sxs-lookup"><span data-stu-id="aad7a-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tokenRequestParameters>**](tokenrequestparameters.md)</span></span>\
<span data-ttu-id="aad7a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<> xmlElement**</span><span class="sxs-lookup"><span data-stu-id="aad7a-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<xmlElement>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aad7a-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="aad7a-112">Syntax</span></span>  
  
```xml  
<tokenRequestParameters>
  <xmlElement xmlElement="String" />
</tokenRequestParameters>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="aad7a-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="aad7a-113">Attributes and Elements</span></span>  
 <span data-ttu-id="aad7a-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="aad7a-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="aad7a-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="aad7a-115">Attributes</span></span>  
  
|<span data-ttu-id="aad7a-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="aad7a-116">Attribute</span></span>|<span data-ttu-id="aad7a-117">Описание</span><span class="sxs-lookup"><span data-stu-id="aad7a-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="aad7a-118">xmlElement</span><span class="sxs-lookup"><span data-stu-id="aad7a-118">xmlElement</span></span>|<span data-ttu-id="aad7a-119">Строка, указывающая элемент XML, который отправляется в тексте сообщения службе маркеров безопасности при запросе маркера.</span><span class="sxs-lookup"><span data-stu-id="aad7a-119">A string specifying an XML element that is sent in the message body to the Security Token Service when requesting a token.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="aad7a-120">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="aad7a-120">Child Elements</span></span>  
 <span data-ttu-id="aad7a-121">Нет.</span><span class="sxs-lookup"><span data-stu-id="aad7a-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="aad7a-122">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="aad7a-122">Parent Elements</span></span>  
  
|<span data-ttu-id="aad7a-123">Элемент</span><span class="sxs-lookup"><span data-stu-id="aad7a-123">Element</span></span>|<span data-ttu-id="aad7a-124">Описание</span><span class="sxs-lookup"><span data-stu-id="aad7a-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="aad7a-125">\<Токенрекуестпараметерс ></span><span class="sxs-lookup"><span data-stu-id="aad7a-125">\<tokenRequestParameters></span></span>](tokenrequestparameters.md)|<span data-ttu-id="aad7a-126">Коллекция параметров запроса маркера.</span><span class="sxs-lookup"><span data-stu-id="aad7a-126">A collection of token request parameters.</span></span> <span data-ttu-id="aad7a-127">Каждый параметр представляет собой элемент XML.</span><span class="sxs-lookup"><span data-stu-id="aad7a-127">Each parameter is an XML element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="aad7a-128">См. также</span><span class="sxs-lookup"><span data-stu-id="aad7a-128">See also</span></span>

- <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.TokenRequestParameters%2A>
- <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.TokenRequestParameters%2A>
- [<span data-ttu-id="aad7a-129">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="aad7a-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="aad7a-130">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="aad7a-130">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="aad7a-131">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="aad7a-131">Security Capabilities with Custom Bindings</span></span>](../../../wcf/feature-details/security-capabilities-with-custom-bindings.md)
- [<span data-ttu-id="aad7a-132">Федерация и выданные маркеры</span><span class="sxs-lookup"><span data-stu-id="aad7a-132">Federation and Issued Tokens</span></span>](../../../wcf/feature-details/federation-and-issued-tokens.md)
- [<span data-ttu-id="aad7a-133">Привязки</span><span class="sxs-lookup"><span data-stu-id="aad7a-133">Bindings</span></span>](../../../wcf/bindings.md)
