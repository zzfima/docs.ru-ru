---
title: <add> из <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 6ba935f7f6dae0e4d9e6581f53a50c684efcbed3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79153091"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="2092f-102">\<добавить \<>> претензийTypeRequirements</span><span class="sxs-lookup"><span data-stu-id="2092f-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="2092f-103">Задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="2092f-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="2092f-104">Например, службы предъявляют требования к входящим учетным данным, которые должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="2092f-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
<span data-ttu-id="2092f-105">[**\<конфигурация>**](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2092f-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2092f-106">&nbsp;&nbsp;[**\<system.serviceМодель>**](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="2092f-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2092f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<привязки>**](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="2092f-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="2092f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<обычайОбязательный>**](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="2092f-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="2092f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<связывающая>**</span><span class="sxs-lookup"><span data-stu-id="2092f-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2092f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<>безопасности**](security-of-custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="2092f-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-custombinding.md)</span></span>\
<span data-ttu-id="2092f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<выдаетсяПараметры>**](issuedtokenparameters.md)</span><span class="sxs-lookup"><span data-stu-id="2092f-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<issuedTokenParameters>**](issuedtokenparameters.md)</span></span>\
<span data-ttu-id="2092f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)</span><span class="sxs-lookup"><span data-stu-id="2092f-112">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<claimTypeRequirements>**](claimtyperequirements-element.md)</span></span>\
<span data-ttu-id="2092f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<добавить>**</span><span class="sxs-lookup"><span data-stu-id="2092f-113">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<add>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2092f-114">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="2092f-114">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2092f-115">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="2092f-115">Attributes and Elements</span></span>  
 <span data-ttu-id="2092f-116">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="2092f-116">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2092f-117">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="2092f-117">Attributes</span></span>  
  
|<span data-ttu-id="2092f-118">attribute</span><span class="sxs-lookup"><span data-stu-id="2092f-118">Attribute</span></span>|<span data-ttu-id="2092f-119">Описание</span><span class="sxs-lookup"><span data-stu-id="2092f-119">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2092f-120">claimType</span><span class="sxs-lookup"><span data-stu-id="2092f-120">claimType</span></span>|<span data-ttu-id="2092f-121">Универсальный код ресурса (URI), определяющий тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="2092f-121">A URI that defines the type of a claim.</span></span> <span data-ttu-id="2092f-122">Например, для приобретения товара с веб-узла пользователь должен представить действительную кредитную карту с достаточным кредитным лимитом.</span><span class="sxs-lookup"><span data-stu-id="2092f-122">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="2092f-123">Типом утверждения будет универсальный код ресурса (URI) кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="2092f-123">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="2092f-124">isOptional</span><span class="sxs-lookup"><span data-stu-id="2092f-124">isOptional</span></span>|<span data-ttu-id="2092f-125">Логическое значение, указывающее, является ли утверждение необязательным.</span><span class="sxs-lookup"><span data-stu-id="2092f-125">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="2092f-126">Если утверждение является обязательным, установите для этого атрибута значение `false`.</span><span class="sxs-lookup"><span data-stu-id="2092f-126">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="2092f-127">Этот атрибут можно использовать, если служба запрашивает определенные данные, но они не являются необходимыми.</span><span class="sxs-lookup"><span data-stu-id="2092f-127">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="2092f-128">Например, если вы требуете, чтобы пользователь ввесил свое имя, фамилию и адрес, но решите, что номер телефона неявляется.</span><span class="sxs-lookup"><span data-stu-id="2092f-128">For example, if you require the user to enter their first name, last name, and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2092f-129">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="2092f-129">Child Elements</span></span>  
 <span data-ttu-id="2092f-130">Нет.</span><span class="sxs-lookup"><span data-stu-id="2092f-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="2092f-131">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="2092f-131">Parent Elements</span></span>  
  
|<span data-ttu-id="2092f-132">Элемент</span><span class="sxs-lookup"><span data-stu-id="2092f-132">Element</span></span>|<span data-ttu-id="2092f-133">Описание</span><span class="sxs-lookup"><span data-stu-id="2092f-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2092f-134">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="2092f-134">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)|<span data-ttu-id="2092f-135">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="2092f-135">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="2092f-136">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="2092f-136">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="2092f-137">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="2092f-137">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="2092f-138">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="2092f-138">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2092f-139">Remarks</span><span class="sxs-lookup"><span data-stu-id="2092f-139">Remarks</span></span>  
 <span data-ttu-id="2092f-140">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="2092f-140">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="2092f-141">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="2092f-141">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="2092f-142">Это требование представлено в политике безопасности.</span><span class="sxs-lookup"><span data-stu-id="2092f-142">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="2092f-143">Когда клиент запрашивает учетные данные в федеративной службе (например, CardSpace), требования помещаются в запрос маркера (RequestSecurityToken), что позволяет федеративной службе выдать учетные данные, полностью отвечающие требованиям.</span><span class="sxs-lookup"><span data-stu-id="2092f-143">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2092f-144">Пример</span><span class="sxs-lookup"><span data-stu-id="2092f-144">Example</span></span>  
 <span data-ttu-id="2092f-145">Следующая конфигурация добавляет два требования типа утверждения к привязке безопасности.</span><span class="sxs-lookup"><span data-stu-id="2092f-145">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
```xml  
<bindings>
  <wsFederationHttpBinding>
    <binding name="myFederatedBinding">
      <security mode="Message">
        <message issuedTokenType="urn:oasis:names:tc:SAML:1.0:assertion">
          <claimTypeRequirements>
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/EmailAddress" />
            <add claimType="http://schemas.microsoft.com/ws/2005/05/identity/claims/UserName"
                 optional="true" />
          </claimTypeRequirements>
        </message>
      </security>
    </binding>
  </wsFederationHttpBinding>
</bindings>
```  
  
## <a name="see-also"></a><span data-ttu-id="2092f-146">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="2092f-146">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="2092f-147">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="2092f-147">\<claimTypeRequirements></span></span>](claimtyperequirements-element.md)
- [<span data-ttu-id="2092f-148">Привязки</span><span class="sxs-lookup"><span data-stu-id="2092f-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2092f-149">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="2092f-149">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="2092f-150">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="2092f-150">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="2092f-151">\<обычайОбязательный></span><span class="sxs-lookup"><span data-stu-id="2092f-151">\<customBinding></span></span>](custombinding.md)
- [<span data-ttu-id="2092f-152">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="2092f-152">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="2092f-153">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="2092f-153">Custom Binding Security</span></span>](../../../wcf/samples/custom-binding-security.md)
