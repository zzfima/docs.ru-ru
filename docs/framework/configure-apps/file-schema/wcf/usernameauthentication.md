---
title: '&lt;UserNameAuthentication&gt;'
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 1b8a85a3b2699aa88db24d1f7afee3de67dbf39b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/23/2019
ms.locfileid: "54656652"
---
# <a name="ltusernameauthenticationgt"></a><span data-ttu-id="27261-102">&lt;UserNameAuthentication&gt;</span><span class="sxs-lookup"><span data-stu-id="27261-102">&lt;userNameAuthentication&gt;</span></span>
<span data-ttu-id="27261-103">Задает учетные данные службы, основанные на имени пользователя и пароле.</span><span class="sxs-lookup"><span data-stu-id="27261-103">Specifies a service's credentials based on user name and password.</span></span>  
  
 <span data-ttu-id="27261-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="27261-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="27261-105">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="27261-105">\<behaviors></span></span>  
<span data-ttu-id="27261-106">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="27261-106">\<serviceBehaviors></span></span>  
<span data-ttu-id="27261-107">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="27261-107">\<behavior></span></span>  
<span data-ttu-id="27261-108">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="27261-108">\<serviceCredentials></span></span>  
<span data-ttu-id="27261-109">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="27261-109">\<userNameAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27261-110">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="27261-110">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="27261-111">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="27261-111">Attributes and Elements</span></span>  
 <span data-ttu-id="27261-112">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="27261-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="27261-113">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="27261-113">Attributes</span></span>  
  
|<span data-ttu-id="27261-114">Атрибут</span><span class="sxs-lookup"><span data-stu-id="27261-114">Attribute</span></span>|<span data-ttu-id="27261-115">Описание</span><span class="sxs-lookup"><span data-stu-id="27261-115">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="27261-116">Объект <xref:System.TimeSpan>, определяющий максимальный срок кэширования маркера.</span><span class="sxs-lookup"><span data-stu-id="27261-116">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="27261-117">Значение по умолчанию - 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="27261-117">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="27261-118">Логическое значение, которое указывает, кэшируются ли маркеры входа.</span><span class="sxs-lookup"><span data-stu-id="27261-118">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="27261-119">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="27261-119">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="27261-120">Строка, указывающая тип настраиваемого проверяющего элемента управления для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="27261-120">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="27261-121">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="27261-121">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="27261-122">Логическое значение, указывающее, включаются ли группы Windows в контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="27261-122">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="27261-123">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="27261-123">The default is `true`.</span></span><br /><br /> <span data-ttu-id="27261-124">Установка для этого атрибута значения `true` влияет на производительность, поскольку приводит к расширению всей группы.</span><span class="sxs-lookup"><span data-stu-id="27261-124">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="27261-125">Если нет необходимости устанавливать список групп, которым принадлежит пользователь, установите значение `false`.</span><span class="sxs-lookup"><span data-stu-id="27261-125">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="27261-126">Целое число, указывающее максимальное количество маркеров входа для кэширования.</span><span class="sxs-lookup"><span data-stu-id="27261-126">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="27261-127">Значение должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="27261-127">This value should be larger than zero.</span></span> <span data-ttu-id="27261-128">Значение по умолчанию — 128.</span><span class="sxs-lookup"><span data-stu-id="27261-128">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="27261-129">Если атрибуту `clientCredentialType` привязки задано значение `username`, имя пользователя сопоставляется с учетными записями Windows.</span><span class="sxs-lookup"><span data-stu-id="27261-129">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="27261-130">Такое поведение можно переопределить с помощью этого атрибута, который является строкой, содержащей имя значения <xref:System.Web.Security.MembershipProvider>, предоставляющего соответствующий механизм проверки пароля.</span><span class="sxs-lookup"><span data-stu-id="27261-130">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="27261-131">Указывает способ проверки пароля.</span><span class="sxs-lookup"><span data-stu-id="27261-131">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="27261-132">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="27261-132">Valid values are:</span></span><br /><br /> <span data-ttu-id="27261-133">— Windows</span><span class="sxs-lookup"><span data-stu-id="27261-133">-   Windows</span></span><br /><span data-ttu-id="27261-134">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="27261-134">-   MembershipProvider</span></span><br /><span data-ttu-id="27261-135">-Custom</span><span class="sxs-lookup"><span data-stu-id="27261-135">-   Custom</span></span><br /><br /> <span data-ttu-id="27261-136">По умолчанию используется Windows.</span><span class="sxs-lookup"><span data-stu-id="27261-136">The default is Windows.</span></span> <span data-ttu-id="27261-137">Это атрибут типа <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="27261-137">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="27261-138">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="27261-138">Child Elements</span></span>  
 <span data-ttu-id="27261-139">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="27261-139">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="27261-140">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="27261-140">Parent Elements</span></span>  
  
|<span data-ttu-id="27261-141">Элемент</span><span class="sxs-lookup"><span data-stu-id="27261-141">Element</span></span>|<span data-ttu-id="27261-142">Описание</span><span class="sxs-lookup"><span data-stu-id="27261-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="27261-143">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="27261-143">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="27261-144">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="27261-144">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27261-145">Примечания</span><span class="sxs-lookup"><span data-stu-id="27261-145">Remarks</span></span>  
 <span data-ttu-id="27261-146">Если ни одна из используемых службой привязок не настроена для проверки подлинности на основании имени пользователя и пароля, атрибуты этого элемента пропускаются.</span><span class="sxs-lookup"><span data-stu-id="27261-146">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="27261-147">К ним относятся `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` и `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="27261-147">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="27261-148">Если ни одна из используемых службой привязок не настроена на использование проверки подлинности Windows для имени и пароля пользователя, параметры, относящиеся к кэшированию маркеров входа, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="27261-148">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="27261-149">К ним относятся `cacheLogonTokenLifetime`, `cacheLogonTokens` и `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="27261-149">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27261-150">См. также</span><span class="sxs-lookup"><span data-stu-id="27261-150">See also</span></span>
- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
