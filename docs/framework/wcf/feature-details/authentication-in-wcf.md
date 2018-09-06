---
title: Аутентификация в WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: 401bd8901f4d8b9292e83d3e54d0afce30c9584f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43785834"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="dc0a3-102">Аутентификация в WCF</span><span class="sxs-lookup"><span data-stu-id="dc0a3-102">Authentication in WCF</span></span>
<span data-ttu-id="dc0a3-103">В следующих разделах показаны несколько различных механизмов Windows Communication Foundation (WCF), проверки подлинности, например, проверка подлинности Windows, сертификаты X.509, имя пользователя и пароли.</span><span class="sxs-lookup"><span data-stu-id="dc0a3-103">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dc0a3-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="dc0a3-104">In This Section</span></span>  
 [<span data-ttu-id="dc0a3-105">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="dc0a3-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="dc0a3-106">Возможности ASP.NET включают членство и поставщик ролей, базу данных для хранения пар имя пользователя-пароль, используемых для проверки подлинности, и роли пользователя для авторизации.</span><span class="sxs-lookup"><span data-stu-id="dc0a3-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="dc0a3-107">В этом разделе объясняется, как службы WCF можно использовать ту же базу данных для проверки подлинности и авторизации пользователей.</span><span class="sxs-lookup"><span data-stu-id="dc0a3-107">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="dc0a3-108">Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="dc0a3-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="dc0a3-109">Демонстрируется процесс интеграции настраиваемого проверяющего элемента управления для имени пользователя/пароля.</span><span class="sxs-lookup"><span data-stu-id="dc0a3-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="dc0a3-110">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="dc0a3-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="dc0a3-111">В качестве дополнительного средства защиты, клиент может проверить подлинность службы, задавая ожидаемое *удостоверений* службы.</span><span class="sxs-lookup"><span data-stu-id="dc0a3-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="dc0a3-112">Если ожидаемое и возвращаемое службой удостоверения не совпадают, проверку подлинности выполнить не удается.</span><span class="sxs-lookup"><span data-stu-id="dc0a3-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="dc0a3-113">Согласование безопасности и время ожидания</span><span class="sxs-lookup"><span data-stu-id="dc0a3-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="dc0a3-114">Как следует использовать свойство <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> в классе <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.</span><span class="sxs-lookup"><span data-stu-id="dc0a3-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="dc0a3-115">Отладка ошибок проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="dc0a3-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="dc0a3-116">Основной акцент делается на общих выявленных проблемах при использовании проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="dc0a3-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dc0a3-117">Ссылка</span><span class="sxs-lookup"><span data-stu-id="dc0a3-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="dc0a3-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="dc0a3-118">Related Sections</span></span>  
 [<span data-ttu-id="dc0a3-119">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="dc0a3-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="dc0a3-120">См. также</span><span class="sxs-lookup"><span data-stu-id="dc0a3-120">See Also</span></span>  
 [<span data-ttu-id="dc0a3-121">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="dc0a3-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="dc0a3-122">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="dc0a3-122">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
