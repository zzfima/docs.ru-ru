---
title: Практическое руководство. Использование поставщика ролей диспетчера авторизации ASP.NET со службой
ms.date: 03/30/2017
ms.assetid: f21deb81-91ef-49ef-94d6-494785143271
ms.openlocfilehash: 778af929b4cfc96ce0683d304be5f8fb87a0e47b
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65880200"
---
# <a name="how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service"></a><span data-ttu-id="520aa-102">Практическое руководство. Использование поставщика ролей диспетчера авторизации ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="520aa-102">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>
<span data-ttu-id="520aa-103">Когда ASP.NET размещает веб-службы, диспетчер авторизации можно интегрировать в приложение для предоставления авторизации для службы.</span><span class="sxs-lookup"><span data-stu-id="520aa-103">When ASP.NET hosts a Web service, you can integrate Authorization Manager into the application to provide authorization to the service.</span></span> <span data-ttu-id="520aa-104">Диспетчер авторизации позволяет разработчику приложения определить отдельные операции, которые можно сгруппировать для образования задач.</span><span class="sxs-lookup"><span data-stu-id="520aa-104">Authorization Manager enables an application developer to define individual operations, which can be grouped together to form tasks.</span></span> <span data-ttu-id="520aa-105">Администратор затем может авторизовать роли на выполнение определенных задач или отдельных операций.</span><span class="sxs-lookup"><span data-stu-id="520aa-105">An administrator can then authorize roles to perform specific tasks or individual operations.</span></span> <span data-ttu-id="520aa-106">Диспетчер авторизации предоставляет средство администрирования в виде оснастки консоли управления (MMC) для управления ролями, задачами, операциями и пользователями.</span><span class="sxs-lookup"><span data-stu-id="520aa-106">Authorization Manager provides an administration tool as a Microsoft Management Console (MMC) snap-in to manage roles, tasks, operations, and users.</span></span> <span data-ttu-id="520aa-107">Администратор может настроить хранилище политик диспетчера авторизации в XML-файле, Active Directory или в хранилище Active Directory Application Mode (ADAM).</span><span class="sxs-lookup"><span data-stu-id="520aa-107">Administrators configure an Authorization Manager policy store in an XML file, Active Directory, or in an Active Directory Application Mode (ADAM) store.</span></span>  
  
 <span data-ttu-id="520aa-108">Диспетчер авторизации интегрируется в приложение путем настройки поставщика ролей диспетчера авторизации ASP.NET для приложения ASP.NET, на котором размещается веб-службы.</span><span class="sxs-lookup"><span data-stu-id="520aa-108">Authorization Manager is Integrated into the application by configuring the Authorization Manager ASP.NET role provider for the ASP.NET application that is hosting the Web service.</span></span> <span data-ttu-id="520aa-109">Как и другие поставщики ролей ASP.NET, настроенного поставщика ролей диспетчера авторизации ASP.NET с помощью <`providers`> элемента.</span><span class="sxs-lookup"><span data-stu-id="520aa-109">Like other ASP.NET role providers, the Authorization Manager ASP.NET role provider is configured using the <`providers`> element.</span></span>  
  
 <span data-ttu-id="520aa-110">Следующий пример кода представляет собой отрывок файла конфигурации для веб-службы, за счет которого диспетчер авторизации интегрируется в приложение.</span><span class="sxs-lookup"><span data-stu-id="520aa-110">The following code example is a portion of a configuration file for a Web service that is integrating Authorization Manager into the application.</span></span>  
  
```xml  
<system.web>  
    <roleManager enabled="true" defaultProvider="AzManRoleProvider">  
      <providers>  
        <add name="AzManRoleProvider"  
             type="System.Web.Security.AuthorizationStoreRoleProvider, System.Web, Version=2.0.0.0, Culture=neutral, publicKeyToken=b03f5f7f11d50a3a"  
             connectionStringName="AzManPolicyStoreConnectionString"   
             applicationName="SecureService"/>  
      </providers>  
    </roleManager>  
</system.web>  
```  
  
 <span data-ttu-id="520aa-111">Дополнительные сведения об интеграции поставщика ролей ASP.NET с помощью приложения WCF, см. в разделе [как: Использование поставщика ролей ASP.NET со службой](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span><span class="sxs-lookup"><span data-stu-id="520aa-111">For more information about integrating an ASP.NET role provider with a WCF application, see [How to: Use the ASP.NET Role Provider with a Service](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md).</span></span> <span data-ttu-id="520aa-112">Дополнительные сведения об использовании диспетчера авторизации с помощью ASP.NET, см. в разделе [как: Использовать диспетчер авторизации (AzMan) с помощью ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).</span><span class="sxs-lookup"><span data-stu-id="520aa-112">For more information about using Authorization Manager with ASP.NET, see [How to: Use Authorization Manager (AzMan) with ASP.NET 2.0](https://go.microsoft.com/fwlink/?LinkId=71303).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="520aa-113">См. также</span><span class="sxs-lookup"><span data-stu-id="520aa-113">See also</span></span>

- [<span data-ttu-id="520aa-114">Практическое руководство. Использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="520aa-114">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)
