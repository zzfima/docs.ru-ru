---
title: '&lt;add&gt; элемента &lt;claimTypeRequirements&gt;'
ms.date: 03/30/2017
ms.assetid: 3234cd45-1478-468e-8b19-5c50815c4786
ms.openlocfilehash: 7f86073d0ecce353c63f31fd28c4bfeffb2411ed
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2019
ms.locfileid: "54145553"
---
# <a name="ltaddgt-of-ltclaimtyperequirementsgt-element"></a><span data-ttu-id="9daec-102">&lt;add&gt; элемента &lt;claimTypeRequirements&gt;</span><span class="sxs-lookup"><span data-stu-id="9daec-102">&lt;add&gt; of &lt;claimTypeRequirements&gt; element</span></span>
<span data-ttu-id="9daec-103">Задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="9daec-103">Specifies the types of required and optional claims expected to appear in the federated credential.</span></span> <span data-ttu-id="9daec-104">Например, службы предъявляют требования к входящим учетным данным, которые должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="9daec-104">For example, services state the requirements on incoming credentials, which must possess a certain set of claim types.</span></span>  
  
 <span data-ttu-id="9daec-105">\<система. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="9daec-105">\<system.ServiceModel></span></span>  
<span data-ttu-id="9daec-106">\<привязки ></span><span class="sxs-lookup"><span data-stu-id="9daec-106">\<bindings></span></span>  
<span data-ttu-id="9daec-107">\<wsFederatedBinding ></span><span class="sxs-lookup"><span data-stu-id="9daec-107">\<wsFederatedBinding></span></span>  
<span data-ttu-id="9daec-108">\<Привязка ></span><span class="sxs-lookup"><span data-stu-id="9daec-108">\<binding></span></span>  
<span data-ttu-id="9daec-109">\<Безопасность ></span><span class="sxs-lookup"><span data-stu-id="9daec-109">\<security></span></span>  
<span data-ttu-id="9daec-110">\<сообщение ></span><span class="sxs-lookup"><span data-stu-id="9daec-110">\<message></span></span>  
<span data-ttu-id="9daec-111">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="9daec-111">\<claimTypeRequirements></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9daec-112">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="9daec-112">Syntax</span></span>  
  
