---
title: "Авторизация в WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 09bbbaad055447103a1153f1888dcae4a511cbeb
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/02/2017
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="69980-102">Авторизация в WCF</span><span class="sxs-lookup"><span data-stu-id="69980-102">Authorization in WCF</span></span>
<span data-ttu-id="69980-103">Авторизация - процесс управления доступом и правами на ресурсы, например службы и файлы.</span><span class="sxs-lookup"><span data-stu-id="69980-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="69980-104">В подразделах этого раздела описано, как решить эту основную задачу в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] различными способами.</span><span class="sxs-lookup"><span data-stu-id="69980-104">The topics in this section show you how to perform this basic task in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69980-105">Содержание</span><span class="sxs-lookup"><span data-stu-id="69980-105">In This Section</span></span>  
 [<span data-ttu-id="69980-106">Механизмы управления доступом</span><span class="sxs-lookup"><span data-stu-id="69980-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="69980-107">Предоставляет краткий обзор механизмов авторизации в [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] и предлагает варианты использования.</span><span class="sxs-lookup"><span data-stu-id="69980-107">Provides a brief outline of the authorization mechanisms in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)], and suggested uses.</span></span>  
  
 [<span data-ttu-id="69980-108">Практическое руководство. Ограничение доступа с использованием класса PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="69980-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="69980-109">Показывает процесс ограничения доступа к сервису с помощью класса <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="69980-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="69980-110">Как: использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="69980-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="69980-111">Пошаговое руководство по конфигурации службы, в котором рассказывается, как разрешить ей использовать функцию поставщика ролей инфраструктуры [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span><span class="sxs-lookup"><span data-stu-id="69980-111">Walks through the configuration of a service to enable it to use the role provider feature of [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)].</span></span>  
  
 [<span data-ttu-id="69980-112">Как: использование поставщика ролей диспетчера авторизации ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="69980-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="69980-113"> может использовать диспетчер авторизации для управления авторизацией на веб-сайте.</span><span class="sxs-lookup"><span data-stu-id="69980-113"> can use the Authorization Manager to manage authorization for a Web site.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="69980-114"> может сходным образом использовать сочетание [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/диспетчер авторизации для авторизации клиентов.</span><span class="sxs-lookup"><span data-stu-id="69980-114"> can similarly leverage the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="69980-115">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="69980-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="69980-116">Объясняет основы использования инфраструктуры модели удостоверения для механизма авторизации на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="69980-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="69980-117">Делегирование и олицетворение</span><span class="sxs-lookup"><span data-stu-id="69980-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="69980-118">Объясняет разницу между делегированием и олицетворением.</span><span class="sxs-lookup"><span data-stu-id="69980-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="69980-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="69980-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="69980-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="69980-120">Related Sections</span></span>  
 [<span data-ttu-id="69980-121">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="69980-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="69980-122">См. также</span><span class="sxs-lookup"><span data-stu-id="69980-122">See Also</span></span>  
 [<span data-ttu-id="69980-123">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="69980-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="69980-124">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="69980-124">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
