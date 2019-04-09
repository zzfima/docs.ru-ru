---
title: Практическое руководство. Использование поставщика членства ASP.NET
ms.date: 03/30/2017
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
ms.openlocfilehash: df86f87bfc2456d77e3c1ee209cb8b4c61f53b21
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/08/2019
ms.locfileid: "59140612"
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="2855b-102">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="2855b-102">How to: Use the ASP.NET Membership Provider</span></span>
<span data-ttu-id="2855b-103">Поставщик членства в среде [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] - это функция, которая позволяет разработчикам [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] создавать веб-узлы с возможностью создания пользователями уникальных комбинаций имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="2855b-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="2855b-104">Эта функция позволяет любому пользователю создавать на узле учетную запись и при входе получать монопольный доступ к узлу и его службам.</span><span class="sxs-lookup"><span data-stu-id="2855b-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="2855b-105">В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="2855b-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="2855b-106">Вместо этого любой пользователь, который предоставляет свои учетные данные (сочетание имени пользователя и пароля), может использовать узел и его службы.</span><span class="sxs-lookup"><span data-stu-id="2855b-106">Instead, any user that supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="2855b-107">Образец приложения, см. в разделе [поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="2855b-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="2855b-108">Дополнительные сведения об использовании [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] функции поставщика ролей см. в разделе [как: Использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="2855b-108">For information about using the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>  
  
 <span data-ttu-id="2855b-109">Возможность членства требует использования базы данных SQL Server для хранения сведений о пользователе.</span><span class="sxs-lookup"><span data-stu-id="2855b-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="2855b-110">Эта возможность также включает методы напоминания пользователю его пароля с помощью специального вопроса.</span><span class="sxs-lookup"><span data-stu-id="2855b-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>  
  
 <span data-ttu-id="2855b-111">Windows Communication Foundation (WCF) разработчикам воспользоваться преимуществами этих функций в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="2855b-111">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="2855b-112">При интеграции в приложение WCF, пользователям необходимо ввести сочетание имя/пароль пользователя клиентскому приложению WCF.</span><span class="sxs-lookup"><span data-stu-id="2855b-112">When integrated into an WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="2855b-113">Чтобы передать данные в службу WCF, использовать привязку, которая поддерживает учетные данные имени и пароля пользователя, такие как <xref:System.ServiceModel.WSHttpBinding> (в конфигурации, [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) и задать тип учетных данных для клиента`UserName`.</span><span class="sxs-lookup"><span data-stu-id="2855b-113">To transfer the data to the WCF service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="2855b-114">В службе безопасности WCF проверяет подлинность пользователя на основе имени пользователя и пароля и назначает роль, заданную [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] роли.</span><span class="sxs-lookup"><span data-stu-id="2855b-114">On the service, WCF security authenticates the user based on the user name and password, and also assigns the role specified by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="2855b-115">WCF не поддерживает методы для заполнения базы данных с помощью сочетания имени и пароля пользователя или другие сведения о пользователе.</span><span class="sxs-lookup"><span data-stu-id="2855b-115">WCF does not provide methods to populate the database with user name/password combinations or other user information.</span></span>  
  
### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="2855b-116">Настройка поставщика членства</span><span class="sxs-lookup"><span data-stu-id="2855b-116">To configure the membership provider</span></span>  
  
1.  <span data-ttu-id="2855b-117">В файле Web.config в разделе <`system.web`> элемент, создайте <`membership`> элемента.</span><span class="sxs-lookup"><span data-stu-id="2855b-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>  
  
2.  <span data-ttu-id="2855b-118">В элементе `<membership>`<providers> создайте элемент`<providers>`.</span><span class="sxs-lookup"><span data-stu-id="2855b-118">Under the `<membership>` element, create a `<providers>` element.</span></span>  
  
3.  <span data-ttu-id="2855b-119">Дочерний элемент <`providers`> элемента, добавьте `<clear />` элемент, чтобы записать коллекцию поставщиков.</span><span class="sxs-lookup"><span data-stu-id="2855b-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>  
  
4.  <span data-ttu-id="2855b-120">В разделе `<clear />` элемент, создайте <`add`> задайте соответствующие значения элемента со следующими атрибутами: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` , `requiresUniqueEmail`, и `passwordFormat`.</span><span class="sxs-lookup"><span data-stu-id="2855b-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="2855b-121">Атрибут `name` используется далее в качестве значения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2855b-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="2855b-122">В следующем примере задается значение `SqlMembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="2855b-122">The following example sets it to `SqlMembershipProvider`.</span></span>  
  
     <span data-ttu-id="2855b-123">В следующем примере демонстрируется раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2855b-123">The following example shows the configuration section.</span></span>  
  
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
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="2855b-124">Настройка системы безопасности службы на прием сочетания имя/пароль пользователя</span><span class="sxs-lookup"><span data-stu-id="2855b-124">To configure service security to accept the user name/password combination</span></span>  
  
1.  <span data-ttu-id="2855b-125">В файле конфигурации в разделе [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемента, добавьте [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="2855b-125">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
2.  <span data-ttu-id="2855b-126">Добавить [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) в раздел привязок.</span><span class="sxs-lookup"><span data-stu-id="2855b-126">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> <span data-ttu-id="2855b-127">Дополнительные сведения о создании элемента привязки WCF, см. в разделе [как: Указание привязки службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="2855b-127">For more information about creating an WCF binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
3.  <span data-ttu-id="2855b-128">Задайте атрибуту `mode` элемента `<security>` значение `Message`.</span><span class="sxs-lookup"><span data-stu-id="2855b-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>  
  
4.  <span data-ttu-id="2855b-129">Задайте `clientCredentialType` атрибут <`message`> элемент `UserName`.</span><span class="sxs-lookup"><span data-stu-id="2855b-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="2855b-130">В этом случае пара "имя пользователя и пароль" будет использоваться в качестве учетной записи клиента.</span><span class="sxs-lookup"><span data-stu-id="2855b-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>  
  
     <span data-ttu-id="2855b-131">В следующем примере показан код конфигурации для привязки.</span><span class="sxs-lookup"><span data-stu-id="2855b-131">The following example shows the configuration code for the binding.</span></span>  
  
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
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="2855b-132">Настройка службы на использование поставщика членства</span><span class="sxs-lookup"><span data-stu-id="2855b-132">To configure a service to use the membership provider</span></span>  
  
1.  <span data-ttu-id="2855b-133">Дочерний элемент `<system.serviceModel>` элемента, добавьте [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемент</span><span class="sxs-lookup"><span data-stu-id="2855b-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element</span></span>  
  
2.  <span data-ttu-id="2855b-134">Добавить [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) для <`behaviors`> элемента.</span><span class="sxs-lookup"><span data-stu-id="2855b-134">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
3.  <span data-ttu-id="2855b-135">Добавить [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и задайте `name` атрибут соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="2855b-135">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="2855b-136">Добавить [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) для <`behavior`> элемента.</span><span class="sxs-lookup"><span data-stu-id="2855b-136">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>  
  
5.  <span data-ttu-id="2855b-137">Добавить [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) для `<serviceCredentials>` элемент.</span><span class="sxs-lookup"><span data-stu-id="2855b-137">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>  
  
6.  <span data-ttu-id="2855b-138">Задайте для атрибута `userNamePasswordValidationMode` значение `MembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="2855b-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="2855b-139">Если `userNamePasswordValidationMode` значение не задано, WCF использует проверку подлинности Windows вместо [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] поставщика членства.</span><span class="sxs-lookup"><span data-stu-id="2855b-139">If the `userNamePasswordValidationMode` value is not set, WCF uses Windows authentication instead of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider.</span></span>  
  
7.  <span data-ttu-id="2855b-140">Задайте для атрибута `membershipProviderName` значение "имя поставщика" (указывается при добавлении поставщика в первой процедуре данного раздела).</span><span class="sxs-lookup"><span data-stu-id="2855b-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="2855b-141">В следующем примере показан фрагмент `<serviceCredentials>`, иллюстрирующий вышеуказанные действия.</span><span class="sxs-lookup"><span data-stu-id="2855b-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="2855b-142">Пример</span><span class="sxs-lookup"><span data-stu-id="2855b-142">Example</span></span>  
 <span data-ttu-id="2855b-143">В следующем коде показана конфигурация службы, использующей возможность членства в ASP.</span><span class="sxs-lookup"><span data-stu-id="2855b-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2855b-144">См. также</span><span class="sxs-lookup"><span data-stu-id="2855b-144">See also</span></span>

- [<span data-ttu-id="2855b-145">Практическое руководство. Использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="2855b-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
- [<span data-ttu-id="2855b-146">Поставщик членства и ролей</span><span class="sxs-lookup"><span data-stu-id="2855b-146">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
