---
title: <add> из <claimTypeRequirements>
ms.date: 03/30/2017
ms.assetid: c68e83c9-39e8-4264-b1ce-b6a9eb5b98aa
ms.openlocfilehash: 97d3ecca369aeffb7b2e8464f385eeae13bd470f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704483"
---
# <a name="add-of-claimtyperequirements"></a><span data-ttu-id="b403e-102">\<Добавить > из \<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="b403e-102">\<add> of \<claimTypeRequirements></span></span>
<span data-ttu-id="b403e-103">Задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="b403e-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="b403e-104">Например, службы предъявляют требования к входящим учетным данным, которые должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="b403e-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="b403e-105">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="b403e-105">\<system.serviceModel></span></span>  
<span data-ttu-id="b403e-106">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="b403e-106">\<bindings></span></span>  
<span data-ttu-id="b403e-107">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b403e-107">\<customBinding></span></span>  
<span data-ttu-id="b403e-108">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="b403e-108">\<binding></span></span>  
<span data-ttu-id="b403e-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="b403e-109">\<security></span></span>  
<span data-ttu-id="b403e-110">\<issuedTokenParameters></span><span class="sxs-lookup"><span data-stu-id="b403e-110">\<issuedTokenParameters></span></span>  
<span data-ttu-id="b403e-111">\<claimTypeRequirements></span><span class="sxs-lookup"><span data-stu-id="b403e-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b403e-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="b403e-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b403e-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="b403e-113">Attributes and Elements</span></span>  
 <span data-ttu-id="b403e-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="b403e-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b403e-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="b403e-115">Attributes</span></span>  
  
|<span data-ttu-id="b403e-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="b403e-116">Attribute</span></span>|<span data-ttu-id="b403e-117">Описание</span><span class="sxs-lookup"><span data-stu-id="b403e-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b403e-118">claimType</span><span class="sxs-lookup"><span data-stu-id="b403e-118">claimType</span></span>|<span data-ttu-id="b403e-119">Универсальный код ресурса (URI), определяющий тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="b403e-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="b403e-120">Например, для приобретения товара с веб-узла пользователь должен представить действительную кредитную карту с достаточным кредитным лимитом.</span><span class="sxs-lookup"><span data-stu-id="b403e-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="b403e-121">Типом утверждения будет универсальный код ресурса (URI) кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="b403e-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="b403e-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="b403e-122">isOptional</span></span>|<span data-ttu-id="b403e-123">Логическое значение, указывающее, является ли утверждение необязательным.</span><span class="sxs-lookup"><span data-stu-id="b403e-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="b403e-124">Если утверждение является обязательным, установите для этого атрибута значение `false`.</span><span class="sxs-lookup"><span data-stu-id="b403e-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="b403e-125">Этот атрибут можно использовать, если служба запрашивает определенные данные, но они не являются необходимыми.</span><span class="sxs-lookup"><span data-stu-id="b403e-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="b403e-126">Например, если требуется, чтобы пользователь ввел имя, фамилию и адрес, а указание номера телефона является необязательным.</span><span class="sxs-lookup"><span data-stu-id="b403e-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b403e-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="b403e-127">Child Elements</span></span>  
 <span data-ttu-id="b403e-128">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="b403e-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b403e-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="b403e-129">Parent Elements</span></span>  
  
|<span data-ttu-id="b403e-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="b403e-130">Element</span></span>|<span data-ttu-id="b403e-131">Описание</span><span class="sxs-lookup"><span data-stu-id="b403e-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b403e-132">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="b403e-132">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)|<span data-ttu-id="b403e-133">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="b403e-133">Specifies a collection of required claim types.</span></span><br /><br /> <span data-ttu-id="b403e-134">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="b403e-134">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="b403e-135">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="b403e-135">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="b403e-136">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="b403e-136">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b403e-137">Примечания</span><span class="sxs-lookup"><span data-stu-id="b403e-137">Remarks</span></span>  
 <span data-ttu-id="b403e-138">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="b403e-138">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="b403e-139">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="b403e-139">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="b403e-140">Это требование представлено в политике безопасности.</span><span class="sxs-lookup"><span data-stu-id="b403e-140">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="b403e-141">Когда клиент запрашивает учетные данные в федеративной службе (например, CardSpace), требования помещаются в запрос маркера (RequestSecurityToken), что позволяет федеративной службе выдать учетные данные, полностью отвечающие требованиям.</span><span class="sxs-lookup"><span data-stu-id="b403e-141">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b403e-142">Пример</span><span class="sxs-lookup"><span data-stu-id="b403e-142">Example</span></span>  
 <span data-ttu-id="b403e-143">Следующая конфигурация добавляет два требования типа утверждения к привязке безопасности.</span><span class="sxs-lookup"><span data-stu-id="b403e-143">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="b403e-144">См. также</span><span class="sxs-lookup"><span data-stu-id="b403e-144">See also</span></span>

- <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>
- <xref:System.ServiceModel.Security.Tokens.IssuedSecurityTokenParameters.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement.ClaimTypeRequirements%2A>
- <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>
- <xref:System.ServiceModel.Configuration.ClaimTypeElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="b403e-145">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="b403e-145">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-element.md)
- [<span data-ttu-id="b403e-146">Привязки</span><span class="sxs-lookup"><span data-stu-id="b403e-146">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="b403e-147">Расширение привязок</span><span class="sxs-lookup"><span data-stu-id="b403e-147">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="b403e-148">Пользовательские привязки</span><span class="sxs-lookup"><span data-stu-id="b403e-148">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="b403e-149">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="b403e-149">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
- [<span data-ttu-id="b403e-150">Практическое руководство. Создание пользовательской привязки с использованием элемента SecurityBindingElement</span><span class="sxs-lookup"><span data-stu-id="b403e-150">How to: Create a Custom Binding Using the SecurityBindingElement</span></span>](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)
- [<span data-ttu-id="b403e-151">Безопасность пользовательской привязки</span><span class="sxs-lookup"><span data-stu-id="b403e-151">Custom Binding Security</span></span>](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
