---
title: Практическое руководство. Использование поставщика ролей ASP.NET со службой
ms.date: 03/30/2017
ms.assetid: 88d33a81-8ac7-48de-978c-5c5b1257951e
ms.openlocfilehash: ddfedeb2491998f64ab241ceba303d50d0714351
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184772"
---
# <a name="how-to-use-the-aspnet-role-provider-with-a-service"></a><span data-ttu-id="6ac0f-102">Практическое руководство. Использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="6ac0f-102">How to: Use the ASP.NET Role Provider with a Service</span></span>

<span data-ttu-id="6ac0f-103">Поставщик ASP.NET роли (совместно с ASP.NET поставщиком членства) — это функция, позволяющая ASP.NET разработчикам создавать веб-сайты, позволяющие пользователям создавать учетную запись с сайта и присваиваться роли для целей авторизации.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-103">The ASP.NET role provider (in conjunction with the ASP.NET membership provider) is a feature that enables ASP.NET developers to create Web sites that allow users to create an account with a site and to be assigned roles for authorization purposes.</span></span> <span data-ttu-id="6ac0f-104">Эта возможность позволяет любому пользователю создать на сайте учетную запись и при входе получать монопольный доступ к сайту и его службам.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-104">With this feature, any user can establish an account with the site, and log in for exclusive access to the site and its services.</span></span> <span data-ttu-id="6ac0f-105">В этом заключается отличие от безопасности Windows, по условиям которой пользователи обязаны создавать ученые записи в домене Windows.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-105">This is in contrast to Windows security, which requires users to have accounts in a Windows domain.</span></span> <span data-ttu-id="6ac0f-106">Вместо этого, любой пользователь, который поставляет свои учетные данные (комбинация имени пользователя /пароль) может использовать сайт и его услуги.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-106">Instead, any user who supplies their credentials (the user name/password combination) can use the site and its services.</span></span>  
  
<span data-ttu-id="6ac0f-107">Для примера приложения [см.](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)</span><span class="sxs-lookup"><span data-stu-id="6ac0f-107">For a sample application, see [Membership and Role Provider](../../../../docs/framework/wcf/samples/membership-and-role-provider.md).</span></span> <span data-ttu-id="6ac0f-108">Для получения дополнительной информации о функции поставщика ASP.NET членства [ASP.NET](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)см.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-108">For more information about the ASP.NET membership provider feature, see [How to: Use the ASP.NET Membership Provider](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md).</span></span>  
  
<span data-ttu-id="6ac0f-109">Возможность поставщика ролей использует базу данных SQL Server для хранения информации о пользователях.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-109">The role provider feature uses a SQL Server database to store user information.</span></span> <span data-ttu-id="6ac0f-110">Разработчики Windows Communication Foundation (WCF) могут воспользоваться этими функциями в целях безопасности.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-110">Windows Communication Foundation (WCF) developers can take advantage of these features for security purposes.</span></span> <span data-ttu-id="6ac0f-111">При интеграции в приложение WCF пользователи должны предоставить клиентское приложение WCF комбинацию имени пользователя/пароля.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-111">When integrated into a WCF application, users must supply a user name/password combination to the WCF client application.</span></span> <span data-ttu-id="6ac0f-112">Чтобы WCF мог использовать базу данных, необходимо <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> создать экземпляр <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> класса, установить его свойство <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>и добавить экземпляр в коллекцию поведения к <xref:System.ServiceModel.ServiceHost> тому, что размещает службу.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-112">To enable WCF to use the database, you must create an instance of the <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior> class, set its <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior.PrincipalPermissionMode%2A> property to <xref:System.ServiceModel.Description.PrincipalPermissionMode.UseAspNetRoles>, and add the instance to the collection of behaviors to the <xref:System.ServiceModel.ServiceHost> that is hosting the service.</span></span>  
  
## <a name="configure-the-role-provider"></a><span data-ttu-id="6ac0f-113">Настройка поставщика ролей</span><span class="sxs-lookup"><span data-stu-id="6ac0f-113">Configure the role provider</span></span>  
  
