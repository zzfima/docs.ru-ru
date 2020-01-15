---
title: Аутентификация в WCF
ms.date: 03/30/2017
helpviewer_keywords:
- authentication [WCF]
- security [WCF], authentication
ms.assetid: 9254d873-843d-4c6e-bea4-8184ac3e44f4
ms.openlocfilehash: abe7aff025207ad8bdf8657daba3584e6a1b2e7f
ms.sourcegitcommit: c01c18755bb7b0f82c7232314ccf7955ea7834db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/15/2020
ms.locfileid: "75964699"
---
# <a name="authentication-in-wcf"></a><span data-ttu-id="f5db7-102">Аутентификация в WCF</span><span class="sxs-lookup"><span data-stu-id="f5db7-102">Authentication in WCF</span></span>
<span data-ttu-id="f5db7-103">В следующих разделах представлен ряд различных механизмов в Windows Communication Foundation (WCF), которые обеспечивают проверку подлинности, например, проверка подлинности Windows, сертификаты X. 509, а также имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="f5db7-103">The following topics show a number of different mechanisms in Windows Communication Foundation (WCF) that provide authentication, for example, Windows authentication, X.509 certificates, and user name and passwords.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f5db7-104">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f5db7-104">In This Section</span></span>  
 [<span data-ttu-id="f5db7-105">Практическое руководство. Использование поставщика членства ASP.NET</span><span class="sxs-lookup"><span data-stu-id="f5db7-105">How to: Use the ASP.NET Membership Provider</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-the-aspnet-membership-provider.md)  
 <span data-ttu-id="f5db7-106">Возможности ASP.NET включают членство и поставщик ролей, базу данных для хранения пар имя пользователя-пароль, используемых для проверки подлинности, и роли пользователя для авторизации.</span><span class="sxs-lookup"><span data-stu-id="f5db7-106">ASP.NET features include a membership and role provider, a database to store user name/password pairs for authentication, and user roles for authorization.</span></span> <span data-ttu-id="f5db7-107">В этом разделе объясняется, как службы WCF могут использовать одну и ту же базу данных для проверки подлинности и авторизации пользователей.</span><span class="sxs-lookup"><span data-stu-id="f5db7-107">This topic explains how WCF services can use the same database to authenticate and authorize users.</span></span>  
  
 [<span data-ttu-id="f5db7-108">Практическое руководство. Использование пользовательского проверяющего элемента управления для имени пользователя и пароля</span><span class="sxs-lookup"><span data-stu-id="f5db7-108">How to: Use a Custom User Name and Password Validator</span></span>](../../../../docs/framework/wcf/feature-details/how-to-use-a-custom-user-name-and-password-validator.md)  
 <span data-ttu-id="f5db7-109">Демонстрируется процесс интеграции настраиваемого проверяющего элемента управления для имени пользователя/пароля.</span><span class="sxs-lookup"><span data-stu-id="f5db7-109">Demonstrates how to integrate a custom user name/password validator.</span></span>  
  
 [<span data-ttu-id="f5db7-110">Идентификация и проверка подлинности службы</span><span class="sxs-lookup"><span data-stu-id="f5db7-110">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 <span data-ttu-id="f5db7-111">В качестве дополнительной защиты клиент может проверить подлинность службы, указав ожидаемое *удостоверение* службы.</span><span class="sxs-lookup"><span data-stu-id="f5db7-111">As an extra safeguard, a client can authenticate the service by specifying the expected *identity* of the service.</span></span> <span data-ttu-id="f5db7-112">Если ожидаемое и возвращаемое службой удостоверения не совпадают, проверку подлинности выполнить не удается.</span><span class="sxs-lookup"><span data-stu-id="f5db7-112">If the expected identity and the identity returned by the service do not match, authentication fails.</span></span>  
  
 [<span data-ttu-id="f5db7-113">Согласование безопасности и время ожидания</span><span class="sxs-lookup"><span data-stu-id="f5db7-113">Security Negotiation and Timeouts</span></span>](../../../../docs/framework/wcf/feature-details/security-negotiation-and-timeouts.md)  
 <span data-ttu-id="f5db7-114">Как следует использовать свойство <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> в классе <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings>.</span><span class="sxs-lookup"><span data-stu-id="f5db7-114">Describes how to use the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings.NegotiationTimeout%2A> property in the <xref:System.ServiceModel.Channels.LocalServiceSecuritySettings> class.</span></span>  
  
 [<span data-ttu-id="f5db7-115">Отладка ошибок проверки подлинности Windows</span><span class="sxs-lookup"><span data-stu-id="f5db7-115">Debugging Windows Authentication Errors</span></span>](../../../../docs/framework/wcf/feature-details/debugging-windows-authentication-errors.md)  
 <span data-ttu-id="f5db7-116">Основной акцент делается на общих выявленных проблемах при использовании проверки подлинности Windows.</span><span class="sxs-lookup"><span data-stu-id="f5db7-116">Focuses on common problems encountered when using Windows authentication.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f5db7-117">Справочные сведения</span><span class="sxs-lookup"><span data-stu-id="f5db7-117">Reference</span></span>  
 <xref:System.ServiceModel>  
  
## <a name="related-sections"></a><span data-ttu-id="f5db7-118">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f5db7-118">Related Sections</span></span>  
 [<span data-ttu-id="f5db7-119">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="f5db7-119">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
## <a name="see-also"></a><span data-ttu-id="f5db7-120">См. также:</span><span class="sxs-lookup"><span data-stu-id="f5db7-120">See also</span></span>

- [<span data-ttu-id="f5db7-121">Общие сведения о безопасности</span><span class="sxs-lookup"><span data-stu-id="f5db7-121">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)
- <span data-ttu-id="f5db7-122">[Модель безопасности для Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="f5db7-122">[Security Model for Windows Server App Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))</span></span>
