---
title: Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF, username and password
ms.assetid: 8e08b74b-fa44-4018-b63d-0d0805f85e3f
ms.openlocfilehash: 7df6ec57204990066ce59700e5c2582701f2a81a
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/27/2019
ms.locfileid: "70045914"
---
# <a name="how-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="d2ef1-102">Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="d2ef1-102">How to: Use a Custom User Name and Password Validator</span></span>

<span data-ttu-id="d2ef1-103">По умолчанию, если для проверки подлинности используется имя пользователя и пароль, Windows Communication Foundation (WCF) использует Windows для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-103">By default, when a user name and password is used for authentication, Windows Communication Foundation (WCF) uses Windows to validate the user name and password.</span></span> <span data-ttu-id="d2ef1-104">Однако WCF позволяет создавать пользовательские схемы проверки подлинности имени пользователя и пароля, которыетакже называются проверяющими.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-104">However, WCF allows for custom user name and password authentication schemes, also known as *validators*.</span></span> <span data-ttu-id="d2ef1-105">Чтобы внедрить пользовательский проверяющий элемент управления для проверки подлинности имени пользователя и пароля, необходимо создать класс, унаследованный от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>, и настроить его.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-105">To incorporate a custom user name and password validator, create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator> and then configure it.</span></span>

<span data-ttu-id="d2ef1-106">Пример приложения см. в разделе [средство проверки пароля для имени пользователя](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span><span class="sxs-lookup"><span data-stu-id="d2ef1-106">For a sample application, see [User Name Password Validator](../../../../docs/framework/wcf/samples/user-name-password-validator.md).</span></span>

### <a name="to-create-a-custom-user-name-and-password-validator"></a><span data-ttu-id="d2ef1-107">Создание пользовательского проверяющего элемента управления для имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="d2ef1-107">To create a custom user name and password validator</span></span>

1. <span data-ttu-id="d2ef1-108">Создайте класс, наследующий от класса <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-108">Create a class that derives from <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#3)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#3)]

2. <span data-ttu-id="d2ef1-109">Реализуйте пользовательскую схему проверки подлинности, переопределив метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-109">Implement the custom authentication scheme by overriding the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    <span data-ttu-id="d2ef1-110">Не используйте код следующего примера, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-110">Do not use the code in the following example that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="d2ef1-111">Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-111">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

    <span data-ttu-id="d2ef1-112">Чтобы вернуть ошибки проверки подлинности клиенту, создайте исключение <xref:System.ServiceModel.FaultException> в методе <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-112">To return authentication errors back to the client, throw a <xref:System.ServiceModel.FaultException> in the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method.</span></span>

    [!code-csharp[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#4)]
    [!code-vb[C_CustomUsernameAndPasswordValidator#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#4)]

### <a name="to-configure-a-service-to-use-a-custom-user-name-and-password-validator"></a><span data-ttu-id="d2ef1-113">Настройка службы для использования пользовательского проверяющего элемента управления для проверки имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="d2ef1-113">To configure a service to use a custom user name and password validator</span></span>

1. <span data-ttu-id="d2ef1-114">Настройте привязку, использующую безопасность сообщений с любым транспортом или безопасность на уровне транспорта по HTTP(S).</span><span class="sxs-lookup"><span data-stu-id="d2ef1-114">Configure a binding that uses message security over any transport or transport-level security over HTTP(S).</span></span>

    <span data-ttu-id="d2ef1-115">При использовании безопасности сообщений добавьте одну из предоставляемых системой привязок, например [ \<WSHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), или `UserName` [ \<> CustomBinding](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) , который поддерживает безопасность сообщений и тип учетных данных.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-115">When using message security, add one of the system-provided bindings, such as a  [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that supports message security and the `UserName` credential type.</span></span>

    <span data-ttu-id="d2ef1-116">При использовании безопасности на транспортном уровне через HTTP (S) добавьте [ \<> WSHttpBinding](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) или [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) [ \<BasicHttpBinding >, NetTcpBinding > или CustomBinding > ](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md), использующий HTTP (S) `Basic` и схему проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-116">When using transport-level security over HTTP(S), add either the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md), a [\<netTcpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) or a [\<customBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) that uses HTTP(S) and the `Basic` authentication scheme.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2ef1-117">Если используется платформа [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] или более поздняя версия, на уровне безопасности сообщений и транспорта можно применять пользовательский модуль проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-117">When [!INCLUDE[netfx35_long](../../../../includes/netfx35-long-md.md)] or later is used, you can use a custom username and password validator with message and transport security.</span></span> <span data-ttu-id="d2ef1-118">С помощью WinFX пользовательское средство проверки имени пользователя и пароля может использоваться только с защитой сообщений.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-118">With WinFX, a custom username and password validator can only be used with message security.</span></span>

    > [!TIP]
    > <span data-ttu-id="d2ef1-119">Дополнительные сведения об использовании \<> NetTcpBinding в этом контексте см. в разделе [ \<безопасность >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="d2ef1-119">For more information on using \<netTcpBinding> in this context, see [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)</span></span>

    1. <span data-ttu-id="d2ef1-120">В файле [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) конфигурации [ в\<](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элементе System. ServiceModel > Добавьте привязки > элемент.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-120">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>

    2. <span data-ttu-id="d2ef1-121">Добавьте элемент привязки [ \<WSHttpBinding > или BasicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) в раздел привязок. [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="d2ef1-121">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) or [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) element to the bindings section.</span></span> <span data-ttu-id="d2ef1-122">Дополнительные сведения о создании элемента привязки WCF см. в разделе [как Укажите привязку службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="d2ef1-122">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>

    3. <span data-ttu-id="d2ef1-123">Задайтедля`Message` [атрибута > \<безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) или [ \<> безопасности](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) значение, `Transport`или .`TransportWithMessageCredential` `mode`</span><span class="sxs-lookup"><span data-stu-id="d2ef1-123">Set the `mode` attribute of the [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md) or [\<security>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md) to `Message`, `Transport`, or `TransportWithMessageCredential`.</span></span>

    4. <span data-ttu-id="d2ef1-124">`clientCredentialType` Задайте атрибут [ >сообщенияилитранспортного>.\<](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="d2ef1-124">Set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md).</span></span>

        <span data-ttu-id="d2ef1-125">При использовании безопасности сообщений задайте `clientCredentialType` атрибуту [ \<сообщения >](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) `UserName`значение.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-125">When using message security, set the `clientCredentialType` attribute of the [\<message>](../../../../docs/framework/configure-apps/file-schema/wcf/message-of-wshttpbinding.md) to `UserName`.</span></span>

        <span data-ttu-id="d2ef1-126">При использовании безопасности на транспортном уровне через HTTP (S) задайте `clientCredentialType` для `Basic`атрибута [ \<> транспорта](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) или [ \<транспортного >](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) значение.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-126">When using transport-level security over HTTP(S), set the `clientCredentialType` attribute of the [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-wshttpbinding.md) or [\<transport>](../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-basichttpbinding.md) to `Basic`.</span></span>

        > [!NOTE]
        > <span data-ttu-id="d2ef1-127">Если служба WCF размещается в службы IIS (IIS) с использованием безопасности на транспортном <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> уровне <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, а свойство имеет значение, настраиваемая схема проверки подлинности использует подмножество проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-127">When a WCF service is hosted in Internet Information Services (IIS) using transport-level security and the <xref:System.ServiceModel.Security.UserNamePasswordServiceCredential.UserNamePasswordValidationMode%2A> property is set to <xref:System.ServiceModel.Security.UserNamePasswordValidationMode.Custom>, the custom authentication scheme uses a subset of Windows authentication.</span></span> <span data-ttu-id="d2ef1-128">Это связано с тем, что в этом случае IIS выполняет проверку подлинности Windows перед тем, как WCF вызовет настраиваемую проверку подлинности.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-128">That is because in this scenario, IIS performs Windows authentication prior to WCF invoking the custom authenticator.</span></span>

    <span data-ttu-id="d2ef1-129">Дополнительные сведения о создании элемента привязки WCF см. в разделе [как Укажите привязку службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="d2ef1-129">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>

    <span data-ttu-id="d2ef1-130">В следующем примере показан код конфигурации для привязки.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-130">The following example shows the configuration code for the binding.</span></span>

    ```xml
    <system.serviceModel>
      <bindings>
      <wsHttpBinding>
          <binding name="Binding1">
            <security mode="Message">
              <message clientCredentialType="UserName" />
            </security>
          </binding>
        </wsHttpBinding>
      </bindings>
    </system.serviceModel>
    ```

2. <span data-ttu-id="d2ef1-131">Настройте поведение, которое будет указывать, что для проверки пар имени пользователя и пароля для входящих маркеров безопасности <xref:System.IdentityModel.Tokens.UserNameSecurityToken> будет использоваться пользовательский проверяющий элемент управления.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-131">Configure a behavior that specifies that a custom user name and password validator is used to validate user name and password pairs for incoming <xref:System.IdentityModel.Tokens.UserNameSecurityToken> security tokens.</span></span>

    1. <span data-ttu-id="d2ef1-132">В качестве [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) дочернего [ \<элемента System. ServiceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) добавьте элемент Behaviors >.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-132">As a child to the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    2. <span data-ttu-id="d2ef1-133">Добавьте > serviceBehaviors в элемент [ Behaviors>\<](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) . [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="d2ef1-133">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element.</span></span>

    3. <span data-ttu-id="d2ef1-134">Добавьте элемент [Behavior > и присвойте атрибуту соответствующее значение. \<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) `name`</span><span class="sxs-lookup"><span data-stu-id="d2ef1-134">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>

    4. <span data-ttu-id="d2ef1-135">Добавьте > ServiceCredentials в элемент > [ поведения.\<](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="d2ef1-135">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-servicebehaviors.md) element.</span></span>

    5. <span data-ttu-id="d2ef1-136">Добавьте [> усернамеаусентикатион в > ServiceCredentials. \<](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) [ \<](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md)</span><span class="sxs-lookup"><span data-stu-id="d2ef1-136">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md).</span></span>

    6. <span data-ttu-id="d2ef1-137">Присвойте свойству `userNamePasswordValidationMode` значение `Custom`.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-137">Set the `userNamePasswordValidationMode` to `Custom`.</span></span>

        > [!IMPORTANT]
        > <span data-ttu-id="d2ef1-138">`userNamePasswordValidationMode` Если значение не задано, WCF использует проверку подлинности Windows вместо настраиваемого средства проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-138">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the custom user name and password validator.</span></span>

    7. <span data-ttu-id="d2ef1-139">Присвойте атрибуту `customUserNamePasswordValidatorType` значение типа вашего пользовательского проверяющего элемента управления для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-139">Set the `customUserNamePasswordValidatorType` to the type that represents your custom user name and password validator.</span></span>

    <span data-ttu-id="d2ef1-140">В следующем примере показан фрагмент `<serviceCredentials>`, иллюстрирующий вышеуказанные действия.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-140">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>

    ```xml
    <serviceCredentials>
      <userNameAuthentication userNamePasswordValidationMode="Custom" customUserNamePasswordValidatorType="Microsoft.ServiceModel.Samples.CalculatorService.CustomUserNameValidator, service" />
    </serviceCredentials>
    ```

## <a name="example"></a><span data-ttu-id="d2ef1-141">Пример</span><span class="sxs-lookup"><span data-stu-id="d2ef1-141">Example</span></span>

<span data-ttu-id="d2ef1-142">В следующем примере кода показано, как создать пользовательский проверяющий элемент управления для проверки имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-142">The following code example demonstrates how to create a custom user name and password validator.</span></span> <span data-ttu-id="d2ef1-143">Не используйте код, переопределяющий метод <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A>, в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-143">Do not use the code that overrides the <xref:System.IdentityModel.Selectors.UserNamePasswordValidator.Validate%2A> method in a production environment.</span></span> <span data-ttu-id="d2ef1-144">Замените код на свою собственную схему проверки подлинности имени пользователя и пароля, в которой может применяться извлечение пар имени пользователя и пароля из базы данных.</span><span class="sxs-lookup"><span data-stu-id="d2ef1-144">Replace the code with your custom user name and password validation scheme, which might involve retrieving user name and password pairs from a database.</span></span>

[!code-csharp[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#1)]
[!code-vb[C_CustomUsernameAndPasswordValidator#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#1)]
[!code-csharp[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_customusernameandpasswordvalidator/cs/service.cs#2)]
[!code-vb[C_CustomUsernameAndPasswordValidator#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_customusernameandpasswordvalidator/vb/service.vb#2)]

## <a name="see-also"></a><span data-ttu-id="d2ef1-145">См. также</span><span class="sxs-lookup"><span data-stu-id="d2ef1-145">See also</span></span>

- <xref:System.IdentityModel.Selectors.UserNamePasswordValidator>
- [<span data-ttu-id="d2ef1-146">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d2ef1-146">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
- [<span data-ttu-id="d2ef1-147">Authentication</span><span class="sxs-lookup"><span data-stu-id="d2ef1-147">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)
