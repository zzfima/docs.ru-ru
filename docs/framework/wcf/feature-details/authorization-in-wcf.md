---
title: Авторизация в WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authorization [WCF]
- security [WCF], authorization
ms.assetid: 8ea0b552-af65-45b0-a157-c6c111b8ce5e
ms.openlocfilehash: 8c605b310f19a05f994296d8f4268b91b408fb18
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2019
ms.locfileid: "65881195"
---
# <a name="authorization-in-wcf"></a><span data-ttu-id="f1eb7-102">Авторизация в WCF</span><span class="sxs-lookup"><span data-stu-id="f1eb7-102">Authorization in WCF</span></span>
<span data-ttu-id="f1eb7-103">Авторизация - процесс управления доступом и правами на ресурсы, например службы и файлы.</span><span class="sxs-lookup"><span data-stu-id="f1eb7-103">Authorization is the process of controlling access and rights to resources, such as services or files.</span></span> <span data-ttu-id="f1eb7-104">В подразделах этого раздела показано, как выполнять эту основную задачу в Windows Communication Foundation (WCF) в различными способами.</span><span class="sxs-lookup"><span data-stu-id="f1eb7-104">The topics in this section show you how to perform this basic task in Windows Communication Foundation (WCF) in a variety of ways.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f1eb7-105">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f1eb7-105">In This Section</span></span>  
 [<span data-ttu-id="f1eb7-106">Механизмы управления доступом</span><span class="sxs-lookup"><span data-stu-id="f1eb7-106">Access Control Mechanisms</span></span>](../../../../docs/framework/wcf/feature-details/access-control-mechanisms.md)  
 <span data-ttu-id="f1eb7-107">Содержит краткий обзор механизмов авторизации в WCF и предлагаемые используется.</span><span class="sxs-lookup"><span data-stu-id="f1eb7-107">Provides a brief outline of the authorization mechanisms in WCF, and suggested uses.</span></span>  
  
 [<span data-ttu-id="f1eb7-108">Практическое руководство. Ограничение доступа с использованием класса PrincipalPermissionAttribute</span><span class="sxs-lookup"><span data-stu-id="f1eb7-108">How to: Restrict Access with the PrincipalPermissionAttribute Class</span></span>](../../../../docs/framework/wcf/how-to-restrict-access-with-the-principalpermissionattribute-class.md)  
 <span data-ttu-id="f1eb7-109">Показывает процесс ограничения доступа к сервису с помощью класса <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span><span class="sxs-lookup"><span data-stu-id="f1eb7-109">Shows the process of restricting access to a service with the <xref:System.Security.Permissions.PrincipalPermissionAttribute>.</span></span>  
  
 [<span data-ttu-id="f1eb7-110">Практическое руководство. Использование поставщика ролей ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="f1eb7-110">How to: Use the ASP.NET Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-role-provider-with-a-service.md)  
 <span data-ttu-id="f1eb7-111">Расскажет об этапах настройки службы, чтобы он мог использовать возможность поставщика ролей ASP.NET.</span><span class="sxs-lookup"><span data-stu-id="f1eb7-111">Walks through the configuration of a service to enable it to use the role provider feature of ASP.NET.</span></span>  
  
 [<span data-ttu-id="f1eb7-112">Практическое руководство. Использование поставщика ролей диспетчера авторизации ASP.NET со службой</span><span class="sxs-lookup"><span data-stu-id="f1eb7-112">How to: Use the ASP.NET Authorization Manager Role Provider with a Service</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-authorization-manager-role-provider-with-a-service.md)  
 <span data-ttu-id="f1eb7-113">ASP.NET можно использовать диспетчер авторизации для управления авторизацией веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="f1eb7-113">ASP.NET can use the Authorization Manager to manage authorization for a Web site.</span></span> <span data-ttu-id="f1eb7-114">WCF аналогичным образом можно использовать комбинацию диспетчера ASP.NET/Authorization для авторизации клиентов.</span><span class="sxs-lookup"><span data-stu-id="f1eb7-114">WCF can similarly leverage the ASP.NET/Authorization Manager combination for authorization of clients.</span></span>  
  
 [<span data-ttu-id="f1eb7-115">Управление утверждениями и авторизацией с помощью модели удостоверения</span><span class="sxs-lookup"><span data-stu-id="f1eb7-115">Managing Claims and Authorization with the Identity Model</span></span>](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)  
 <span data-ttu-id="f1eb7-116">Объясняет основы использования инфраструктуры модели удостоверения для механизма авторизации на основе утверждений.</span><span class="sxs-lookup"><span data-stu-id="f1eb7-116">Explains the basics of using the Identity Model infrastructure for claims-based authorization.</span></span>  
  
 [<span data-ttu-id="f1eb7-117">Делегирование и олицетворение</span><span class="sxs-lookup"><span data-stu-id="f1eb7-117">Delegation and Impersonation</span></span>](../../../../docs/framework/wcf/feature-details/delegation-and-impersonation-with-wcf.md)  
 <span data-ttu-id="f1eb7-118">Объясняет разницу между делегированием и олицетворением.</span><span class="sxs-lookup"><span data-stu-id="f1eb7-118">Explains the difference between delegation and impersonation.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f1eb7-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="f1eb7-119">Reference</span></span>  
 <xref:System.ServiceModel.Security>  
  
 <xref:System.ServiceModel.Description.PrincipalPermissionMode>  
  
 <xref:System.ServiceModel.Description.ServiceAuthorizationBehavior>  
  
 <xref:System.Security.Permissions.PrincipalPermissionAttribute>  
  
## <a name="related-sections"></a><span data-ttu-id="f1eb7-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f1eb7-120">Related Sections</span></span>  
 [<span data-ttu-id="f1eb7-121">Authentication</span><span class="sxs-lookup"><span data-stu-id="f1eb7-121">Authentication</span></span>](../../../../docs/framework/wcf/feature-details/authentication-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="f1eb7-122">См. также</span><span class="sxs-lookup"><span data-stu-id="f1eb7-122">See also</span></span>

- [<span data-ttu-id="f1eb7-123">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="f1eb7-123">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [<span data-ttu-id="f1eb7-124">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="f1eb7-124">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
