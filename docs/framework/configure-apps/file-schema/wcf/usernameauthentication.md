---
title: <userNameAuthentication>
ms.date: 03/30/2017
ms.assetid: 24d8b398-770f-418f-ba23-c4325419cfa6
ms.openlocfilehash: 5a4cf8d429198b889f2bb362294ba3841c814b26
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083150"
---
# <a name="usernameauthentication"></a><span data-ttu-id="dde7a-101">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="dde7a-101">\<userNameAuthentication></span></span>
<span data-ttu-id="dde7a-102">Задает учетные данные службы, основанные на имени пользователя и пароле.</span><span class="sxs-lookup"><span data-stu-id="dde7a-102">Specifies a service's credentials based on user name and password.</span></span>  
  
 <span data-ttu-id="dde7a-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dde7a-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="dde7a-104">\<варианты поведения ></span><span class="sxs-lookup"><span data-stu-id="dde7a-104">\<behaviors></span></span>  
<span data-ttu-id="dde7a-105">\<serviceBehaviors ></span><span class="sxs-lookup"><span data-stu-id="dde7a-105">\<serviceBehaviors></span></span>  
<span data-ttu-id="dde7a-106">\<поведение ></span><span class="sxs-lookup"><span data-stu-id="dde7a-106">\<behavior></span></span>  
<span data-ttu-id="dde7a-107">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="dde7a-107">\<serviceCredentials></span></span>  
<span data-ttu-id="dde7a-108">\<userNameAuthentication></span><span class="sxs-lookup"><span data-stu-id="dde7a-108">\<userNameAuthentication></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dde7a-109">Синтаксис</span><span class="sxs-lookup"><span data-stu-id="dde7a-109">Syntax</span></span>  
  
