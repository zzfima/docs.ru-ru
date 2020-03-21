---
title: Практическое руководство. Использование поставщика членства ASP.NET
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: 5b15d56c7150a8478bc32651538903778e3b877d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184797"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="679af-102">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="679af-102">How to: Use the ASP.NET Membership Provider</span></span>

<span data-ttu-id="679af-103">Поставщик ASP.NET членства — это функция, которая позволяет разработчикам ASP.NET создавать веб-сайты, позволяющие пользователям создавать уникальные комбинации имен пользователей и паролей.</span><span class="sxs-lookup"><span data-stu-id="679af-103">The ASP.NET membership provider is a feature that enables ASP.NET developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="679af-104">Эта функция позволяет любому пользователю создавать на узле учетную запись и при входе получать монопольный доступ к узлу и его службам.</span><span class="sxs-lookup"><span data-stu-id="679af-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="679af-105">В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="679af-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="679af-106">Вместо этого, любой пользователь, который поставляет свои учетные данные (комбинация имени пользователя / пароля) может использовать сайт и его услуги.</span><span class="sxs-lookup"><span data-stu-id="679af-106">Instead, any user that supplies their credentials (the user name/password combination) can use the site and its services.</span></span>

<span data-ttu-id="679af-107">Для примера приложения [см.](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)</span><span class="sxs-lookup"><span data-stu-id="679af-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="679af-108">Для получения информации об использовании функции поставщика ASP.NET роли [ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)см.</span><span class="sxs-lookup"><span data-stu-id="679af-108">For information about using the ASP.NET role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>

<span data-ttu-id="679af-109">Возможность членства требует использования базы данных SQL Server для хранения сведений о пользователе.</span><span class="sxs-lookup"><span data-stu-id="679af-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="679af-110">Эта возможность также включает методы напоминания пользователю его пароля с помощью специального вопроса.</span><span class="sxs-lookup"><span data-stu-id="679af-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>

<span data-ttu-id="679af-111">Разработчики Windows Communication Foundation (WCF) могут воспользоваться этими функциями в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="679af-111">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="679af-112">При интеграции в приложение WCF пользователи должны предоставить клиентское приложение WCF комбинацию имени пользователя/пароля.</span><span class="sxs-lookup"><span data-stu-id="679af-112">When integrated into an WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="679af-113">Для передачи данных в службу WCF используйте привязку, поддерживающую учетные данные имени пользователя/пароля, такие как <xref:System.ServiceModel.WSHttpBinding> (в конфигурации, [ \<wsHttpBinding>) ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)и установите тип учетных данных `UserName`клиента.</span><span class="sxs-lookup"><span data-stu-id="679af-113">To transfer the data to the WCF service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="679af-114">На службе служба безопасности WCF проверяет подлинность пользователя на основе имени пользователя и пароля, а также назначает роль, указанную ASP.NET роль.</span><span class="sxs-lookup"><span data-stu-id="679af-114">On the service, WCF security authenticates the user based on the user name and password, and also assigns the role specified by the ASP.NET role.</span></span>

> [!NOTE]
> <span data-ttu-id="679af-115">WCF не предоставляет методы заполнения базы данных комбинациями имени/паролем пользователя или другой информацией пользователя.</span><span class="sxs-lookup"><span data-stu-id="679af-115">WCF does not provide methods to populate the database with user name/password combinations or other user information.</span></span>

### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="679af-116">Настройка поставщика членства</span><span class="sxs-lookup"><span data-stu-id="679af-116">To configure the membership provider</span></span>

1. <span data-ttu-id="679af-117">В файле Web.config под `system.web` элементом <`membership`> создается элемент <>.</span><span class="sxs-lookup"><span data-stu-id="679af-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>

2. <span data-ttu-id="679af-118">В элементе `<membership>`.</span><span class="sxs-lookup"><span data-stu-id="679af-118">Under the `<membership>` element, create a `<providers>` element.</span></span>

3. <span data-ttu-id="679af-119">Как ребенок, чтобы `providers` <> `<clear />` элемент, добавьте элемент, чтобы промыть коллекцию поставщиков.</span><span class="sxs-lookup"><span data-stu-id="679af-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>

