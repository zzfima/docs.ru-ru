---
title: "Практическое руководство. Использование поставщика членства ASP.NET"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF and ASP.NET
- WCF, authorization
- WCF, security
ms.assetid: 322c56e0-938f-4f19-a981-7b6530045b90
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6c5042e73945c54da2b1ee71fc5ea61727dc73c8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-use-the-aspnet-membership-provider"></a><span data-ttu-id="a8565-102">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="a8565-102">How to: Use the ASP.NET Membership Provider</span></span>
<span data-ttu-id="a8565-103">Поставщик членства в среде [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] - это функция, которая позволяет разработчикам [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] создавать веб-узлы с возможностью создания пользователями уникальных комбинаций имени пользователя и пароля.</span><span class="sxs-lookup"><span data-stu-id="a8565-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create unique user name and password combinations.</span></span> <span data-ttu-id="a8565-104">Эта функция позволяет любому пользователю создавать на узле учетную запись и при входе получать монопольный доступ к узлу и его службам.</span><span class="sxs-lookup"><span data-stu-id="a8565-104">With this facility, any user can establish an account with the site, and sign in for exclusive access to the site and its services.</span></span> <span data-ttu-id="a8565-105">В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="a8565-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="a8565-106">Вместо этого любой пользователь, который предоставляет свои учетные данные (сочетание имени пользователя и пароля), может использовать узел и его службы.</span><span class="sxs-lookup"><span data-stu-id="a8565-106">Instead, any user that supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="a8565-107">Пример приложения см. в разделе [поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="a8565-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="a8565-108">Дополнительные сведения об использовании [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] возможность поставщика ролей, в разделе [как: использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="a8565-108">For information about using the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider feature, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span>  
  
 <span data-ttu-id="a8565-109">Возможность членства требует использования базы данных SQL Server для хранения сведений о пользователе.</span><span class="sxs-lookup"><span data-stu-id="a8565-109">The membership feature requires using a SQL Server database to store the user information.</span></span> <span data-ttu-id="a8565-110">Эта возможность также включает методы напоминания пользователю его пароля с помощью специального вопроса.</span><span class="sxs-lookup"><span data-stu-id="a8565-110">The feature also includes methods for prompting with a question any users who have forgotten their password.</span></span>  
  
 <span data-ttu-id="a8565-111">Разработчики [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] могут воспользоваться преимуществами этих функций в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="a8565-111">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="a8565-112">Когда эти функции интегрированы в приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], пользователи должны предоставлять сочетание имя/пароль пользователя клиентскому приложению [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8565-112">When integrated into an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, users must supply a user name/password combination to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span> <span data-ttu-id="a8565-113">Для передачи данных в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] службы, привязку, которая поддерживает учетные данные имени и пароля пользователя, такие как <xref:System.ServiceModel.WSHttpBinding> (в конфигурации [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) и задайте учетные данные клиента Тип `UserName`.</span><span class="sxs-lookup"><span data-stu-id="a8565-113">To transfer the data to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, use a binding that supports user name/password credentials, such as the <xref:System.ServiceModel.WSHttpBinding> (in configuration, the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)) and set the client credential type to `UserName`.</span></span> <span data-ttu-id="a8565-114">В службе система безопасности [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] проверяет подлинность пользователя по имени и паролю пользователя и назначает роль, заданную ролью [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8565-114">On the service, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] security authenticates the user based on the user name and password, and also assigns the role specified by the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a8565-115">В [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] не предусмотрены какие-либо методы для заполнения базы данных сочетаниями имени/пароля пользователя или другими сведениями о пользователе.</span><span class="sxs-lookup"><span data-stu-id="a8565-115">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] does not provide methods to populate the database with user name/password combinations or other user information.</span></span>  
  
### <a name="to-configure-the-membership-provider"></a><span data-ttu-id="a8565-116">Настройка поставщика членства</span><span class="sxs-lookup"><span data-stu-id="a8565-116">To configure the membership provider</span></span>  
  
1.  <span data-ttu-id="a8565-117">В файле Web.config в разделе <`system.web`> элемент, создать <`membership`> элемент.</span><span class="sxs-lookup"><span data-stu-id="a8565-117">In the Web.config file, under the <`system.web`> element, create a <`membership`> element.</span></span>  
  
2.  <span data-ttu-id="a8565-118">В элементе `<membership>` создайте элемент`<providers>`.</span><span class="sxs-lookup"><span data-stu-id="a8565-118">Under the `<membership>` element, create a `<providers>` element.</span></span>  
  
3.  <span data-ttu-id="a8565-119">Как дочерние для <`providers`> элемента, добавьте `<clear />` элемент, чтобы очистить коллекцию поставщиков.</span><span class="sxs-lookup"><span data-stu-id="a8565-119">As a child to the <`providers`> element, add a `<clear />` element to flush the collection of providers.</span></span>  
  
4.  <span data-ttu-id="a8565-120">В разделе `<clear />` элемент, создать <`add`> присвойте соответствующие значения элемента со следующими атрибутами: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer` , `requiresUniqueEmail`, и `passwordFormat`.</span><span class="sxs-lookup"><span data-stu-id="a8565-120">Under the `<clear />` element, create an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, `applicationName`, `enablePasswordRetrieval`, `enablePasswordReset`, `requiresQuestionAndAnswer`, `requiresUniqueEmail`, and `passwordFormat`.</span></span> <span data-ttu-id="a8565-121">Атрибут `name` используется далее в качестве значения в файле конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a8565-121">The `name` attribute is used later as a value in the configuration file.</span></span> <span data-ttu-id="a8565-122">В следующем примере задается значение `SqlMembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="a8565-122">The following example sets it to `SqlMembershipProvider`.</span></span>  
  
     <span data-ttu-id="a8565-123">В следующем примере демонстрируется раздел конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a8565-123">The following example shows the configuration section.</span></span>  
  
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
  