```xml  
<claimTypeRequirements>
  <add claimType="URI"
       isOptional="Boolean" />
</claimTypeRequirements>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9daec-113">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="9daec-113">Attributes and Elements</span></span>  
 <span data-ttu-id="9daec-114">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="9daec-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9daec-115">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="9daec-115">Attributes</span></span>  
  
|<span data-ttu-id="9daec-116">Атрибут</span><span class="sxs-lookup"><span data-stu-id="9daec-116">Attribute</span></span>|<span data-ttu-id="9daec-117">Описание</span><span class="sxs-lookup"><span data-stu-id="9daec-117">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9daec-118">claimType</span><span class="sxs-lookup"><span data-stu-id="9daec-118">claimType</span></span>|<span data-ttu-id="9daec-119">Универсальный код ресурса (URI), определяющий тип утверждения.</span><span class="sxs-lookup"><span data-stu-id="9daec-119">A URI that defines the type of a claim.</span></span> <span data-ttu-id="9daec-120">Например, для приобретения товара с веб-узла пользователь должен представить действительную кредитную карту с достаточным кредитным лимитом.</span><span class="sxs-lookup"><span data-stu-id="9daec-120">For example, to purchase a product from a Web site, the user must present a valid credit card with sufficient credit limit.</span></span> <span data-ttu-id="9daec-121">Типом утверждения будет универсальный код ресурса (URI) кредитной карты.</span><span class="sxs-lookup"><span data-stu-id="9daec-121">The claim type would be the credit card URI.</span></span>|  
|<span data-ttu-id="9daec-122">isOptional</span><span class="sxs-lookup"><span data-stu-id="9daec-122">isOptional</span></span>|<span data-ttu-id="9daec-123">Логическое значение, указывающее, является ли утверждение необязательным.</span><span class="sxs-lookup"><span data-stu-id="9daec-123">A Boolean value that specifies if this is for an optional claim.</span></span> <span data-ttu-id="9daec-124">Если утверждение является обязательным, установите для этого атрибута значение `false`.</span><span class="sxs-lookup"><span data-stu-id="9daec-124">Set this attribute to `false` if this is a required claim.</span></span><br /><br /> <span data-ttu-id="9daec-125">Этот атрибут можно использовать, если служба запрашивает определенные данные, но они не являются необходимыми.</span><span class="sxs-lookup"><span data-stu-id="9daec-125">You can use this attribute when the service asks for some information but does not require it.</span></span> <span data-ttu-id="9daec-126">Например, если требуется, чтобы пользователь ввел имя, фамилию и адрес, а указание номера телефона является необязательным.</span><span class="sxs-lookup"><span data-stu-id="9daec-126">For example, if you require the user to enter his/her first name, last name and address, but decide that phone number is optional.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9daec-127">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="9daec-127">Child Elements</span></span>  
 <span data-ttu-id="9daec-128">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="9daec-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9daec-129">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="9daec-129">Parent Elements</span></span>  
  
|<span data-ttu-id="9daec-130">Элемент</span><span class="sxs-lookup"><span data-stu-id="9daec-130">Element</span></span>|<span data-ttu-id="9daec-131">Описание</span><span class="sxs-lookup"><span data-stu-id="9daec-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9daec-132">\<claimTypeRequirements ></span><span class="sxs-lookup"><span data-stu-id="9daec-132">\<claimTypeRequirements></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/claimtyperequirements-for-message.md)|<span data-ttu-id="9daec-133">Задает коллекцию обязательных типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="9daec-133">Specifies a collection of required claim types.</span></span> <span data-ttu-id="9daec-134">Каждый элемент имеет тип <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span><span class="sxs-lookup"><span data-stu-id="9daec-134">Each element is of type <xref:System.ServiceModel.Configuration.ClaimTypeElement>.</span></span><br /><br /> <span data-ttu-id="9daec-135">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="9daec-135">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="9daec-136">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="9daec-136">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="9daec-137">Каждый элемент в этой коллекции задает типы обязательных и необязательных утверждений, которые могут появляться в федеративных учетных данных.</span><span class="sxs-lookup"><span data-stu-id="9daec-137">Each element in this collection specifies the types of required and optional claims expected to appear in a federated credential.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9daec-138">Примечания</span><span class="sxs-lookup"><span data-stu-id="9daec-138">Remarks</span></span>  
 <span data-ttu-id="9daec-139">В федеративном сценарии службы предъявляют требования к входящим учетным данным.</span><span class="sxs-lookup"><span data-stu-id="9daec-139">In a federated scenario, services state the requirements on incoming credentials.</span></span> <span data-ttu-id="9daec-140">Например, входящие учетные данные должны обладать определенным набором типов утверждений.</span><span class="sxs-lookup"><span data-stu-id="9daec-140">For example, the incoming credentials must possess a certain set of claim types.</span></span> <span data-ttu-id="9daec-141">Это требование представлено в политике безопасности.</span><span class="sxs-lookup"><span data-stu-id="9daec-141">This requirement is manifested in a security policy.</span></span> <span data-ttu-id="9daec-142">Когда клиент запрашивает учетные данные в федеративной службе (например, CardSpace), требования помещаются в запрос маркера (RequestSecurityToken), что позволяет федеративной службе выдать учетные данные, полностью отвечающие требованиям.</span><span class="sxs-lookup"><span data-stu-id="9daec-142">When a client requests credentials from a federated service (for example, CardSpace), it puts the requirements into a token request (RequestSecurityToken) so that the federated service can issue the credentials that satisfy the requirements accordingly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9daec-143">Пример</span><span class="sxs-lookup"><span data-stu-id="9daec-143">Example</span></span>  
 <span data-ttu-id="9daec-144">Следующая конфигурация добавляет два требования типа утверждения к привязке безопасности.</span><span class="sxs-lookup"><span data-stu-id="9daec-144">The following configuration adds two claim type requirements to a security binding.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="9daec-145">См. также</span><span class="sxs-lookup"><span data-stu-id="9daec-145">See Also</span></span>  
 <xref:System.ServiceModel.FederatedMessageSecurityOverHttp.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Security.Tokens.ClaimTypeRequirement>  
 <xref:System.ServiceModel.Configuration.FederatedMessageSecurityOverHttpElement.ClaimTypeRequirements%2A>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElementCollection>  
 <xref:System.ServiceModel.Configuration.ClaimTypeElement>
