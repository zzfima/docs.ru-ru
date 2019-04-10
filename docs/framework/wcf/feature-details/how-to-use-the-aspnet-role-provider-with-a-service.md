---
title: Практическое руководство. Использование поставщика ролей ASP.NET со службой
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: 8f3fadc60645ef81d2683c63fda0ddd5bf24c982
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2019
ms.locfileid: "59301143"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="32281-102">Практическое руководство. Использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="32281-102">How to: Use the ASP.NET Role Provider with a Service</span></span>
<span data-ttu-id="32281-103">Поставщик ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] (совместно с поставщиком ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]) - возможность, позволяющая разработчикам [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] создавать веб-сайты, на которых пользователи могут создавать учетные записи и получать роли, используемые для авторизации.</span><span class="sxs-lookup"><span data-stu-id="32281-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider (in conjunction with the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider) is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="32281-104">Эта возможность позволяет любому пользователю создать на сайте учетную запись и при входе получать монопольный доступ к сайту и его службам.</span><span class="sxs-lookup"><span data-stu-id="32281-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="32281-105">В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="32281-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="32281-106">Вместо этого любой пользователь, который предоставляет свои учетные данные (сочетание имени пользователя и пароля), может использовать сайт и его службы.</span><span class="sxs-lookup"><span data-stu-id="32281-106">Instead, any user who supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="32281-107">Образец приложения, см. в разделе [поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="32281-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="32281-108">Дополнительные сведения о [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] функции поставщика участия см. в разделе [как: Использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="32281-108">For more information about the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
 <span data-ttu-id="32281-109">Возможность поставщика ролей использует базу данных SQL Server для хранения информации о пользователях.</span><span class="sxs-lookup"><span data-stu-id="32281-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="32281-110">Windows Communication Foundation (WCF) разработчикам воспользоваться преимуществами этих функций в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="32281-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="32281-111">При интеграции в приложение WCF, пользователям необходимо ввести сочетание имя/пароль пользователя клиентскому приложению WCF.</span><span class="sxs-lookup"><span data-stu-id="32281-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="32281-112">Чтобы включить WCF для использования базы данных, необходимо создать экземпляр <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> класса, задайте его <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> свойства <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>и добавьте экземпляр в коллекцию поведений узла <xref:System.ServiceModel.ServiceHost> , на котором размещена служба.</span><span class="sxs-lookup"><span data-stu-id="32281-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
### <a name="to-configure-the-role-provider"></a><span data-ttu-id="32281-113">Настройка поставщика ролей</span><span class="sxs-lookup"><span data-stu-id="32281-113">To configure the role provider</span></span>  
  
1. <span data-ttu-id="32281-114">В файле Web.config в разделе <`system.web`> элемента, добавьте <`roleManager`> и присвойте его `enabled` атрибут `true`.</span><span class="sxs-lookup"><span data-stu-id="32281-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="32281-115">Задайте для атрибута `defaultProvider` значение `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="32281-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="32281-116">Дочерний элемент <`roleManager`> элемента, добавьте <`providers`> элемента.</span><span class="sxs-lookup"><span data-stu-id="32281-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="32281-117">Дочерний элемент <`providers`> элемента, добавьте <`add`> задайте соответствующие значения элемента со следующими атрибутами: `name`, `type`, `connectionStringName`, и `applicationName`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="32281-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
    ```xml  
    <!-- Configure the Sql Role Provider. -->  
    <roleManager enabled ="true"   
     defaultProvider ="SqlRoleProvider" >  
       <providers>  
         <add name ="SqlRoleProvider"   
           type="System.Web.Security.SqlRoleProvider"   
           connectionStringName="SqlConn"   
           applicationName="MembershipAndRoleProviderSample"/>  
       </providers>  
    </roleManager>  
    ```  
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="32281-118">Настройка службы на использование поставщика ролей</span><span class="sxs-lookup"><span data-stu-id="32281-118">To configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="32281-119">Добавьте в файл Web.config, [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="32281-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="32281-120">Добавить [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемент <`system.ServiceModel`> элемента.</span><span class="sxs-lookup"><span data-stu-id="32281-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="32281-121">Добавить [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) для <`behaviors`> элемента.</span><span class="sxs-lookup"><span data-stu-id="32281-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="32281-122">Добавить [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и присвойте `name` атрибут соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="32281-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="32281-123">Добавить [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) для <`behavior`> элемента.</span><span class="sxs-lookup"><span data-stu-id="32281-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="32281-124">Задайте для атрибута `principalPermissionMode` значение `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="32281-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="32281-125">Задайте для атрибута `roleProviderName` значение `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="32281-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="32281-126">В следующем примере показан фрагмент файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="32281-126">The following example shows a fragment of the configuration.</span></span>  
  
    ```xml  
    <behaviors>  
     <serviceBehaviors>  
      <behavior name="CalculatorServiceBehavior">  
       <serviceAuthorization principalPermissionMode ="UseAspNetRoles"  
                             roleProviderName ="SqlRoleProvider" />  
      </behavior>  
     </serviceBehaviors>  
    </behaviors>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="32281-127">См. также</span><span class="sxs-lookup"><span data-stu-id="32281-127">See also</span></span>

- [<span data-ttu-id="32281-128">Поставщик членства и ролей</span><span class="sxs-lookup"><span data-stu-id="32281-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="32281-129">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="32281-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