### <a name="to-configure-service-security-to-accept-the-user-namepassword-combination"></a><span data-ttu-id="a8565-124">Настройка системы безопасности службы на прием сочетания имя/пароль пользователя</span><span class="sxs-lookup"><span data-stu-id="a8565-124">To configure service security to accept the user name/password combination</span></span>  
  
1.  <span data-ttu-id="a8565-125">В файле конфигурации в разделе [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемента, добавьте [ \<привязки >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="a8565-125">In the configuration file, under the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element, add a [\<bindings>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) element.</span></span>  
  
2.  <span data-ttu-id="a8565-126">Добавить [ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) для раздела привязок.</span><span class="sxs-lookup"><span data-stu-id="a8565-126">Add a [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) to the bindings section.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="a8565-127">Создание [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] элемент привязки в разделе [как: задание привязки службы в конфигурации](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="a8565-127"> creating an [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding element, see [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
3.  <span data-ttu-id="a8565-128">Задайте атрибуту `mode` элемента `<security>` значение `Message`.</span><span class="sxs-lookup"><span data-stu-id="a8565-128">Set the `mode` attribute of the `<security>` element to `Message`.</span></span>  
  
4.  <span data-ttu-id="a8565-129">Задать `clientCredentialType` атрибут <`message`> элемент `UserName`.</span><span class="sxs-lookup"><span data-stu-id="a8565-129">Set the `clientCredentialType` attribute of the <`message`> element to `UserName`.</span></span> <span data-ttu-id="a8565-130">В этом случае пара "имя пользователя и пароль" будет использоваться в качестве учетной записи клиента.</span><span class="sxs-lookup"><span data-stu-id="a8565-130">This specifies that a user name/password pair will be used as the client's credential.</span></span>  
  
     <span data-ttu-id="a8565-131">В следующем примере показан код конфигурации для привязки.</span><span class="sxs-lookup"><span data-stu-id="a8565-131">The following example shows the configuration code for the binding.</span></span>  
  
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
  
### <a name="to-configure-a-service-to-use-the-membership-provider"></a><span data-ttu-id="a8565-132">Настройка службы на использование поставщика членства</span><span class="sxs-lookup"><span data-stu-id="a8565-132">To configure a service to use the membership provider</span></span>  
  
1.  <span data-ttu-id="a8565-133">Как дочерние для `<system.serviceModel>` элемента, добавьте [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемент</span><span class="sxs-lookup"><span data-stu-id="a8565-133">As a child to the `<system.serviceModel>` element, add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element</span></span>  
  
2.  <span data-ttu-id="a8565-134">Добавить [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) для <`behaviors`> элемент.</span><span class="sxs-lookup"><span data-stu-id="a8565-134">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
3.  <span data-ttu-id="a8565-135">Добавить [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и задайте `name` соответствующее значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="a8565-135">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) and set the `name` attribute to an appropriate value.</span></span>  
  
4.  <span data-ttu-id="a8565-136">Добавить [ \<serviceCredentials >](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) для <`behavior`> элемент.</span><span class="sxs-lookup"><span data-stu-id="a8565-136">Add a [\<serviceCredentials>](../../../../docs/framework/configure-apps/file-schema/wcf/servicecredentials.md) to the <`behavior`> element.</span></span>  
  
5.  <span data-ttu-id="a8565-137">Добавить [ \<userNameAuthentication >](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) для `<serviceCredentials>` элемента.</span><span class="sxs-lookup"><span data-stu-id="a8565-137">Add a [\<userNameAuthentication>](../../../../docs/framework/configure-apps/file-schema/wcf/usernameauthentication.md) to the `<serviceCredentials>` element.</span></span>  
  
6.  <span data-ttu-id="a8565-138">Задайте для атрибута `userNamePasswordValidationMode` значение `MembershipProvider`.</span><span class="sxs-lookup"><span data-stu-id="a8565-138">Set the `userNamePasswordValidationMode` attribute to `MembershipProvider`.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="a8565-139">Если значение `userNamePasswordValidationMode` не задано, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] использует проверку подлинности Windows вместо поставщика членства [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="a8565-139">If the `userNamePasswordValidationMode` value is not set, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] uses Windows authentication instead of the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider.</span></span>  
  
7.  <span data-ttu-id="a8565-140">Задайте для атрибута `membershipProviderName` значение "имя поставщика" (указывается при добавлении поставщика в первой процедуре данного раздела).</span><span class="sxs-lookup"><span data-stu-id="a8565-140">Set the `membershipProviderName` attribute to the name of the provider (specified when adding the provider in the first procedure in this topic).</span></span> <span data-ttu-id="a8565-141">В следующем примере показан фрагмент `<serviceCredentials>`, иллюстрирующий вышеуказанные действия.</span><span class="sxs-lookup"><span data-stu-id="a8565-141">The following example shows the `<serviceCredentials>` fragment to this point.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="a8565-142">Пример</span><span class="sxs-lookup"><span data-stu-id="a8565-142">Example</span></span>  
 <span data-ttu-id="a8565-143">В следующем коде показана конфигурация службы, использующей возможность членства в ASP.</span><span class="sxs-lookup"><span data-stu-id="a8565-143">The following code shows the configuration for a service that uses the ASP membership feature.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="a8565-144">См. также</span><span class="sxs-lookup"><span data-stu-id="a8565-144">See Also</span></span>  
 [<span data-ttu-id="a8565-145">Практическое руководство. Использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="a8565-145">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 [<span data-ttu-id="a8565-146">Поставщик членства и ролей</span><span class="sxs-lookup"><span data-stu-id="a8565-146">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
