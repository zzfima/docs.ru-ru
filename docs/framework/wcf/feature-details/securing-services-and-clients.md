---
title: Защита служб и клиентов
ms.date: 03/30/2017
helpviewer_keywords:
- message security [WCF]
ms.assetid: e681f3bd-0c09-4a58-b0e4-0ecbdf1aa6c7
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 60aa4da95666de01daa087c4c8e826c8cf72ba85
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/05/2018
ms.locfileid: "43734933"
---
# <a name="securing-services-and-clients"></a><span data-ttu-id="74aa2-102">Защита служб и клиентов</span><span class="sxs-lookup"><span data-stu-id="74aa2-102">Securing Services and Clients</span></span>
<span data-ttu-id="74aa2-103">Сведения этого раздела посвящена программирование безопасности в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="74aa2-103">The information in this section focuses on programming security in Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="74aa2-104">Обычно обеспечение безопасности включает выбор подходящей предоставляемой системой привязки, задание свойств элемента безопасности и задание свойств поведений службы, управляющих извлечением учетных данных для использования службой или клиентом.</span><span class="sxs-lookup"><span data-stu-id="74aa2-104">Generally, this includes selecting an appropriate system-provided binding, setting the properties of the security element, and then setting properties of the service behaviors that govern how credentials are retrieved for use by either the service or the client.</span></span> <span data-ttu-id="74aa2-105">Эти подходы охватывают требования к безопасности большинства пользователей для большинства сценариев, как показано в [типовые сценарии безопасности](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="74aa2-105">These techniques cover the security requirements of most users for most scenarios, as shown in [Common Security Scenarios](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md).</span></span> <span data-ttu-id="74aa2-106">Если сценарий требует больше возможностей, сначала ознакомьтесь с разделом [возможности безопасности при использовании пользовательских привязок](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); Если решение не очевидными, см. в разделе [расширение безопасности](../../../../docs/framework/wcf/extending/extending-security.md).</span><span class="sxs-lookup"><span data-stu-id="74aa2-106">If your scenario requires more capabilities, first see [Security Capabilities with Custom Bindings](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md); if a solution is not apparent, see [Extending Security](../../../../docs/framework/wcf/extending/extending-security.md).</span></span> <span data-ttu-id="74aa2-107">Если при создании (или взаимодействия с) система, использующая сложные утверждения, см. в пункте [авторизации](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span><span class="sxs-lookup"><span data-stu-id="74aa2-107">If you are creating (or interoperating with) a system that uses rich claims, see the topics in [Authorization](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="74aa2-108">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="74aa2-108">In This Section</span></span>  
 [<span data-ttu-id="74aa2-109">Программирование безопасности WCF</span><span class="sxs-lookup"><span data-stu-id="74aa2-109">Programming WCF Security</span></span>](../../../../docs/framework/wcf/feature-details/programming-wcf-security.md)  
 <span data-ttu-id="74aa2-110">Общие сведения о модели программирования, используемой для защиты сообщений.</span><span class="sxs-lookup"><span data-stu-id="74aa2-110">An overview of the programming model used to secure messages.</span></span>  
  
 [<span data-ttu-id="74aa2-111">Общие сведения о безопасности транспорта</span><span class="sxs-lookup"><span data-stu-id="74aa2-111">Transport Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/transport-security-overview.md)  
 <span data-ttu-id="74aa2-112">Общие сведения о защите сообщений на транспортном уровне.</span><span class="sxs-lookup"><span data-stu-id="74aa2-112">An overview of how to secure messages through the transport layer.</span></span>  
  
 [<span data-ttu-id="74aa2-113">Безопасность сообщений</span><span class="sxs-lookup"><span data-stu-id="74aa2-113">Message Security</span></span>](../../../../docs/framework/wcf/feature-details/message-security-in-wcf.md)  
 <span data-ttu-id="74aa2-114">Сводка причин для использования безопасности уровня сообщений в Windows Communication Foundation (WCF).</span><span class="sxs-lookup"><span data-stu-id="74aa2-114">Summarizes reasons for using message-level security in Windows Communication Foundation (WCF).</span></span>  
  
 [<span data-ttu-id="74aa2-115">Безопасные сеансы</span><span class="sxs-lookup"><span data-stu-id="74aa2-115">Secure Sessions</span></span>](../../../../docs/framework/wcf/feature-details/secure-sessions.md)  
 <span data-ttu-id="74aa2-116">Обсуждение вопросов, необходимых при обеспечении безопасности сеанса WCF.</span><span class="sxs-lookup"><span data-stu-id="74aa2-116">A discussion of the considerations required when securing a WCF session.</span></span>  
  
 [<span data-ttu-id="74aa2-117">Работа с сертификатами</span><span class="sxs-lookup"><span data-stu-id="74aa2-117">Working with Certificates</span></span>](../../../../docs/framework/wcf/feature-details/working-with-certificates.md)  
 <span data-ttu-id="74aa2-118">Описание некоторых стандартных задач, которые требуется выполнять при использовании сертификатов X.509.</span><span class="sxs-lookup"><span data-stu-id="74aa2-118">An explanation of some of the common tasks required when using X.509 certificates.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="74aa2-119">Ссылка</span><span class="sxs-lookup"><span data-stu-id="74aa2-119">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Security>  
  
## <a name="related-sections"></a><span data-ttu-id="74aa2-120">Связанные разделы</span><span class="sxs-lookup"><span data-stu-id="74aa2-120">Related Sections</span></span>  
 [<span data-ttu-id="74aa2-121">Основные понятия безопасности</span><span class="sxs-lookup"><span data-stu-id="74aa2-121">Security Concepts</span></span>](../../../../docs/framework/wcf/feature-details/security-concepts.md)  
  
 [<span data-ttu-id="74aa2-122">Расширение безопасности</span><span class="sxs-lookup"><span data-stu-id="74aa2-122">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="74aa2-123">Типовые сценарии безопасности</span><span class="sxs-lookup"><span data-stu-id="74aa2-123">Common Security Scenarios</span></span>](../../../../docs/framework/wcf/feature-details/common-security-scenarios.md)  
  
 [<span data-ttu-id="74aa2-124">Привязки и безопасность</span><span class="sxs-lookup"><span data-stu-id="74aa2-124">Bindings and Security</span></span>](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
  
 [<span data-ttu-id="74aa2-125">Возможности безопасности при использовании пользовательских привязок</span><span class="sxs-lookup"><span data-stu-id="74aa2-125">Security Capabilities with Custom Bindings</span></span>](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
  
 [<span data-ttu-id="74aa2-126">Расширение безопасности</span><span class="sxs-lookup"><span data-stu-id="74aa2-126">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
  
 [<span data-ttu-id="74aa2-127">Авторизация</span><span class="sxs-lookup"><span data-stu-id="74aa2-127">Authorization</span></span>](../../../../docs/framework/wcf/feature-details/authorization-in-wcf.md)  
  
## <a name="see-also"></a><span data-ttu-id="74aa2-128">См. также</span><span class="sxs-lookup"><span data-stu-id="74aa2-128">See Also</span></span>  
 [<span data-ttu-id="74aa2-129">Базовое программирование для WCF</span><span class="sxs-lookup"><span data-stu-id="74aa2-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="74aa2-130">Модель безопасности для Windows Server App Fabric</span><span class="sxs-lookup"><span data-stu-id="74aa2-130">Security Model for Windows Server App Fabric</span></span>](https://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