4. <span data-ttu-id="679af-120">Под `<clear />` элементом создайте `add` элемент <> со следующими атрибутами, установленными `enablePasswordReset` `requiresQuestionAndAnswer`на `requiresUniqueEmail`соответствующие значения: `name`, `type` `connectionStringName`, `applicationName` `enablePasswordRetrieval`, , , , , и `passwordFormat`.</span><span class="sxs-lookup"><span data-stu-id="679af-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="679af-121">Атрибут `name` используется далее в качестве значения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="679af-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="679af-122">В следующем примере задается значение `SqlMembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="679af-122">The following example sets it to `SqlMembershipProvider`.</span></span>

    <span data-ttu-id="679af-123">В следующем примере демонстрируется раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="679af-123">The following example shows the configuration section.</span></span>

    ```xml
    <!-- Configure the Sql Membership Provider -->
    <membership defaultProvider="SqlMembershipProvider" userIsOnlineTimeWindow="15">
      <providers>
        <clear />
          <add
            name="SqlMembershipProvider"
            type="System.Web.Security.SqlMembershipProvider"
            connectionStringName="SqlConn"
            applicationName="MembershipAndRoleProviderSample"
            enablePasswordRetrieval="false"
            enablePasswordReset="false"
            requiresQuestionAndAnswer="false"
            requiresUniqueEmail="true"
            passwordFormat="Hashed" />
      </providers>
    </membership>
    ```

### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="679af-124">Настройка системы безопасности службы на прием сочетания имя/пароль пользователя</span><span class="sxs-lookup"><span data-stu-id="679af-124">To configure service security to accept the user name/password combination</span></span>

1. <span data-ttu-id="679af-125">В файле конфигурации, под [ \<элементом system.serviceModel>,](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) добавьте [ \<привязки>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="679af-125">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>

2. <span data-ttu-id="679af-126">Добавьте [ \<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) в раздел привязки.</span><span class="sxs-lookup"><span data-stu-id="679af-126">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="679af-127">Для получения дополнительной информации о создании элемента связывания WCF [см.](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="679af-127">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>

3. <span data-ttu-id="679af-128">Задайте атрибуту `mode` элемента `<security>` значение `Message`.</span><span class="sxs-lookup"><span data-stu-id="679af-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>

4. <span data-ttu-id="679af-129">Установите `clientCredentialType` атрибут элемента `message` <`UserName`>.</span><span class="sxs-lookup"><span data-stu-id="679af-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="679af-130">В этом случае пара "имя пользователя и пароль" будет использоваться в качестве учетной записи клиента.</span><span class="sxs-lookup"><span data-stu-id="679af-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>

    <span data-ttu-id="679af-131">В следующем примере показан код конфигурации для привязки.</span><span class="sxs-lookup"><span data-stu-id="679af-131">The following example shows the configuration code for the binding.</span></span>

    ```xml
    <system.serviceModel>
    <bindings>
      <wsHttpBinding>
      <!-- Set up a binding that uses UserName as the client credential type -->
        <binding name="MembershipBinding">
          <security mode ="Message">
            <message clientCredentialType ="UserName"/>
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    </system.serviceModel>
    ```

### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="679af-132">Настройка службы на использование поставщика членства</span><span class="sxs-lookup"><span data-stu-id="679af-132">To configure a service to use the membership provider</span></span>

1. <span data-ttu-id="679af-133">Как ребенок, `<system.serviceModel>` добавляйте [ \<>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемент поведения</span><span class="sxs-lookup"><span data-stu-id="679af-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element</span></span>

2. <span data-ttu-id="679af-134">Добавьте><`behaviors`> элемента [ \<serviceBehaviors.](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="679af-134">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>

3. <span data-ttu-id="679af-135">Добавьте [ \<поведение>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и установите `name` атрибут соответствующим значением.</span><span class="sxs-lookup"><span data-stu-id="679af-135">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>

4. <span data-ttu-id="679af-136">Добавьте [ \<>serviceCredentials](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) `behavior` в элемент <>.</span><span class="sxs-lookup"><span data-stu-id="679af-136">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>

5. <span data-ttu-id="679af-137">Добавьте к элементу `<serviceCredentials>` [ \<>userNameAuthentication.](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md)</span><span class="sxs-lookup"><span data-stu-id="679af-137">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>

6. <span data-ttu-id="679af-138">Задайте для атрибута `userNamePasswordValidationMode` значение `MembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="679af-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="679af-139">Если `userNamePasswordValidationMode` значение не установлено, WCF использует аутентификацию Windows вместо ASP.NET поставщика членства.</span><span class="sxs-lookup"><span data-stu-id="679af-139">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the ASP.NET membership provider.</span></span>

7. <span data-ttu-id="679af-140">Задайте для атрибута `membershipProviderName` значение "имя поставщика" (указывается при добавлении поставщика в первой процедуре данного раздела).</span><span class="sxs-lookup"><span data-stu-id="679af-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="679af-141">В следующем примере показан фрагмент `<serviceCredentials>`, иллюстрирующий вышеуказанные действия.</span><span class="sxs-lookup"><span data-stu-id="679af-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>

    ```xml
    <behaviors>
       <serviceBehaviors>
          <behavior name="MyServiceBehavior">
             <serviceCredentials>
                <userNameAuthentication
                userNamePasswordValidationMode="MembershipProvider"
                membershipProviderName="SqlMembershipProvider" />
             </serviceCredentials>
          </behavior>
       </serviceBehaviors>
    </behaviors>
    ```

## <a name="example"></a><span data-ttu-id="679af-142">Пример</span><span class="sxs-lookup"><span data-stu-id="679af-142">Example</span></span>

<span data-ttu-id="679af-143">В следующем коде показана конфигурация службы, использующей возможность членства в ASP.</span><span class="sxs-lookup"><span data-stu-id="679af-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service behaviorConfiguration="MyServiceBehavior" name="Microsoft.Samples.GettingStarted.CalculatorService">
        <endpoint address="http://microsoft.com/WCFservices/Calculator"
          binding="wsHttpBinding" bindingConfiguration="MembershipBinding"
          name="ASPmemberUserName" contract="Microsoft.Samples.GettingStarted.ICalculator" />
      </service>
    </services>
    <behaviors>
      <serviceBehaviors>
        <behavior name="MyServiceBehavior">
          <serviceCredentials>
            <userNameAuthentication
              userNamePasswordValidationMode="MembershipProvider"
              membershipProviderName="SqlMembershipProvider" />
          </serviceCredentials>
        </behavior>
          </serviceBehaviors>
    </behaviors>
    <bindings>
      <wsHttpBinding>
        <binding name="MembershipBinding">
          <security mode="Message">
            <message clientCredentialType="UserName" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a><span data-ttu-id="679af-144">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="679af-144">See also</span></span>

- [<span data-ttu-id="679af-145">Практическое руководство. Использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="679af-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="679af-146">Поставщик членства и ролей</span><span class="sxs-lookup"><span data-stu-id="679af-146">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
