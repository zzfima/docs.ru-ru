---
title: Защита служб и клиентов
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
ms.openlocfilehash: e455c7a48e1484d5acdcc5f6cdc9098997a3ba83
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59120735"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="f7ac6-102">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="f7ac6-102">Securing Services and Clients</span></span>
<span data-ttu-id="f7ac6-103">Сведения этого раздела посвящена программирование безопасности в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f7ac6-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="f7ac6-104">Обычно обеспечение безопасности включает выбор подходящей предоставляемой системой привязки, задание свойств элемента безопасности и задание свойств поведений службы, управляющих извлечением учетных данных для использования службой или клиентом.</span><span class="sxs-lookup"><span data-stu-id="f7ac6-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="f7ac6-105">Эти подходы охватывают требования к безопасности большинства пользователей для большинства сценариев, как показано в [типовые сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="f7ac6-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="f7ac6-106">Если сценарий требует больше возможностей, сначала ознакомьтесь с разделом [возможности безопасности при использовании пользовательских привязок](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); Если решение не очевидными, см. в разделе [расширение безопасности](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="f7ac6-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="f7ac6-107">Если при создании (или взаимодействия с) система, использующая сложные утверждения, см. в пункте [авторизации](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="f7ac6-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f7ac6-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="f7ac6-108">In This Section</span></span>  
 [<span data-ttu-id="f7ac6-109">Программирование безопасности WCF</span><span class="sxs-lookup"><span data-stu-id="f7ac6-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="f7ac6-110">Общие сведения о модели программирования, используемой для защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="f7ac6-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="f7ac6-111">Общие сведения о безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="f7ac6-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="f7ac6-112">Общие сведения о защите сообщений на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="f7ac6-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="f7ac6-113">Безопасность сообщений</span><span class="sxs-lookup"><span data-stu-id="f7ac6-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="f7ac6-114">Сводка причин для использования безопасности уровня сообщений в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="f7ac6-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="f7ac6-115">Безопасные сеансы</span><span class="sxs-lookup"><span data-stu-id="f7ac6-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="f7ac6-116">Обсуждение вопросов, необходимых при обеспечении безопасности сеанса WCF.</span><span class="sxs-lookup"><span data-stu-id="f7ac6-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="f7ac6-117">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="f7ac6-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="f7ac6-118">Описание некоторых стандартных задач, которые требуется выполнять при использовании сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="f7ac6-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="f7ac6-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="f7ac6-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="f7ac6-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="f7ac6-120">Related Sections</span></span>  
 [<span data-ttu-id="f7ac6-121">Основные понятия безопасности</span><span class="sxs-lookup"><span data-stu-id="f7ac6-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="f7ac6-122">Расширение безопасности</span><span class="sxs-lookup"><span data-stu-id="f7ac6-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="f7ac6-123">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="f7ac6-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="f7ac6-124">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="f7ac6-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="f7ac6-125">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="f7ac6-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="f7ac6-126">Расширение безопасности</span><span class="sxs-lookup"><span data-stu-id="f7ac6-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="f7ac6-127">Авторизация</span><span class="sxs-lookup"><span data-stu-id="f7ac6-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="f7ac6-128">См. также</span><span class="sxs-lookup"><span data-stu-id="f7ac6-128">See also</span></span>

- [<span data-ttu-id="f7ac6-129">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="f7ac6-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="f7ac6-130">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="f7ac6-130">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
