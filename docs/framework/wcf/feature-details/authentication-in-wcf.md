---
title: "Аутентификация в WCF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 432ed9debeffad82125b567508ed46b46d4b8821
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/22/2017
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="82a0d-102">Аутентификация в WCF</span><span class="sxs-lookup"><span data-stu-id="82a0d-102">Authentication in WCF</span></span>
<span data-ttu-id="82a0d-103">В следующем разделе показаны различные механизмы безопасности в [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)], которые обеспечивают проверку подлинности. Например, проверка подлинности Windows, сертификаты X.509, имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="82a0d-103">The following topics show a number of different mechanisms in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="82a0d-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="82a0d-104">In This Section</span></span>  
 [<span data-ttu-id="82a0d-105">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="82a0d-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="82a0d-106">Возможности ASP.NET включают членство и поставщик ролей, базу данных для хранения пар имя пользователя-пароль, используемых для проверки подлинности, и роли пользователя для авторизации.</span><span class="sxs-lookup"><span data-stu-id="82a0d-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="82a0d-107">В этом разделе объясняется, как службы [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] могут использовать ту же базу данных для проверки подлинности и авторизации пользователей.</span><span class="sxs-lookup"><span data-stu-id="82a0d-107">This topic explains how [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="82a0d-108">Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="82a0d-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="82a0d-109">Демонстрируется процесс интеграции настраиваемого проверяющего элемента управления для имени пользователя/пароля.</span><span class="sxs-lookup"><span data-stu-id="82a0d-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="82a0d-110">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="82a0d-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="82a0d-111">В качестве дополнительного средства защиты, клиент может проверить подлинность службы, задавая ожидаемое *удостоверение* службы.</span><span class="sxs-lookup"><span data-stu-id="82a0d-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="82a0d-112">Если ожидаемое и возвращаемое службой удостоверения не совпадают, проверку подлинности выполнить не удается.</span><span class="sxs-lookup"><span data-stu-id="82a0d-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="82a0d-113">Согласование безопасности и время ожидания</span><span class="sxs-lookup"><span data-stu-id="82a0d-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="82a0d-114">Как следует использовать свойство <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> в классе <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.</span><span class="sxs-lookup"><span data-stu-id="82a0d-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="82a0d-115">Отладка ошибок проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="82a0d-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="82a0d-116">Основной акцент делается на общих выявленных проблемах при использовании проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="82a0d-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="82a0d-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="82a0d-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="82a0d-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="82a0d-118">Related Sections</span></span>  
 [<span data-ttu-id="82a0d-119">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="82a0d-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="82a0d-120">См. также</span><span class="sxs-lookup"><span data-stu-id="82a0d-120">See Also</span></span>  
 [<span data-ttu-id="82a0d-121">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="82a0d-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="82a0d-122">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="82a0d-122">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
