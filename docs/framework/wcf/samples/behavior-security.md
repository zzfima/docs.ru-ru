---
title: "Безопасность поведений"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19710ae3-f197-4d28-ba9d-52e465006819
caps.latest.revision: "5"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: a125aa0968abbd69580cab46f3231a6536eff9c5
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="behavior-security"></a><span data-ttu-id="bbed5-102">Безопасность поведений</span><span class="sxs-lookup"><span data-stu-id="bbed5-102">Behavior Security</span></span>
<span data-ttu-id="bbed5-103">В этом разделе приведены образцы, демонстрирующие настройку безопасности для поведения служб.</span><span class="sxs-lookup"><span data-stu-id="bbed5-103">This section includes samples that demonstrate configuring security for service behaviors.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bbed5-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="bbed5-104">In This Section</span></span>  
 [<span data-ttu-id="bbed5-105">Поведение аудита службы</span><span class="sxs-lookup"><span data-stu-id="bbed5-105">Service Auditing Behavior</span></span>](../../../../docs/framework/wcf/samples/service-auditing-behavior.md)  
 <span data-ttu-id="bbed5-106">Этот образец демонстрирует, как использовать <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> для включения аудита событий безопасности во время выполнения операций службы.</span><span class="sxs-lookup"><span data-stu-id="bbed5-106">This sample demonstrates how to use the <xref:System.ServiceModel.Description.ServiceSecurityAuditBehavior> to enable auditing of security events during service operations.</span></span>  
  
 [<span data-ttu-id="bbed5-107">Поставщик членства и ролей</span><span class="sxs-lookup"><span data-stu-id="bbed5-107">Membership and Role Provider</span></span>](../../../../docs/framework/wcf/samples/membership-and-role-provider.md)  
 <span data-ttu-id="bbed5-108">В этом образце показано, как служба может с помощью поставщиков членства и ролей [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] выполнять проверку подлинности и авторизацию клиентов.</span><span class="sxs-lookup"><span data-stu-id="bbed5-108">This sample demonstrates how a service can use the [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] membership and role providers to authenticate and authorize clients.</span></span>  
  
 [<span data-ttu-id="bbed5-109">Авторизация доступа к операциям службы</span><span class="sxs-lookup"><span data-stu-id="bbed5-109">Authorizing Access to Service Operations</span></span>](../../../../docs/framework/wcf/samples/authorizing-access-to-service-operations.md)  
 <span data-ttu-id="bbed5-110">В этом примере демонстрируется использование [ \<serviceAuthorization >](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) включить <xref:System.Security.Permissions.PrincipalPermissionAttribute> атрибут для авторизации доступа к операциям службы.</span><span class="sxs-lookup"><span data-stu-id="bbed5-110">This sample demonstrates how to use the [\<serviceAuthorization>](../../../../docs/framework/configure-apps/file-schema/wcf/serviceauthorization-element.md) to enable use of the <xref:System.Security.Permissions.PrincipalPermissionAttribute> attribute to authorize access to service operations.</span></span>  
  
 [<span data-ttu-id="bbed5-111">Олицетворение клиента</span><span class="sxs-lookup"><span data-stu-id="bbed5-111">Impersonating the Client</span></span>](../../../../docs/framework/wcf/samples/impersonating-the-client.md)  
 <span data-ttu-id="bbed5-112">В этом образце показано, как олицетворять приложение абонента в службе таким образом, чтобы служба могла получить доступ к ресурсам системы от лица абонента.</span><span class="sxs-lookup"><span data-stu-id="bbed5-112">This sample demonstrates how to impersonate the caller application at the service so that the service can access system resources on behalf of the caller.</span></span>