1. <span data-ttu-id="6ac0f-114">В файле Web.config под `system.web` элементом <`roleManager`> добавить `enabled` элемент `true`<> и установить его атрибут.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-114">In the Web.config file, under the <`system.web`> element, add a <`roleManager`> element and set its `enabled` attribute to `true`.</span></span>  
  
2. <span data-ttu-id="6ac0f-115">Задайте для атрибута `defaultProvider` значение `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-115">Set the `defaultProvider` attribute to `SqlRoleProvider`.</span></span>  
  
3. <span data-ttu-id="6ac0f-116">В качестве ребенка `roleManager` в элемент <`providers`> добавьте элемент> <.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-116">As a child to the <`roleManager`> element, add a <`providers`> element.</span></span>  
  
4. <span data-ttu-id="6ac0f-117">Как ребенок, к `providers` элементу <`add`>, добавьте элемент <> со `name` `type`следующими атрибутами, установленными к соответствующим значениям: , `connectionStringName`и, `applicationName`как показано в следующем примере.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-117">As a child to the <`providers`> element, add an <`add`> element with the following attributes set to appropriate values: `name`, `type`, `connectionStringName`, and `applicationName`, as shown in the following example.</span></span>  
  
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
  
## <a name="configure-the-service-to-use-the-role-provider"></a><span data-ttu-id="6ac0f-118">Настройка службы для использования ролевой услуги поставщика</span><span class="sxs-lookup"><span data-stu-id="6ac0f-118">Configure the service to use the role provider</span></span>  
  
1. <span data-ttu-id="6ac0f-119">В файле Web.config добавьте [ \<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) элемент.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-119">In the Web.config file, add a [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) element.</span></span>  
  
2. <span data-ttu-id="6ac0f-120">Добавьте элемент [ \<>поведения](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) `system.ServiceModel` в элемент> <.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-120">Add a [\<behaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/behaviors.md) element to the <`system.ServiceModel`> element.</span></span>  
  
3. <span data-ttu-id="6ac0f-121">Добавьте><`behaviors`> элемента [ \<serviceBehaviors.](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md)</span><span class="sxs-lookup"><span data-stu-id="6ac0f-121">Add a [\<serviceBehaviors>](../../../../docs/framework/configure-apps/file-schema/wcf/servicebehaviors.md) to the <`behaviors`> element.</span></span>  
  
4. <span data-ttu-id="6ac0f-122">Добавьте [ \<элемент поведения>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) и установите `name` атрибут в соответствующее значение.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-122">Add a [\<behavior>](../../../../docs/framework/configure-apps/file-schema/wcf/behavior-of-endpointbehaviors.md) element and set the `name` attribute to an appropriate value.</span></span>  
  
5. <span data-ttu-id="6ac0f-123">Добавьте [ \<>авторизации службы](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) в элемент <`behavior`>.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-123">Add a [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to the <`behavior`> element.</span></span>  
  
6. <span data-ttu-id="6ac0f-124">Задайте для атрибута `principalPermissionMode` значение `UseAspNetRoles`.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-124">Set the `principalPermissionMode` attribute to `UseAspNetRoles`.</span></span>  
  
7. <span data-ttu-id="6ac0f-125">Задайте для атрибута `roleProviderName` значение `SqlRoleProvider`.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-125">Set the `roleProviderName` attribute to `SqlRoleProvider`.</span></span> <span data-ttu-id="6ac0f-126">В следующем примере показан фрагмент файла конфигурации.</span><span class="sxs-lookup"><span data-stu-id="6ac0f-126">The following example shows a fragment of the configuration.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="6ac0f-127">См. также раздел</span><span class="sxs-lookup"><span data-stu-id="6ac0f-127">See also</span></span>

- [<span data-ttu-id="6ac0f-128">Поставщик членства и ролей</span><span class="sxs-lookup"><span data-stu-id="6ac0f-128">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)
- [<span data-ttu-id="6ac0f-129">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="6ac0f-129">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)