```xml  
<userNameAuthentication cacheLogonTokenLifetime="TimeSpan"
                        cacheLogonTokens="Boolean"
                        customUserNamePasswordValidatorType="String"
                        includeWindowsGroups="Boolean"
                        maxCacheLogonTokens="Integer"
                        membershipProviderName="String"
                        userNamePasswordValidationMode="Windows/MembershipProvider/Custom" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dde7a-110">Атрибуты и элементы</span><span class="sxs-lookup"><span data-stu-id="dde7a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="dde7a-111">В следующих разделах описаны атрибуты, дочерние и родительские элементы.</span><span class="sxs-lookup"><span data-stu-id="dde7a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dde7a-112">Атрибуты</span><span class="sxs-lookup"><span data-stu-id="dde7a-112">Attributes</span></span>  
  
|<span data-ttu-id="dde7a-113">Атрибут</span><span class="sxs-lookup"><span data-stu-id="dde7a-113">Attribute</span></span>|<span data-ttu-id="dde7a-114">Описание</span><span class="sxs-lookup"><span data-stu-id="dde7a-114">Description</span></span>|  
|---------------|-----------------|  
|`cacheLogonTokenLifetime`|<span data-ttu-id="dde7a-115">Объект <xref:System.TimeSpan>, определяющий максимальный срок кэширования маркера.</span><span class="sxs-lookup"><span data-stu-id="dde7a-115">A <xref:System.TimeSpan> that specifies the maximum length of time a token is cached.</span></span> <span data-ttu-id="dde7a-116">Значение по умолчанию - 00:15:00.</span><span class="sxs-lookup"><span data-stu-id="dde7a-116">The default is 00:15:00.</span></span>|  
|`cacheLogonTokens`|<span data-ttu-id="dde7a-117">Логическое значение, которое указывает, кэшируются ли маркеры входа.</span><span class="sxs-lookup"><span data-stu-id="dde7a-117">A Boolean value that specifies whether logon tokens are cached.</span></span> <span data-ttu-id="dde7a-118">Значение по умолчанию — `false`.</span><span class="sxs-lookup"><span data-stu-id="dde7a-118">The default is `false`.</span></span>|  
|`customUserNamePasswordValidatorType`|<span data-ttu-id="dde7a-119">Строка, указывающая тип настраиваемого проверяющего элемента управления для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="dde7a-119">A string that specifies the type of custom username password validator to be used.</span></span> <span data-ttu-id="dde7a-120">Значение по умолчанию - пустая строка.</span><span class="sxs-lookup"><span data-stu-id="dde7a-120">The default is an empty string.</span></span>|  
|`includeWindowsGroups`|<span data-ttu-id="dde7a-121">Логическое значение, указывающее, включаются ли группы Windows в контекст безопасности.</span><span class="sxs-lookup"><span data-stu-id="dde7a-121">A Boolean value that specifies whether Windows groups are included in the security context.</span></span> <span data-ttu-id="dde7a-122">Значение по умолчанию — `true`.</span><span class="sxs-lookup"><span data-stu-id="dde7a-122">The default is `true`.</span></span><br /><br /> <span data-ttu-id="dde7a-123">Установка для этого атрибута значения `true` влияет на производительность, поскольку приводит к расширению всей группы.</span><span class="sxs-lookup"><span data-stu-id="dde7a-123">Setting this attribute to `true` has a performance impact as it results in a full-group expansion.</span></span> <span data-ttu-id="dde7a-124">Если нет необходимости устанавливать список групп, которым принадлежит пользователь, установите значение `false`.</span><span class="sxs-lookup"><span data-stu-id="dde7a-124">Set this property to `false` if you do not need to establish the list of groups a user belongs to.</span></span>|  
|`maxCacheLogonTokens`|<span data-ttu-id="dde7a-125">Целое число, указывающее максимальное количество маркеров входа для кэширования.</span><span class="sxs-lookup"><span data-stu-id="dde7a-125">An integer that specifies the maximum number of logon tokens to cache.</span></span> <span data-ttu-id="dde7a-126">Значение должно быть больше нуля.</span><span class="sxs-lookup"><span data-stu-id="dde7a-126">This value should be larger than zero.</span></span> <span data-ttu-id="dde7a-127">Значение по умолчанию — 128.</span><span class="sxs-lookup"><span data-stu-id="dde7a-127">The default is 128.</span></span>|  
|`membershipProviderName`|<span data-ttu-id="dde7a-128">Если атрибуту `clientCredentialType` привязки задано значение `username`, имя пользователя сопоставляется с учетными записями Windows.</span><span class="sxs-lookup"><span data-stu-id="dde7a-128">When the `clientCredentialType` attribute of a binding is set to `username`, the username is mapped to Windows accounts.</span></span> <span data-ttu-id="dde7a-129">Такое поведение можно переопределить с помощью этого атрибута, который является строкой, содержащей имя значения <xref:System.Web.Security.MembershipProvider>, предоставляющего соответствующий механизм проверки пароля.</span><span class="sxs-lookup"><span data-stu-id="dde7a-129">You can override this behavior using this attribute, which is a string that contains the name of the <xref:System.Web.Security.MembershipProvider> value that provides the relevant password validation mechanism.</span></span>|  
|`userNamePasswordValidationMode`|<span data-ttu-id="dde7a-130">Указывает способ проверки пароля.</span><span class="sxs-lookup"><span data-stu-id="dde7a-130">Specifies the manner in which username password is validated.</span></span> <span data-ttu-id="dde7a-131">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="dde7a-131">Valid values are:</span></span><br /><br /> <span data-ttu-id="dde7a-132">— Windows</span><span class="sxs-lookup"><span data-stu-id="dde7a-132">-   Windows</span></span><br /><span data-ttu-id="dde7a-133">-MembershipProvider</span><span class="sxs-lookup"><span data-stu-id="dde7a-133">-   MembershipProvider</span></span><br /><span data-ttu-id="dde7a-134">-Custom</span><span class="sxs-lookup"><span data-stu-id="dde7a-134">-   Custom</span></span><br /><br /> <span data-ttu-id="dde7a-135">По умолчанию используется Windows.</span><span class="sxs-lookup"><span data-stu-id="dde7a-135">The default is Windows.</span></span> <span data-ttu-id="dde7a-136">Это атрибут типа <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span><span class="sxs-lookup"><span data-stu-id="dde7a-136">This attribute is of type <xref:System.ServiceModel.Security.UserNamePasswordValidationMode>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="dde7a-137">Дочерние элементы</span><span class="sxs-lookup"><span data-stu-id="dde7a-137">Child Elements</span></span>  
 <span data-ttu-id="dde7a-138">Отсутствует.</span><span class="sxs-lookup"><span data-stu-id="dde7a-138">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dde7a-139">Родительские элементы</span><span class="sxs-lookup"><span data-stu-id="dde7a-139">Parent Elements</span></span>  
  
|<span data-ttu-id="dde7a-140">Элемент</span><span class="sxs-lookup"><span data-stu-id="dde7a-140">Element</span></span>|<span data-ttu-id="dde7a-141">Описание</span><span class="sxs-lookup"><span data-stu-id="dde7a-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dde7a-142">\<serviceCredentials ></span><span class="sxs-lookup"><span data-stu-id="dde7a-142">\<serviceCredentials></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)|<span data-ttu-id="dde7a-143">Задает учетные данные, используемые при проверке подлинности службы, а также параметры, относящиеся к проверке учетных данных клиента.</span><span class="sxs-lookup"><span data-stu-id="dde7a-143">Specifies the credential to be used in authenticating the service, and the client credential validation related settings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dde7a-144">Примечания</span><span class="sxs-lookup"><span data-stu-id="dde7a-144">Remarks</span></span>  
 <span data-ttu-id="dde7a-145">Если ни одна из используемых службой привязок не настроена для проверки подлинности на основании имени пользователя и пароля, атрибуты этого элемента пропускаются.</span><span class="sxs-lookup"><span data-stu-id="dde7a-145">If none of the bindings used by a service is configured for user name/password-based authentication, the attributes for this element are ignored.</span></span> <span data-ttu-id="dde7a-146">К ним относятся `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName` и `userNamePasswordValidationMode`.</span><span class="sxs-lookup"><span data-stu-id="dde7a-146">These include `customUserNamePasswordValidatorType`, `includeWindowsGroups`, `membershipProviderName`, and `userNamePasswordValidationMode`.</span></span>  
  
 <span data-ttu-id="dde7a-147">Если ни одна из используемых службой привязок не настроена на использование проверки подлинности Windows для имени и пароля пользователя, параметры, относящиеся к кэшированию маркеров входа, пропускаются.</span><span class="sxs-lookup"><span data-stu-id="dde7a-147">If none of the bindings used by a service is configured to use Windows authentication for user name/password, the settings related to caching of logon tokens are ignored.</span></span> <span data-ttu-id="dde7a-148">К ним относятся `cacheLogonTokenLifetime`, `cacheLogonTokens` и `maxCacheLogonTokens`.</span><span class="sxs-lookup"><span data-stu-id="dde7a-148">These include the `cacheLogonTokenLifetime`, `cacheLogonTokens`, and `maxCacheLogonTokens`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dde7a-149">См. также</span><span class="sxs-lookup"><span data-stu-id="dde7a-149">See also</span></span>

- <xref:System.ServiceModel.Configuration.UserNameServiceElement>
- <xref:System.ServiceModel.Description.ServiceCredentials.UserNameAuthentication%2A>
- <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential>
- <xref:System.ServiceModel.Configuration.ServiceCredentialsElement.UserNameAuthentication%2A>
