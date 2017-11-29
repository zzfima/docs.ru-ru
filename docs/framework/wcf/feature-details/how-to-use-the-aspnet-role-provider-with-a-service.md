---
title: "Практическое руководство. Использование поставщика ролей ASP.NET со службой"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
caps.latest.revision: "8"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bdddbd39a528e6abd6a0268db310b6173849f19b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="895fb-102">Практическое руководство. Использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="895fb-102">How to: Use the ASP.NET Role Provider with a Service</span></span>
<span data-ttu-id="895fb-103">Поставщик ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] (совместно с поставщиком ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]) - функция, позволяющая разработчикам [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] создавать веб-сайты, на которых пользователи могут создавать учетные записи и получать роли, используемые для авторизации.</span><span class="sxs-lookup"><span data-stu-id="895fb-103">The [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] role provider (in conjunction with the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider) is a feature that enables [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="895fb-104">Эта функция позволяет любому пользователю создать на сайте учетную запись и при входе получать монопольный доступ к сайту и его службам.</span><span class="sxs-lookup"><span data-stu-id="895fb-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="895fb-105">В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="895fb-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="895fb-106">Вместо этого любой пользователь, который предоставляет свои учетные данные (сочетание имени пользователя и пароля), может использовать сайт и его службы.</span><span class="sxs-lookup"><span data-stu-id="895fb-106">Instead, any user who supplies his or her credentials (the user name/password combination) can use the site and its services.</span></span>  
  
 <span data-ttu-id="895fb-107">Пример приложения см. в разделе [поставщик членства и ролей](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span><span class="sxs-lookup"><span data-stu-id="895fb-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="895fb-108">[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] функции поставщика членства, см. [как: использование поставщика членства ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span><span class="sxs-lookup"><span data-stu-id="895fb-108"> the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
 <span data-ttu-id="895fb-109">Возможность поставщика ролей использует базу данных SQL Server для хранения информации о пользователях.</span><span class="sxs-lookup"><span data-stu-id="895fb-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="895fb-110">Разработчики [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] могут воспользоваться преимуществами этих функций в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="895fb-110">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="895fb-111">Когда эти функции интегрированы в приложение [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], пользователи должны предоставлять сочетание имя/пароль пользователя клиентскому приложению [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span><span class="sxs-lookup"><span data-stu-id="895fb-111">When integrated into a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] application, users must supply a user name/password combination to the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application.</span></span> <span data-ttu-id="895fb-112">Чтобы включить использование базы данных [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], необходимо создать экземпляр класса <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>, задать его свойству <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> значение <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles> и добавить экземпляр в коллекцию поведений узла <xref:System.ServiceModel.ServiceHost>, в котором размещена служба.</span><span class="sxs-lookup"><span data-stu-id="895fb-112">To enable [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
### <a name="to-configure-the-role-provider"></a><span data-ttu-id="895fb-113">Настройка поставщика ролей</span><span class="sxs-lookup"><span data-stu-id="895fb-113">To configure the role provider</span></span>  
  
1.  <span data-ttu-id="895fb-114">В файле Web.config в разделе <`system.web`> элемента, добавьте <`roleManager`> и присвойте его `enabled` атрибут `true`.</span><span class="sxs-lookup"><span data-stu-id="895fb-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2.  <span data-ttu-id="895fb-115">Задайте для атрибута `defaultProvider` значение `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="895fb-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3.  <span data-ttu-id="895fb-116">Как дочерние для <`roleManager`> элемента, добавьте <`providers`> элемент.</span><span class="sxs-lookup"><span data-stu-id="895fb-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4.  <span data-ttu-id="895fb-117">Как дочерние для <`providers`> элемента, добавьте <`add`> присвойте соответствующие значения элемента со следующими атрибутами: `name`, `type`, `connectionStringName`, и `applicationName`, как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="895fb-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
### <a name="to-configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="895fb-118">Настройка службы на использование поставщика ролей</span><span class="sxs-lookup"><span data-stu-id="895fb-118">To configure the service to use the role provider</span></span>  
  
1.  <span data-ttu-id="895fb-119">Добавьте в файл Web.config, [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемента.</span><span class="sxs-lookup"><span data-stu-id="895fb-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2.  <span data-ttu-id="895fb-120">Добавить [ \<поведения >](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) элемента <`system.ServiceModel`> элемент.</span><span class="sxs-lookup"><span data-stu-id="895fb-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3.  <span data-ttu-id="895fb-121">Добавить [ \<serviceBehaviors >](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) для <`behaviors`> элемент.</span><span class="sxs-lookup"><span data-stu-id="895fb-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4.  <span data-ttu-id="895fb-122">Добавить [ \<поведение >](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и присвойте `name` соответствующее значение атрибута.</span><span class="sxs-lookup"><span data-stu-id="895fb-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5.  <span data-ttu-id="895fb-123">Добавить [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) для <`behavior`> элемент.</span><span class="sxs-lookup"><span data-stu-id="895fb-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6.  <span data-ttu-id="895fb-124">Задайте для атрибута `principalPermissionMode` значение `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="895fb-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7.  <span data-ttu-id="895fb-125">Задайте для атрибута `roleProviderName` значение `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="895fb-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="895fb-126">В следующем примере показан фрагмент файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="895fb-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="895fb-127">См. также</span><span class="sxs-lookup"><span data-stu-id="895fb-127">See Also</span></span>  
 [<span data-ttu-id="895fb-128">Поставщик членства и ролей</span><span class="sxs-lookup"><span data-stu-id="895fb-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 [<span data-ttu-id="895fb-129">Как: использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="895fb-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
